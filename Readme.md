# AcaPy Load Test Results
This repo documents load test results for the [Aries Cloud Agent Python (AcaPy)](https://github.com/hyperledger/aries-cloudagent-python).

The load tests have been performed using the [Aries Cloud Agent Load Generator](https://github.com/My-DIGI-ID/aries-cloudagent-loadgenerator).

# Findings Load Testing AcaPy 0.7.3 with Aries Askar
## Positiv Findings
### Longest endurance test
- **200 iterations per Minute for 12h (with Postgres HA):** [Revokable/Full Flow Constant Load/11 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Constant%20Load/11%20AcaPy%200_7_3%20askar_wallet)
- **200 iterations per Minute for 12h (with single Postgres):** [Revokable/Full Flow Constant Load/12 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Constant%20Load/12%20AcaPy%200_7_3%20askar_wallet)
- **300 iterations per Minute for 24h (with single Postgres):** [Non-Revokable/Full-Flow-Constant-Load/03 AcaPy 0_7_3](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Non-Revokable/Full-Flow-Constant-Load/03%20AcaPy%200_7_3%20askar_wallet)
  - non-revokable
  - holder agents threw errors after running for ca. 11 hours and ca. 200.000 iterations

### Verified maximum peak performance in full iterations per minute
#### 16 CPU / 64 RAM
- **~400 (with Single Postgres):** [Revokable/Full Flow Increasing Load/04 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Increasing%20Load/04%20AcaPy%200_7_3%20askar_wallet)
- **~550 (with Single Postgres; non-revocable credentials):** [Non-Revokable/Full-Flow-Increasing-Load/01 AcaPy 0_7_3](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Non-Revokable/Full-Flow-Increasing-Load/01%20AcaPy%200_7_3%20askar_wallet)
#### 32 CPU / 32 RAM
- **~600 (with Single Postgres):** [Revokable/Full Flow Increasing Load/11 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Increasing%20Load/11%20AcaPy%200_7_3%20askar_wallet)
- **~650 (with Postgres HA):** [Revokable/Full Flow Increasing Load/12 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Increasing%20Load/12%20AcaPy%200_7_3%20askar_wallet)

### Aries Askar seems to offer a more stable performance compared to the Indy SDK wallet
#### Test 1: 2 CPU / 4 RAM
- **Indy SDK Wallet:** [Revokable/Full Flow Max Number of Prallel Iterations/02 AcaPy 0_7_3_indy_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Max%20Number%20of%20Prallel%20Iterations/02%20AcaPy%200_7_3_indy_wallet)
- **Askar Wallet:** [Revokable/Full Flow Max Number of Prallel Iterations/03 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Max%20Number%20of%20Prallel%20Iterations/03%20AcaPy%200_7_3%20askar_wallet)
#### Test 2: 16 CPU / 64 RAM
- **Indy SDK Wallet:** [Revokable/Full Flow Constant Load/13 AcaPy 0_7_3 indy_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Constant%20Load/13%20AcaPy%200_7_3%20indy_wallet)
- **Askar Wallet:** [Revokable/Full Flow Constant Load/14 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Constant%20Load/14%20AcaPy%200_7_3%20askar_wallet)
#### Test 3: with Non-Revocable Credentials
- **Indy SDK Wallet:** [Non-Revokable/Full Flow Constant Load/02 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Non-Revokable/Full-Flow-Constant-Load/02%20AcaPy%200_7_3%20indy_wallet)
- **Askar Wallet:** [Non-Revokable/Full-Flow-Constant-Load/01 AcaPy 0_7_3](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Non-Revokable/Full-Flow-Constant-Load/01%20AcaPy%200_7_3%20askar_wallet)

### AcaPy offers the same peak performance if multitenancy is enabled and only ONE sub wallet is used
- **Without Multitenancy**
  - 400 iterations per minute: [Revokable/Full Flow Increasing Load/04 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Increasing%20Load/04%20AcaPy%200_7_3%20askar_wallet)
- **1 Sub-Wallet**
  - 400 iterations per minute: [Revokable/Full Flow Increasing Load/01 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Multitenancy/Revokable/Full%20Flow%20Increasing%20Load/01%20AcaPy%200_7_3%20askar_wallet)


### Overloading AcaPy for 10 minutes does not crash the AcaPy
- [Revokable/Full Flow Constant Load/09 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Constant%20Load/09%20AcaPy%200_7_3%20askar_wallet)
- [Revokable/Full Flow Constant Load/10 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Constant%20Load/10%20AcaPy%200_7_3%20askar_wallet)

## Identified Issues
### Credential issuance fails due to "Revocation registry metadata not found"
- **Test Reports**
  - [Revokable/Full Flow Increasing Load/08 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Increasing%20Load/08%20AcaPy%200_7_3%20askar_wallet)
  - [Revokable/Full Flow Constant Load/08 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Constant%20Load/08%20AcaPy%200_7_3%20askar_wallet)
  - Errors do not occur if credentials are not revocable: [Non-Revokable/Full-Flow-Constant-Load/01 AcaPy 0_7_3](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Non-Revokable/Full-Flow-Constant-Load/01%20AcaPy%200_7_3%20askar_wallet)
- **AcaPy Issues**
  - [AcaPy Issue 1588](https://github.com/hyperledger/aries-cloudagent-python/issues/1588)
- **Reproducibility**
  - reproducible locally using 4 CPUs and 10 GB RAM
  
### Drops in performance correlate to creation of new revocation registries
- [Revokable/Full Flow Constant Load/14 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Constant%20Load/14%20AcaPy%200_7_3%20askar_wallet)

### Any RevReg Size may or may not cause issues
Hypothesis: When ever a RevReg is full there is a chance that the system will crash completely. As smaller the RevReg size as more often a new RevReg needs to be created resulting in a hight chance that the system might crash.
- as smaller the RevReg size as higher the chance for a crash
- as higher the iteration/min rate as higher the chance for a crash

- **RevReg Size of 1.000 - Crashed:** [Revokable/Full Flow Constant Load/06 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/blob/main/Without%20Multitenancy/Revokable/Full%20Flow%20Constant%20Load/06%20AcaPy%200_7_3%20askar_wallet)
- **RevReg Size of 3.000 - Crashed:** [Revokable/Full Flow Constant Load/07 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Constant%20Load/07%20AcaPy%200_7_3%20askar_wallet)
- **RevReg Size of 3.000 - Crashed:** [Revokable/Full Flow Increasing Load/09 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Increasing%20Load/09%20AcaPy%200_7_3%20askar_wallet)
- **RevReg Size of 3.000 - No Issues:** [Revokable/Full Flow Constant Load/14 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Constant%20Load/14%20AcaPy%200_7_3%20askar_wallet)
- **RevReg Size of 10 - Crashed:** [Revokable/Full Flow Constant Load/15 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Constant%20Load/15%20AcaPy%200_7_3%20askar_wallet)
- **RevReg Size of 10 - Crashed + `statement_timeout` set to 6000 ms did not help to recover:** [Revokable/Full Flow Constant Load/16 AcaPy 0_7_3
  askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Constant%20Load/16%20AcaPy%200_7_3%20askar_wallet)
- **RevReg Size of 10 - Crashed + `lock_timeout` set to 6000 ms did not help to recover:** [Revokable/Full Flow Constant Load/17 AcaPy 0_7_3
  askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Constant%20Load/17%20AcaPy%200_7_3%20askar_wallet)
- **RevReg Size of 10 - Crashed + `lock_timeout`, `statement_timeout`, and `idle_in_transaction_session` set to 60000 ms did not help to recover:** [Revokable/Full Flow Constant Load/18 AcaPy 0_7_3
  askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Constant%20Load/18%20AcaPy%200_7_3%20askar_wallet)

### RecipientKey is not a raw Ed25519VerificationKey2018 key
- **Test Reports**
  - [Revokable/Full Flow Increasing Load/10 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Increasing%20Load/10%20AcaPy%200_7_3%20askar_wallet)
  - [Revokable/Full Flow Constant Load/08 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Constant%20Load/08%20AcaPy%200_7_3%20askar_wallet)
  - [Revokable/Full Flow Constant Load/12 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Constant%20Load/12%20AcaPy%200_7_3%20askar_wallet)
- **AcaPy Issues**
  - [AcaPy Issue 1634](https://github.com/hyperledger/aries-cloudagent-python/issues/1634)
- **Reproducibility**
  - cannot reproduce it explicitly, but have seen it multiple times

### System crashes after "Record not found" exception
- **Test Reports**
  - **RevReg Size of 3.000:** [Revokable/Full Flow Increasing Load/09 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Increasing%20Load/09%20AcaPy%200_7_3%20askar_wallet)
  - **RevReg Size of 10 and iteration/min 200:** [Revokable/Full Flow Constant Load/15 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Constant%20Load/15%20AcaPy%200_7_3%20askar_wallet)
  - **RevReg Size of 10 and iteration/min 200:** [Revokable/Full Flow Constant Load/16 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Constant%20Load/16%20AcaPy%200_7_3%20askar_wallet)
  - **RevReg Size of 10 and iteration/min 375:** [Revokable/Full Flow Constant Load/17 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Constant%20Load/17%20AcaPy%200_7_3%20askar_wallet)
  - **RevReg Size of 10 and iteration/min 200 and only one issuer/verifier:** [Revokable/Full Flow Constant Load/19 AcaPy 0_7_3
    askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Constant%20Load/19%20AcaPy%200_7_3%20askar_wallet)
- **Reproducibility**
  - can be reproduced by having a hight iteration per minute rate and small RevReg size (e.g. 10)
- **Notes**
  - "Record not found" exception is reported via webhook call (Credential Exchange Event)

### Holder database locked
- **Test Reports**
  - [Revokable/Full Flow Constant Load/07 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Constant%20Load/07%20AcaPy%200_7_3%20askar_wallet)
  - [Revokable/Full Flow Increasing Load/12 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Increasing%20Load/12%20AcaPy%200_7_3%20askar_wallet)
- **Reproducibility**
  - cannot reproduce it explicitly, but have seen it multiple times
- **Notes**
  - holder agents are using a sqlite database
  - agent does not seem to be able to recover from this error by itself
  - during the second run I/O utilization of the host VM was at 100 % as the issue occurred - during the first run I/O Utilization was only at 80 %

### AcaPy performance drops significantly if multitenancy is enabled and more than one sub wallet is used
- Errors are returned by the database:
  - Error when updating storage record value. Backend error. Caused by: error returned from database: sorry, too many clients already.
  - Error when finding storage record. Backend error. Caused by: error returned from database: sorry, too many clients already.

- **Without Multitenancy**
  - 400 iterations per minute: [Revokable/Full Flow Increasing Load/04 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Without%20Multitenancy/Revokable/Full%20Flow%20Increasing%20Load/04%20AcaPy%200_7_3%20askar_wallet)
- **1 Sub-Wallet**
  - 400 iterations per minute: [Revokable/Full Flow Increasing Load/01 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Multitenancy/Revokable/Full%20Flow%20Increasing%20Load/01%20AcaPy%200_7_3%20askar_wallet)
- **2 Sub-Wallets**
  - 350 iterations per minute: [Revokable/Full Flow Increasing Load/03 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Multitenancy/Revokable/Full%20Flow%20Increasing%20Load/03%20AcaPy%200_7_3%20askar_wallet)
- **3 Sub-Wallets**
  - XXX iterations per minute: [Revokable/Full Flow Increasing Load/04 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Multitenancy/Revokable/Full%20Flow%20Increasing%20Load/04%20AcaPy%200_7_3%20askar_wallet)