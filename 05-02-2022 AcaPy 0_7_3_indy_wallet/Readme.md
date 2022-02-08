# Full Process Constant Load

## Test Configuration
- number-of-iterations: 5000
- number-of-parallel-iterations: 1
- one iteration consists of the following steps:
  - Create a connection
  - Issue a credential
  - Send and verify a proof request
- Interrupted the test after ~4638 iterations accidentally
  
## Virtual Machine
- 2 CPUs
- 4 GB RAM

## Setup
- started the full load testing setup using docker compose on the VM

- Docker Containers
  - bcgovimages/aries-cloudagent:py36-1.16-1_0.7.3   
  - bcgovimages/aries-cloudagent:py36-1.16-1_0.7.3   
  - postgres:13.1-alpine                             
  - postgres:13.1-alpine                             
  - setup_tails-server                               
  - grafana/loki:2.4.2                               
  - izakmarais/grafana-reporter                      
  - grafana/grafana:latest                           
  - grafana/grafana-image-renderer:latest            
  - von-network-base                                 
  - von-network-base                                 
  - von-network-base                                 
  - von-network-base                                 
  - von-network-base                                 

## Wallet
- Indy SDK
- Postgres Plugin