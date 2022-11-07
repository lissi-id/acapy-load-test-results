# Full Flow with Revocation - Constant Load

## Virtual Machine
- GCP e2-highcpu-16
  - 16 CPUs
  - 16 GB RAM


## Setup
- 10 Holder AcaPy (Askar + separate in-memory sqlite DB for each instance)
- 10 Issuer/Verifier AcaPy (Askar + Postgres) 

## Versions
- AcaPy = 0.7.5

## Results
- Duration: 04.11. 17:10 - 06.11. 12:30 = 43,5 h
- 200 RPM
- Started 501.253 Iterations
- Finished 500.106 Iterations
- 1.147 Failed Iterations
- CPU usage increases over time
- RAM usage increases over time