# Architecture

## Serving path

`Authenticated client -> Azure ML endpoint -> 100 percent traffic route -> production-v2 -> MLflow scoring server -> scikit-learn pipeline -> binary prediction`

The endpoint provides the stable scoring URI. The deployment owns the serving container and compute. Azure mounts registered model `Level_8_Production_Classifier:2`. The MLflow score script converts the `input_data` request into a pandas DataFrame and invokes the packaged pipeline.

This is the certified historical serving architecture. The endpoint, deployment, and managed compute were subsequently deleted in R5. Recreating the serving path requires a new controlled deployment; the preserved registered model remains available for that process.

## Verified separation of concerns

- The model registry preserves artifact identity.
- The deployment defines model, environment, instance type, and instance count.
- The endpoint defines authentication and traffic routing.
- Direct invocation validates a deployment independently of endpoint traffic.
- Routed invocation validates the normal production path.
- Certification records preserve the observed state and limitations.
