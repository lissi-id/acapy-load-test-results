# Full Flow Increasing Load

## Virtual Machine
- 16 CPUs
- 16 GB RAM

## Setup
- 3 Holder AcaPy (Askar + separate in-memory sqlite DB for each instance)
- 1 Issuer/Verifier AcaPy (Askar + Postgres) 
- Issuer/Verifier Mediator activated with 1 instances (Askar + Postgres)
- Timeout before sending the connection invitation to the holder: 1000ms

## Versions
- AcaPy = 0.7.4
