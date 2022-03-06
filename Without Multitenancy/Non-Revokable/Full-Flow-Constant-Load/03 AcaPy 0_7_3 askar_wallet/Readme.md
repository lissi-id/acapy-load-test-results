# No Revocation - Full Flow - Constant Load

## Virtual Machine
- 16 CPUs
- 64 GB RAM

## Setup
- 10 Holder AcaPy (Askar + separate in-memory sqlite DB for each instance)
- 10 Issuer/Verifier AcaPy (Askar + Postgres)                             


## New Error Messages Reported via Webhook Events
- 1x type=aries_event_error message=AcaPyPublisher.handleCredential: ConnectionTarget schema validation failed. {'recipient_keys': {0: ['Value 1wa1uqPwRKF3xtV2csFsXS1xv5PK7BjNunZZqnYMJ7 is not a raw Ed25519VerificationKey2018 key']}}. time=1646355517173
- 6x type=aries_event_error message=AcaPyPublisher.handleProof: abandoned: abandoned
- 17x type=aries_event_error message=AcaPyPublisher.handleCredential: issuance-abandoned: issuance-abandoned