# Full Flow with Revocation Increasing Load

## Virtual Machine
- 16 CPUs
- 64 GB RAM

## Setup
- 10 Holder AcaPy (Askar + separate in-memory sqlite DB for each instance)
- 10 Issuer/Verifier AcaPy (Askar + Postgres)   

## Cause
In the version of the Load Generator used, the `numberOfBatchedCredentialRevocations` was only reset AFTER the revocation publishing process finished successfully. This led to other threads also triggering revocation publishing processes. All the parallel running revocation publishing processes seem
to block each other on the database resulting in a crash of the system.

### Logs show parallel started revocation publishing processes
2022-03-22 07:34:43	class=c.b.s.g.a.l.HttpRequestLogger thread=http-nio-8080-exec-15 | type=http_request request=POST/revocation/revoke httpCode=504 durationInMs=60000.047783 
2022-03-22 07:34:39	class=c.b.s.g.a.l.HttpRequestLogger thread=http-nio-8080-exec-9 | type=http_request request=POST/revocation/revoke httpCode=504 durationInMs=60000.642343 
2022-03-22 07:34:39	class=c.b.s.g.a.l.HttpRequestLogger thread=http-nio-8080-exec-2 | type=http_request request=POST/revocation/revoke httpCode=504 durationInMs=60000.20286 
2022-03-22 07:34:38	class=c.b.s.g.a.l.HttpRequestLogger thread=http-nio-8080-exec-8 | type=http_request request=POST/revocation/revoke httpCode=504 durationInMs=60000.301311 
2022-03-22 07:34:38	class=c.b.s.g.a.l.HttpRequestLogger thread=http-nio-8080-exec-5 | type=http_request request=POST/revocation/revoke httpCode=504 durationInMs=60000.457534