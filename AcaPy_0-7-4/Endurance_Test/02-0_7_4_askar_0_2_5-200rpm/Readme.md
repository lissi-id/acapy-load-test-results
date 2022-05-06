# Full Flow with Revocation - Constant Load

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
- > 500.000 credentials issued, requested, and revoked
- only ~250 credential issuances failed
- Grafana dashboard export failed as Loki crashed - only first 12h have been exported successfully
- Issuer/Verifier CPU usage is very constant
- Holder CPU usage grows slowly over time (maybe because of SQL Lite instead of Postgres)
