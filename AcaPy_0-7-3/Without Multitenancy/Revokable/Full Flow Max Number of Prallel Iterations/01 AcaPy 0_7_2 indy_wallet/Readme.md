# Full Flow Max Number of Prallel Iterations

## Test Configuration
- number-of-iterations: 5000
- number-of-parallel-iterations: 5
- one iteration consists of the following steps:
  - Create a connection
  - Issue a credential
  - Send and verify a proof request
  
## Virtual Machine
- 2 CPUs
- 4 GB RAM

## Setup
- started the full load testing setup using docker compose on the VM

- Docker Containers
  - grafana/loki:2.4.2                              
  - izakmarais/grafana-reporter                     
  - grafana/grafana:latest                          
  - grafana/grafana-image-renderer:latest           
  - bcgovimages/aries-cloudagent:py36-1.16-1_0.7.2  
  - bcgovimages/aries-cloudagent:py36-1.16-1_0.7.2  
  - setup_tails-server                              
  - postgres:13.1-alpine                            
  - postgres:13.1-alpine                            
  - von-network-base                                
  - von-network-base                                
  - von-network-base                                
  - von-network-base                                
  - von-network-base                                

## Wallet
- Indy SDK
- Postgres Plugin