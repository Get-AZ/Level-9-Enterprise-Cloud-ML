# Level 9 Enterprise Cloud Machine Learning Deployment

## Project summary

This project extended a governed Level 8 MLflow classification package into an Azure Machine Learning managed online endpoint. Registered model `Level_8_Production_Classifier:2` was deployed as `production-v2`, validated through direct scoring at zero endpoint traffic, and then activated as the endpoint's sole 100 percent route.

The local model, direct Azure deployment invocation, and normal routed endpoint invocation returned the same class prediction for the certified validation record. Azure logged `POST /score 200`.

**Lifecycle status:** `CERTIFIED, THEN DECOMMISSIONED`

**Serving certification:** `PASS WITH MONITORING LIMITATION`

Real-time inference and routing passed. Automatic model-input and model-output collection did not initialize, and Application Insights was disabled. This repository therefore does not claim complete production observability.

After certification, explicit authorization was provided to delete the endpoint. On 17 September 2026, Azure CLI returned exit code `0`; both endpoint `show` failure and endpoint-list absence confirmed deletion. The contained deployment and managed compute were removed. The registered model, Azure ML workspace, resource group, and local evidence were preserved.

## Certified cloud configuration

| Component | Certified value |
|---|---|
| Region | West US 2 |
| Resource group | `rg-final-enterprise-cloud-ml` |
| Azure ML workspace | `mlw-final-enterprise-cloud-ml` |
| Endpoint | `level8-bank-endpoint-r3` |
| Deployment | `production-v2` |
| Registered model | `Level_8_Production_Classifier:2` |
| Compute | `Standard_D2as_v4 x 1` |
| Certified traffic | `production-v2 = 100%` |
| Current endpoint state | `Deleted and absence verified` |
| Current managed compute | `Removed with endpoint` |
| Local prediction | `0` |
| Azure prediction | `[0]` |

## Repository map

- `docs/ARCHITECTURE.md` - verified request and serving architecture
- `docs/DEPLOYMENT_GUIDE.md` - controlled deployment sequence
- `docs/OPERATIONS_RUNBOOK.md` - health, routing, rollback, and deletion checks
- `docs/MODEL_CARD.md` - model purpose, contract, evidence, and limits
- `docs/REQUEST_SCHEMA.md` - exact 16-field input contract
- `docs/SECURITY.md` - credential and access boundaries
- `docs/MONITORING_LIMITATIONS.md` - unresolved telemetry state
- `docs/COST_GOVERNANCE.md` - running-cost estimate and decommission decision
- `PUBLICATION_BOUNDARY.md` - supported and unsupported public claims
- `evidence/DEPLOYMENT_CERTIFICATION_SUMMARY.json` - structured verified facts
- `evidence/ENDPOINT_DECOMMISSION_SUMMARY.json` - structured R5 deletion evidence
- `SHA256SUMS.txt` - integrity hashes

## Technology

Azure Machine Learning, managed online endpoints, Azure CLI ML extension, MLflow 3.15.1, Azure ML inference server 1.5.1, scikit-learn 1.6.1, skops 0.14.0, pandas 2.2.3, NumPy 2.1.3, Python, YAML, JSON, SHA256, Git, and GitHub.

## Publication status

This directory is a GitHub-ready package for the `Get-AZ` account. Its presence does not claim that a remote repository has already been created or pushed.
