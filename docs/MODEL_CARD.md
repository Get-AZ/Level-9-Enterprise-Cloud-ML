# Model Card

## Model

- Name: `Level_8_Production_Classifier`
- Registered version: `2`
- Serving format: MLflow model with scikit-learn pipeline
- Output: binary class prediction

## Deployment evidence

The packaged model loaded successfully in Azure ML. One certified record produced class `0` locally and `[0]` through both direct and routed Azure invocation. The serving log recorded HTTP 200.

## Intended use

Controlled demonstration of governed model deployment and real-time inference through Azure Machine Learning.

## Limitations

- No stored MLflow signature was present.
- One validation record does not establish population-level performance.
- Input/output telemetry collectors were not operational.
- Application Insights was disabled.
- Load, latency, availability, failover, and autoscaling were not certified.

The earlier Level 8 project remains the source for model-training and held-out evaluation evidence.
