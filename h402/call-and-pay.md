# Call & Pay

Once you have found a route in the [catalog](discover-routes.md), calling it is a single
request that may trigger the [payment handshake](how-paying-works.md). You can do this from
the CLI or with raw HTTP.

## With the CLI

The h402 CLI wraps the full flow — request, receive the `402` quote, sign locally, retry,
and return the result — so a caller issues one command and the payment is handled
underneath:

1. The CLI calls the route.
2. On `402`, it presents/sign the quote with the local wallet (EIP-3009 over Base USDC).
3. It retries with the signature and returns the provider result.

This is the path most agents use; see [For AI Agents](for-ai-agents.md) for setup.

## With raw HTTP

Any HTTP client can drive the same flow directly against the proxy path:

```
POST /api/proxy/{category}/{action}/{provider}
```

1. **First request** → the server returns `402 Payment Required` with the
   `PAYMENT-REQUIRED` header (the signed quote).
2. **Sign** the EIP-3009 authorization for the quoted amount/payee locally.
3. **Retry** the same request with the `PAYMENT-SIGNATURE` header → the call settles and
   returns the result with a `PAYMENT-RESPONSE` header.

Free routes skip step 1's payment requirement and return immediately.

## The response envelope

Results come back in a structured **envelope** rather than raw provider output. The
envelope wraps:

- the **provider data** (the actual result of the task), and
- **routing metadata** (which route/provider served it, settlement info).

This gives callers a consistent shape across every provider and task, so an agent does not
have to special-case each vendor's response format.

## Errors

h402 returns structured error envelopes too. If an upstream provider fails — including on
free routes — the caller receives a friendly, structured error rather than a raw upstream
failure, so error handling is uniform across routes. Combined with the **idempotency key**,
a caller can safely retry without risking a double charge.

> **TODO (operator):** drop in copy-pasteable CLI and `curl` examples against a real route
> (e.g. `ai/image-generate`) once the production domain and a stable demo route are fixed.
