# Full Flow with Revocation Increasing Load

## Virtual Machine
- 16 CPUs
- 64 GB RAM

## Setup
- 10 Holder AcaPy (Askar + separate in-memory sqlite DB for each instance)
- 10 Issuer/Verifier AcaPy (Askar + Postgres)   

## Special Configuration
- `TEST_FLOWS_FULL_FLOW_CREDENTIAL_REVOCATION_BATCH_SIZE=50`
- it is ensured that no parallel "Revocation Publishing" processes exist that may collide

