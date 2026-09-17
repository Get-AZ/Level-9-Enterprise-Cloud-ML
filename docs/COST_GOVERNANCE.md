# Cost Governance

The deployment used one `Standard_D2as_v4` instance in West US 2. The public Linux pay-as-you-go rate observed on 17 September 2026 was approximately `$0.096 per hour`.

| Period | Estimated base compute |
|---|---:|
| Hour | $0.096 |
| 24 hours | $2.30 |
| 7 days | $16.13 |
| 730-hour month | $70.08 |
| 365 days | $840.96 |

Actual cost can differ because of credits, contract pricing, taxes, storage, logging, bandwidth, and later price changes. Setting endpoint traffic to zero does not deallocate the managed instance. Delete the endpoint when live demonstration is no longer required.

## Decommission outcome

The endpoint was deleted on 17 September 2026 after explicit authorization. Azure returned deletion exit code `0`, and two independent checks confirmed endpoint absence. The contained `Standard_D2as_v4` managed compute was removed, stopping further endpoint-compute accrual. The registered model, workspace, and resource group remain and may still incur separate storage or service charges where applicable.
