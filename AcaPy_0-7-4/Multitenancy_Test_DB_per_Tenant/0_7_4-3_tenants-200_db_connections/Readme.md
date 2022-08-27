# Multitenancy: Full Flow Increasing Load

## Virtual Machine
- 16 CPUs
- 64 GB RAM

## Setup
- 10 Holder AcaPy (Askar + separate in-memory sqlite DB for each instance)
- 12 Issuer/Verifier AcaPy (Askar + Postgres)
- 9 Sub-Wallets
- 200 Connections Max to Postgres
- 10 Connections Max per Issuer/Verifier AcaPy

## Versions
- AcaPy = 0.7.4-rc.0
- Askar = 0.2.5