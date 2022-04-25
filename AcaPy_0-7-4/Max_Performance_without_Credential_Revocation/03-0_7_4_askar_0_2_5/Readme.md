# Full Flow Increasing Load

## Virtual Machine
- 32 CPUs
- 32 GB RAM
- SSD

## Setup
- 18 Holder AcaPy (Askar + separate in-memory sqlite DB for each instance)
- 15 Issuer/Verifier AcaPy (Askar + Postgres) 

## Versions
- AcaPy = 0.7.4-rc.0
- Askar = 0.2.5

## Result
- maxed out at 700 iterations per minute
- hard to tell what the bottleneck is
  - Disk IO is very high
  - maybe it would be possible to further scale by running more Issuer/Verifier AcaPy instances