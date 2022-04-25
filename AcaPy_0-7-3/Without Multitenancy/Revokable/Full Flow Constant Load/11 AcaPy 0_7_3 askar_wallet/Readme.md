# Full Flow Constant Load

## Virtual Machine
- 32 CPUs
- 32 GB RAM

## Setup
- 15 Holder AcaPy (Askar + separate in-memory sqlite DB for each instance)
- 15 Issuer/Verifier AcaPy (Askar + Postgres HA Cluster)


## Special Load Generator Configuration via `application.yml`
```
server:
   tomcat: 
      accept-count: 10000
      max-connections: 10000
      max-threads: 10000
```
