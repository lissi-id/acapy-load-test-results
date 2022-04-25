# Full Flow Constant Load

## Virtual Machine
- 16 CPUs
- 64 GB RAM

## Setup
- 10 Holder AcaPy (Indy + separate in-memory sqlite DB for each instance)
- 10 Issuer/Verifier AcaPy (Indy + Postgres)

## Errors
### Errors via AcaPy HTTP API
- POST/issue-credential/send: 504 Gateway Time-out
- POST/connections/create-invitation: 504 Gateway Time-out
- POST/present-proof/send-request: 504 Gateway Time-out
- POST/issue-credential/send: Pool with the same name is already opened.

### Errors via Webhook Events
- AcaPyPublisher.handleCredential: Exception opening pool ledger local_test_ledger: Error: Invalid pool handle. Caused by: Pool with the same name is already opened
- AcaPyPublisher.handleProof: Exception opening pool ledger local_test_ledger: Error: Invalid pool handle. Caused by: Pool with the same name is already opened

### Revocation Registry Index
- it looks like many revocation registry index are assigned to multiple credential issuances (needs to be further analysed to be sure - e.g. to rule out any retry mechanism which leads to indices being shown multiple times)