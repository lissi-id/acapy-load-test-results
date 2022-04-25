# Multitenancy: Full Flow Increasing Load

## Virtual Machine
- 16 CPUs
- 64 GB RAM

## Setup
- 10 Holder AcaPy (Askar + separate in-memory sqlite DB for each instance)
- 15 Issuer/Verifier AcaPy (Askar + Postgres)
- 3 Sub-Wallets
- 300 Connections Max to Postgres
- 20 Connections Max per Issuer/Verifier AcaPy