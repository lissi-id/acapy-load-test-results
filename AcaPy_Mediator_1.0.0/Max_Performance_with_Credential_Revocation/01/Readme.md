# Full Flow with Revocation Increasing Load

## Virtual Machine
- GCP e2-highcpu-16
  - 16 CPUs
  - 16 GB RAM
  
## Setup
- 10 Holder AcaPy (Askar + separate in-memory sqlite DB for each instance)
- 10 Issuer/Verifier AcaPy (Askar + Postgres) 
- Issuer/Verifier Mediator activated with 5 instances (Askar + Postgres)
- Timeout before sending the connection invitation to the holder: 0ms

## Version
- AcaPy = [75c057e2625fab3bf8b2742e2f890adba3bb8dbf](https://github.com/hyperledger/aries-cloudagent-python/commit/75c057e2625fab3bf8b2742e2f890adba3bb8dbf)

