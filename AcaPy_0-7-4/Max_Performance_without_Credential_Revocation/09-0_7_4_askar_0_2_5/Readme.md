# Full Flow Increasing Load

## Virtual Machine
- 16 CPUs
- 16 GB RAM

## Setup
- 3 Holder AcaPy (Askar + separate in-memory sqlite DB for each instance)
- 1 Issuer/Verifier AcaPy (Askar + Postgres) 
- Issuer/Verifier Mediator activated with 1 instances (Askar + Postgres)

## Versions
- AcaPy = 0.7.4

## Results
- if many IssuerVerifier AcaPys are started each AcaPy connects to the mediator
  - this does not seem to be any issue
  - the last mediator connection that has been established will also be used as the default mediator connection
- scaling the IssuerVerifier AcaPys does not increase the performance -> remains at 100 iterations per minute