# Full Flow with Revocation Increasing Load

## Virtual Machine
- 16 CPUs
- 64 GB RAM

## Setup
- 10 Holder AcaPy (Askar + separate in-memory sqlite DB for each instance)
- 10 Issuer/Verifier AcaPy (Askar + Postgres)   

## Special Configuration
- `TEST_FLOWS_FULL_FLOW_CREDENTIAL_REVOCATION_BATCH_SIZE=500`
- it is ensured that no parallel "Revocation Publishing" processes exist that may collide

- Error Message: `type=aries_event_error message=AcaPyPublisher.handleCredential: Error updating revocation registry index. Backend error. Caused by: error returned from database: canceling statement due to statement timeout.`