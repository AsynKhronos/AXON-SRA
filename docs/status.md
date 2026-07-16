# Development status

## Public repository status

The public repository currently contains the project vision, architecture, validation model, policies, and branding assets.

The source tree and binary runtime are being cleaned and validated before publication.

No end-user build is currently available.

## Current engineering focus

The active work has progressed from frame/resource observation and position dataflow into position-related constant-buffer value analysis.

The current classification work is designed to correlate observed values with:

- present dimensions;
- render-target dimensions;
- viewport dimensions;
- shader identity;
- exact target-draw occurrence;
- multi-frame changes.

Target value classes include:

- `Constant`
- `ViewportWidth`
- `ViewportHeight`
- `HalfViewportWidth`
- `HalfViewportHeight`
- `InverseWidth`
- `InverseHeight`
- `AspectRatio`
- `ProjectionScale`
- `UnknownDynamic`

## Implemented or validated foundations

The working baseline includes development work covering:

- legacy authority audit and cleanup;
- SR ownership skeleton;
- canonical state interning;
- chronological frame journal;
- asynchronous frame sealing and bounded handoff;
- frame model and resource graph;
- present-bound scene routing;
- present-root and root-writer diagnostics;
- inter-frame ping-pong analysis;
- persistent and versioned producer provenance;
- shader semantic cache;
- semantic bound-edge filtering;
- indexed producer provenance;
- bounded `BuiltIn Position` backward dataflow;
- unresolved-dataflow diagnostics;
- interprocedural output-staging dataflow;
- position constant-buffer binding resolution;
- position-related value observation.

## Not yet complete

The following capabilities must not be presented as finished:

- reliable camera and projection classification across titles;
- current-versus-previous matrix resolution;
- general depth reconstruction;
- native motion-vector discovery across engines;
- synthesized per-pixel motion;
- jitter inference and normalization;
- temporal input synthesis;
- capability and confidence classifier;
- production FSR, XeSS, or DLSS dispatch;
- FSR 4 / D3D12 interop;
- universal D3D11 compatibility;
- release-ready binaries.

## Status vocabulary

Use these terms consistently:

| Label | Meaning |
|---|---|
| **Implemented** | Exists in the working development baseline |
| **Validated** | Exercised against defined evidence and acceptance criteria |
| **Active development** | Implementation is moving and not accepted as stable |
| **Planned** | Defined architectural target without a completed implementation |
| **Experimental** | Implemented for investigation but not supported as a release guarantee |
| **Released** | Published, versioned, documented, and covered by a compatibility policy |
