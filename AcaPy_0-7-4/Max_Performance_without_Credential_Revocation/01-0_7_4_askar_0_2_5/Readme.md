# Full Flow Increasing Load

## Virtual Machine
- 16 CPUs
- 64 GB RAM

## Setup
- 10 Holder AcaPy (Askar + separate in-memory sqlite DB for each instance)
- 10 Issuer/Verifier AcaPy (Askar + Postgres) 

## Versions
- AcaPy = 0.7.4-rc.0
- Askar = 0.2.5

## Result
- at least a 11 % performance gain
- no more "Revocation registry metadata not found" Errors issuing revocable credentials
  - solves https://github.com/hyperledger/aries-cloudagent-python/issues/1586
  - solves https://github.com/hyperledger/aries-cloudagent-python/issues/1588 
