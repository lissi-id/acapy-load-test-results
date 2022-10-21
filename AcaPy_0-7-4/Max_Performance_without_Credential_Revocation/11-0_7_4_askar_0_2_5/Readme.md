# Full Flow Increasing Load

## Virtual Machine
- 16 CPUs
- 16 GB RAM

## Setup
- 3 Holder AcaPy (Askar + separate in-memory sqlite DB for each instance)
- 1 Issuer/Verifier AcaPy (Askar + Postgres) 
- Issuer/Verifier Mediator activated with 1 instance (Askar + Postgres)
- Timeout before sending the connection invitation to the holder: 5000ms

## Versions
- AcaPy = 0.7.4

## Results
- the single mediator instance is maxed out as it is using 94 % of CPU and cannot scale vertically any further