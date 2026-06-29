# Sunnypilot NNLC Steering Models

Repository for custom neural-network lateral steering models for **sunnypilot**.

This repository is meant to keep trained NNLC model files separated from the main sunnypilot/openpilot source tree. The generated models are stored in the `models/` directory and can be copied into sunnypilot when testing Neural Network Lateral Control on supported cars.

## Purpose

The goal is to collect and version trained steering models used by sunnypilot's **Neural Network Lateral Control (NNLC)** system.

These models are trained from driving data and are used to predict the steering torque/feedforward behavior of a specific vehicle platform.

## Directory structure

```text
models/
```

The `models/` directory contains the trained `.json` model files.

Model names should match the car fingerprint used by sunnypilot/openpilot, for example:

```text
PSA_PEUGEOT_3008.json
```

When needed, a model can also include the EPS firmware in the filename, following sunnypilot's NNLC matching logic.

## Training tools

The training workflow is handled by this repository:

https://github.com/cristianku/openpilot-nnlc-tools

Use `openpilot-nnlc-tools` to process driving data and generate the final NNLC model file, then store the resulting model in this repository under `models/`.

## Notes

These models are experimental and should be tested carefully. A model trained for one car or EPS firmware may not behave correctly on another vehicle, even if the platform looks similar.
