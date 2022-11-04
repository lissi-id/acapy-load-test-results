# Full Flow Constant Load at 100rpm

## Virtual Machine
- 16 CPUs
- 16 GB RAM

## Setup
- 10 Holder AcaPy (Askar + separate in-memory sqlite DB for each instance)
- 5 Issuer/Verifier AcaPy (Askar + Postgres) 
- Issuer/Verifier Mediator activated with 5 instances (Askar + Postgres)
- Timeout before sending the connection invitation to the holder: 5000ms

## Versions
- AcaPy = 0.7.4

## Results
- system crashed after 329 successful iterations
- only one mediator instance is reporting a very high amount of errors the other instances only show a low number of errors