# Full Flow Increasing Load

## Virtual Machine
- 32 CPUs
- 32 GB RAM

## Setup
- 15 Holder AcaPy (Askar + separate in-memory sqlite DB for each instance)
- 15 Issuer/Verifier AcaPy (Askar + Postgres)


## Interesting Errors
- POST/connections/receive-invitation httpCode:422 durationInMs:6.976019 body:{"recipientKeys": {"0": ["Value 1vsvuAxKariKcpsjrKjzruNUu48HUCa4dsVjaKfyDR is not a raw Ed25519VerificationKey2018 key"]}}