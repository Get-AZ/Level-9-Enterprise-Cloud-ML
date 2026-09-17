# Operations Runbook

## Routine checks

These checks apply only after a future redeployment. The certified endpoint is currently deleted.

- Confirm endpoint provisioning state is `Succeeded`.
- Confirm deployment `production-v2` is `Succeeded`.
- Confirm the deployment still references registered model version 2.
- Inspect the endpoint traffic map.
- Review recent container errors and `POST /score` status.
- Send a controlled non-sensitive reference request.
- Compare the result with an approved expected value.
- Review current Azure cost and whether the endpoint still needs to be live.

## Rollback

If routed validation fails, set `production-v2` traffic to zero and verify the new traffic map. Review schema, model identity, dependencies, and logs before another activation. A mature blue-green release should retain a known-good deployment for immediate fallback.

## Decommission

R5 completed this procedure on 17 September 2026. Final evidence was preserved, explicit authorization was recorded, and `level8-bank-endpoint-r3` was deleted. Exact-name lookup failed with exit code `3`, and the endpoint list did not contain the target. The contained deployment and managed compute were removed. The workspace, registered model version 2, resource group, and local certification package were retained.

## Redeployment boundary

The scoring URI is no longer operational. Any future service restoration requires explicit authorization and a new endpoint/deployment workflow; do not represent the historical URI as live.
