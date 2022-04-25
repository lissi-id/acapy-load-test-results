# Full Flow with Revocation Increasing Load

## Virtual Machine
- 16 CPUs
- 64 GB RAM

## Setup
- 10 Holder AcaPy (Askar + separate in-memory sqlite DB for each instance)
- 10 Issuer/Verifier AcaPy (Askar + Postgres) 

## Versions
- AcaPy = 0.7.4-rc.0
- Askar = 0.2.5

## Results
- No more errors revoking credentials
