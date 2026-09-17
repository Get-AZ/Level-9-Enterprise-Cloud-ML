# Security

## Certified controls

- Endpoint authentication mode was `key`.
- Credentials were not written to certification artifacts.
- Subscription and resource identity were verified before mutations.
- Public packaging excludes keys, tokens, passwords, connection strings, raw data, and model binaries.

## Recommended production controls

- Store secrets in an approved vault and rotate them.
- Apply least-privilege Azure roles.
- Review access regularly.
- Use private networking where business risk requires it.
- Prefer managed identity or another approved identity flow where supported.
- Define log retention, privacy, and incident-response procedures.

The recommended controls are not presented as completed Level 9 evidence.
