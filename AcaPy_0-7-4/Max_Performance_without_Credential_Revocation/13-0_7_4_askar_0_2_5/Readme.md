# Full Flow Increasing Load

## Virtual Machine
- 16 CPUs
- 16 GB RAM

## Setup
- 10 Holder AcaPy (Askar + separate in-memory sqlite DB for each instance)
- 5 Issuer/Verifier AcaPy (Askar + Postgres) 
- Issuer/Verifier Mediator activated with 5 instances (Askar + Postgres)
- Timeout before sending the connection invitation to the holder: 15000ms

## Versions
- AcaPy = 0.7.4

## Results
- max performance dropped to 80