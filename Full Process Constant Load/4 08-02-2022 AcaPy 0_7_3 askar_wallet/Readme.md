# Full Process Constant Load

## Test Configuration
- number-of-total-iterations: 5000
- number-of-iterations-per-minute: 300
- core-thread-pool-size: 300
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
- 30x Holder AcaPy
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
- stopped after ~ 1467 iterations due to too many HTTP 500 from Holder AcaPys
- Holder AcaPys fail on `POST/connections/receive-invitation` -> caused 304 failed HTTP Requests
- many connection invitations, credential issuances, and proof requests stay pending
- maybe too many Holder AcaPys try to access the same wallet DB