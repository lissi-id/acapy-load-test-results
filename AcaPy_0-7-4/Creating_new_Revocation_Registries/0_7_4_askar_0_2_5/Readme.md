# Full Flow Constant Load - Small RevRec Size of 10

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
- Regenerating RevRegs does not seem to crash the AcaPy from time to time anymore even if the RevReg size is very small
- Errors
  - "Revocation registry is full"
  - "Cred def id XXX has no active revocation registry"
- of 2445 credential issuances 40 failed -> 10 failed due to the errors above the other 30 might have failed due to errors on the holder side