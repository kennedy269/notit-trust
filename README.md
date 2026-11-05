# notit-trust

Signed trust files for Not It, a VPN Kyle Kennedy runs for himself and a few invited friends.

Every file here is a JWS signed by a Not It root key held in a Mac's Secure Enclave. Not It clients
check each signature against the root keys built into the app, refuse a revocation list whose
sequence number is lower than one they have already seen, and ignore anything else in this
repository. Publishing here keeps revocation working even if the Cloudflare account that runs the
rest of Not It is compromised.

| Path | What it is |
|---|---|
| `revocations/latest.jws` | The current revocation list |
| `revocations/NNNN.jws` | Every revocation list ever published, by sequence number |
| `always-on/latest.jws` | The current list of always-on exit servers (published once they exist) |

Root key IDs: `21bb3697b12c719af9ccc05c7fa8d67e` (primary) and `9beb080ae3d9d735f0ae611d71ebc84d`
(backup).
