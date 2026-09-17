# Deployment Guide

## Controlled sequence

1. Verify subscription, resource group, workspace, endpoint, and model identity.
2. Validate the local MLflow package and dependency definitions.
3. Confirm that the intended deployment name is unused.
4. Create `production-v2` with registered model version 2 and one `Standard_D2as_v4` instance.
5. Preserve endpoint traffic at zero.
6. Verify provisioning, container events, readiness, model identity, and traffic.
7. Recover and validate the 16-column inference contract.
8. Run the request locally and record the expected prediction.
9. Invoke `production-v2` directly by deployment name.
10. Compare the Azure response with the local result.
11. Obtain explicit authorization for traffic activation.
12. Assign `production-v2=100` and verify the traffic map.
13. Invoke the endpoint without a deployment override.
14. Verify prediction agreement, HTTP 200, final state, and traffic.
15. Write certification evidence and decide whether continued compute cost is justified.

## Safety boundary

Deployment creation, traffic activation, and deletion are separate changes. Passing one stage does not authorize the next stage.
