# Multitenancy: Full Flow Increasing Load

## Virtual Machine
- 16 CPUs
- 64 GB RAM

## Setup
- 10 Holder AcaPy (Askar + separate in-memory sqlite DB for each instance)
- 12 Issuer/Verifier AcaPy (Askar + Postgres)
- 9 Sub-Wallets
- 950 Connections Max to Postgres
- 10 Connections Max per Issuer/Verifier AcaPy
- **Configured Issuer-Verifier AcaPy to use same database for all tenants**
  - added `--multitenancy-config '{\"wallet_type\":\"askar-profile\",\"wallet_name\":\"wallet_db\"}'` to issuer-verifier AcaPys

## Versions
- AcaPy = 0.7.4