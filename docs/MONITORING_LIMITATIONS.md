# Monitoring Limitations

## Observed state

Real-time scoring was operational. The container logs reported that `inputs_collector` and `outputs_collector` were not defined. Startup logs stated that data collection was not enabled, and Application Insights was disabled.

## Consequence

The project cannot claim automatic model-input capture, model-output capture, live drift observations, production alerting, or complete service telemetry.

## Required remediation

1. Enable supported Azure ML data collection configuration.
2. Verify collector initialization in the serving container.
3. Confirm authorized records arrive in the intended store.
4. Define privacy, access, and retention controls.
5. Configure service-health and inference-error alerts.
6. Validate drift analysis with authorized production observations.
7. Reissue certification only after evidence passes.
