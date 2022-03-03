# No Revocation - Full Flow - Constant Load

## Virtual Machine
- 16 CPUs
- 64 GB RAM

## Setup
- 10 Holder AcaPy (Indy + separate in-memory sqlite DB for each instance)
- 10 Issuer/Verifier AcaPy (Indy + Postgres)   

## Configuration
- `lock_timeout` set to 60000 ms
- `statement_timeout` set to 60000 ms
- `idle_in_transaction_session_timeout` set to 60000 ms