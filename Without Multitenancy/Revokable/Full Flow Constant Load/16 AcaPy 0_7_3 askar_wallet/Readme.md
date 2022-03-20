# Full Flow Constant Load

## Virtual Machine
- 16 CPUs
- 64 GB RAM

## Setup
- 10 Holder AcaPy (Askar + separate in-memory sqlite DB for each instance)
- 10 Issuer/Verifier AcaPy (Askar + Postgres)   

## Configuration
- very small RevReg size of 10
- `statement_timeout` set to 6000 ms