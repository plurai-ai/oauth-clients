# oauth-clients

Client ID Metadata Documents for Plurai's OAuth clients. Each document's URL is the client's `client_id`, and the
authorization server (Clerk) fetches it from here.

| File | Client | Environment |
|---|---|---|
| `plurai-sdk-staging.json` | Plurai SDK (`plurai login`) | staging |

Rules for every document:

- It is served as `application/json` with no redirect, and its `client_id` equals the exact URL it is served at.
- Its URL is carried by the SDK. Moving or renaming a file breaks the login until the SDK names the new URL.
- It holds no secret: the SDK is a public client (`token_endpoint_auth_method: none`).

The production document is hosted by the backend.
