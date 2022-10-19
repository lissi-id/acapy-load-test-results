# Full Flow Increasing Load

## Virtual Machine
- 16 CPUs
- 16 GB RAM

## Setup
- 3 Holder AcaPy (Askar + separate in-memory sqlite DB for each instance)
- 1 Issuer/Verifier AcaPy (Askar + Postgres) 
- Issuer/Verifier Mediator activated

## Versions
- AcaPy = 0.7.4

## Result
- 1 Error: "Value is not an indy credential definition identifier" -> right at the beginning of the tests; does not seem to be relevant
- max performance with mediator seems to be **100 iterations** per minute
- without mediator the max performance is **at least 150 iterations** per minute
- Mediator Errors: many "RouteRecord record not found for {'recipient_key': 'XXX'}"
- Hypothesis for "RouteRecord record not found for {'recipient_key': 'XXX'}" errors: AcaPy takes too long to register recipient key to mediator in case the mediator is overloaded and the holder agent reached out to the mediator before the recipient key has been registered