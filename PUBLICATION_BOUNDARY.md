# Publication Boundary

## Supported claims

- Azure ML endpoint and deployment reached `Succeeded`.
- Registered model version 2 was mounted by `production-v2`.
- The container completed readiness and served scoring requests.
- Direct inference succeeded while endpoint traffic remained at zero.
- Production traffic was assigned to `production-v2` at 100 percent after authorization.
- Routed endpoint inference succeeded without a deployment override.
- Local and Azure predictions agreed for the certified record.
- Certification artifacts passed read-back and SHA256 integrity checks.
- After explicit authorization, the endpoint was deleted successfully.
- Endpoint absence was verified by both the failed exact-name lookup and absence from the endpoint list.
- The contained deployment and managed compute were removed, while registered model version 2, the workspace, and the resource group were preserved.

## Unsupported claims

This package does not claim that the endpoint is currently live. It also does not claim complete telemetry, production drift collection, Application Insights coverage, high availability, autoscaling, failover, load-tested throughput, latency objectives, private networking, managed-identity client authentication, or population-level production accuracy.

## Sensitive material excluded

Endpoint keys, access tokens, passwords, connection strings, raw datasets, model binaries, local recovery archives, and private audit logs are excluded from this publication package.
