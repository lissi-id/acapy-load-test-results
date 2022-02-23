# AcaPy Load Test Results
This repo documents load test results for the [Aries Cloud Agent Python (AcaPy)](https://github.com/hyperledger/aries-cloudagent-python).

The load tests have been performed using the [Aries Cloud Agent Load Generator](https://github.com/My-DIGI-ID/aries-cloudagent-loadgenerator).

# Findings Load Testing AcaPy 0.7.3 with Aries Askar
## Positiv Findings
### Overloading AcaPy for 10 minutes does not crash the AcaPy
- [Full Flow Constant Load/09 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Full%20Flow%20Constant%20Load/09%20AcaPy%200_7_3%20askar_wallet)
- [Full Flow Constant Load/10 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Full%20Flow%20Constant%20Load/10%20AcaPy%200_7_3%20askar_wallet)

### Longest endurance test
- **200 iterations per Minute for 12h (with Postgres HA):** [Full Flow Constant Load/11 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Full%20Flow%20Constant%20Load/11%20AcaPy%200_7_3%20askar_wallet)
- **200 iterations per Minute for 12h (with single Postgres):** [Full Flow Constant Load/12 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Full%20Flow%20Constant%20Load/12%20AcaPy%200_7_3%20askar_wallet)

### Verified maximum performance of > 600 full iterations per minute
- **~600 (with Single Postgres):** [Full Flow Increasing Load/11 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Full%20Flow%20Increasing%20Load/11%20AcaPy%200_7_3%20askar_wallet)
- **~650 (with Postgres HA):** [Full Flow Increasing Load/12 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Full%20Flow%20Increasing%20Load/12%20AcaPy%200_7_3%20askar_wallet)

### Aries Askar seems to offer a more stable performance compared to the Indy SDK wallet
- **Indy SDK Wallet:** [Full Flow Max Number of Prallel Iterations/02 AcaPy 0_7_3_indy_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Full%20Flow%20Max%20Number%20of%20Prallel%20Iterations/02%20AcaPy%200_7_3_indy_wallet)
- **Askar Wallet:** [Full Flow Max Number of Prallel Iterations/03 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Full%20Flow%20Max%20Number%20of%20Prallel%20Iterations/03%20AcaPy%200_7_3%20askar_wallet)

## Identified Issues
### Credential issuance fails due to "Revocation registry metadata not found"
- **Test Reports**
  - [Full Flow Increasing Load/08 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Full%20Flow%20Increasing%20Load/08%20AcaPy%200_7_3%20askar_wallet)
  - [Full Flow Constant Load/08 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Full%20Flow%20Constant%20Load/08%20AcaPy%200_7_3%20askar_wallet)
- **AcaPy Issues**
  - [AcaPy Issue 1588](https://github.com/hyperledger/aries-cloudagent-python/issues/1588)
- **Reproducibility**
  - reproducible locally using 4 CPUs and 10 GB RAM

### RecipientKey is not a raw Ed25519VerificationKey2018 key
- **Test Reports**
  - [Full Flow Increasing Load/10 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Full%20Flow%20Increasing%20Load/10%20AcaPy%200_7_3%20askar_wallet)
  - [Full Flow Constant Load/08 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Full%20Flow%20Constant%20Load/08%20AcaPy%200_7_3%20askar_wallet)
  - [Full Flow Constant Load/12 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Full%20Flow%20Constant%20Load/12%20AcaPy%200_7_3%20askar_wallet)
- **AcaPy Issues**
  - [AcaPy Issue 1634](https://github.com/hyperledger/aries-cloudagent-python/issues/1634)
- **Reproducibility**
  - cannot reproduce it explicitly, but have seen it multiple times

### System crashes after "Record not found" exception
- **Test Reports**
  - [Full Flow Increasing Load/09 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Full%20Flow%20Increasing%20Load/09%20AcaPy%200_7_3%20askar_wallet)
- **Reproducibility**
  - cannot reproduce it explicitly, but have seen it multiple times
- **Notes**
  - "Record not found" exception is reported via webhook call (Credential Exchange Event)

### Holder database locked
- **Test Reports**
  - [Full Flow Constant Load/07 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Full%20Flow%20Constant%20Load/07%20AcaPy%200_7_3%20askar_wallet)
  - [Full Flow Increasing Load/12 AcaPy 0_7_3 askar_wallet](https://github.com/lissi-id/acapy-load-test-results/tree/main/Full%20Flow%20Increasing%20Load/12%20AcaPy%200_7_3%20askar_wallet)
- **Reproducibility**
  - cannot reproduce it explicitly, but have seen it multiple times
- **Notes**
  - holder agents are using a sqlite database
  - agent does not seem to be able to recover from this error by itself
  - during the second run I/O utilization of the host VM was at 100 % as the issue occurred - during the first run I/O Utilization was only at 80 %
