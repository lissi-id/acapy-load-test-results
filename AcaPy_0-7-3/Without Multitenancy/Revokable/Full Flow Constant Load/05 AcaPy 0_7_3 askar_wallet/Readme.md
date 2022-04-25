# Full Flow Constant Load

## Test Configuration
- number-of-total-iterations: 10000
- number-of-iterations-per-minute: 200
- core-thread-pool-size: 200
- use-connectionless-proof-requests: false
- one iteration consists of the following steps:
  - Create a connection
  - Issue a credential
  - Send and verify a proof request
  
## Virtual Machine
- 32 CPUs
- 32 GB RAM

## Setup
- started the full load testing setup using docker compose on the VM
- 10x Issuer/Verifier AcaPy
- 20x Holder AcaPy
- Docker Images
  - bcgovimages/aries-cloudagent:py36-1.16-1_0.7.3
  - nginx:latest                                  
  - postgres:13.1-alpine                          
  - setup_tails-server                            
  - grafana/loki:2.4.2                            
  - grafana/grafana-image-renderer:latest         
  - izakmarais/grafana-reporter                   
  - grafana/grafana:latest                        
  - von-network-base                             

## Wallet
- Askar
- Postgres Plugin


## Ended
- stopped after ~ 4000 iterations due to very poor performance
- surprisingly, the test results `3 08-02-2022 AcaPy 0_7_3 askar_wallet` were better and could not be reproduced in the context of this test run