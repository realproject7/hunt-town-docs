# Call & Pay

Once you have picked a capability and a [provider](providers.md), calling it is a single
request that may trigger the [payment handshake](how-paying-works.md).

## With the CLI

```
h402 call web/search --json '{"query":"onchain agent payments"}'
```

The CLI resolves the provider (explicit `--provider`, or the catalog's recommended default),
issues the call, handles the `402` challenge, signs locally with your wallet, retries, and
returns the result.

Useful flags:

| Flag | Effect |
| --- | --- |
| `--provider <name>` | Pin a specific provider instead of the recommended default |
| `--max-usd <usd>` | Refuse the call if the quote exceeds this amount |
| `--no-credit` | Pay in USDC even if credits are available |
| `--idempotency-key <uuid>` | Supply your own key for a retry |

Every successful response reports **which provider served it** and **how it was chosen**
(explicitly, or from the catalog default), plus a copy-pasteable pinned command that
reproduces the exact call.

## With raw HTTP

Any HTTP client can drive the same flow against the pinned path:

```
POST /routes/{provider}/{category}/{action}
```

1. **Call** with an `idempotency-key` header and no payment.
2. If the capability is free — or covered by credit — you get the result immediately.
3. Otherwise the server returns **`402`** with the price challenge.
4. **Sign** an EIP-3009 authorization for the quoted amount, locally.
5. **Retry the same request, with the same idempotency key**, attaching the signature. The
   call settles and returns.

## The response

Results come back in a consistent envelope rather than raw upstream output:

```
{ "data": { ... },        // the provider's result
  "meta": { ... },        // optional provider metadata
  "h402": { ... } }       // pinned provider, payment mode, follow-up info
```

The `h402` block is what makes a call auditable after the fact: it records the provider that
served the request and how payment was handled. For long-running jobs it also carries a
**follow-up instruction** telling the caller how to poll for the finished result.

## Retries and double charges

The idempotency key is **double-charge protection, not result replay**. Reusing it on a
retry ensures a flaky network cannot cause two payments for one task.

One deliberate safety property: if the server responds to a retry with a *replacement*
payment challenge, the client **refuses it automatically**. Creating a new payment requires
a fresh, explicit call — an unattended agent cannot be walked into paying twice by a
surprise re-quote.

## Errors

Upstream failures are returned as structured errors rather than raw provider output, so
error handling is uniform across providers. h402 never forwards a request whose payment
state is ambiguous; unresolved settlements are reconciled rather than silently retried
against a different provider.

> **TODO (operator):** replace the illustrative command above with copy-pasteable CLI and
> `curl` examples against a real capability and provider once the production domain is live.
