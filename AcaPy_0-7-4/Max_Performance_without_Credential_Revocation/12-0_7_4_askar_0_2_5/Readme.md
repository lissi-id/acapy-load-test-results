# Full Flow Increasing Load

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
- even though the timeout has been introduced the number of "Error resolving recipient for forwarded message" errors remains the same
- while a singe mediator instance used 94 % CPU in this scaled setup each mediator only uses 34 % CPU and are therefore not under a high load