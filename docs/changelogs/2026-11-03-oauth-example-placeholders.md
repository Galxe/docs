# security: use explicit placeholders in OAuth examples

## 1. Background

The OAuth documentation contains four opaque access/refresh token values in
example responses. Their validity is unknown; no issuer-side validation or
revocation is claimed.

## 2. Behavior

Example responses now show `<ACCESS_TOKEN>` and `<REFRESH_TOKEN>`. The API
contract and surrounding instructions do not change.

## 3. Findings

The values were present in both the current document and historical versions.
They are treated as examples with unknown provenance, not confirmed active
credentials.

## 4. Change

Replace only the four example values in
`galxe-id/galxe-id-integration/galxe-id-oauth.mdx`.

## 5. Verification

Exactly four replacements were made; modified JSON examples parse successfully.
The staged diff passes whitespace checking and the added-content secret scan.
No executable code or API behavior changes.

## 6. Authorization

Prepared during the requested security follow-up for Galxe-related organizations.
This is a draft for review, with no merge or publication to the documentation site.

## 7. Outcome

New documentation builds will no longer embed the four opaque values after merge.

## 8. Remaining work

The Galxe ID service owner should identify and revoke the old values if they were
issued credentials. Replacing examples does not revoke credentials or erase history.
