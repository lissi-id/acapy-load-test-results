# Load Test Results for AcaPy 0.7.4 with Aries Askar
## Positiv Findings
- at least a 11 % performance gain compared to 0.7.3
- no more "Revocation registry metadata not found" Errors issuing revocable credentials
  - solves https://github.com/hyperledger/aries-cloudagent-python/issues/1586
  - solves https://github.com/hyperledger/aries-cloudagent-python/issues/1588 
- no more errors revoking credentials
- AcaPy did never crash completely
- Max performance was 700 rpm without revocation using a 32CPU, 32GB, SSD VM (Single Postgres instance)