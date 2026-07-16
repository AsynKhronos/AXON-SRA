# Development status

## Summary

| Area | Status |
|---|---|
| Layered SR subsystem | Implemented in development baseline |
| Stable IDs | Implemented |
| Frame journal and frame model | Implemented |
| Immutable sealed frames | Implemented |
| Resource graph and provenance | Implemented |
| Scene routing | Implemented |
| Analysis scheduler | Implemented |
| Shader semantic cache | Implemented |
| Semantic bound-edge filtering | Validated |
| Indexed producer provenance | Validated |
| Position backward dataflow | Active development |
| Temporal input synthesis | Planned |
| DLSS / FSR / XeSS backend contract | Planned |
| End-user release | Not available |

## Milestone map

### Foundation — complete in the working baseline

The project was rebuilt as a layered subsystem with explicit interfaces and controlled DXVK hooks. The older monolithic approach is treated as reference telemetry rather than the target architecture.

### Phase 8.0 — shader semantic baseline

Validated target-shader discovery, position writers, exact position stores, and relevant constant-buffer bindings.

### Phase 8.1 — semantic bound-edge filtering

Reduced unnecessary resource-edge traversal and eliminated dropped handoffs in the validated run.

### Phase 8.2 — indexed producer provenance

Replaced repeated broad scans with indexed lookups.

Validation snapshot over 6,144 frames:

| Counter | Result |
|---|---:|
| Indexed provenance lookups | 2,183,445 |
| Indexed entries scanned | 437,284 |
| Average entries scanned per lookup | ~0.20 |
| Index rebuilds | 1 |
| Memory ambiguities | 0 |
| Dropped handoffs | 0 |
| Dropped journal events | 0 |

### Phase 9 — bounded position backward dataflow

Current work traces dependencies from exact `BuiltIn Position` stores through immutable SPIR-V. The implementation is explicitly bounded and records uniform-buffer, push-constant, and shader-input contributors where safely recoverable.

## What is not complete

The following items should not be presented as finished:

- universal motion-vector recovery;
- production temporal reconstruction;
- vendor SDK dispatch;
- automatic support for arbitrary D3D11 titles;
- stable installation packages;
- image-quality claims against native integrations.

## Status language

Use these labels consistently:

- **Implemented** — exists in the development baseline.
- **Validated** — exercised with measured diagnostics in at least one target workload.
- **Active development** — implementation is changing and not accepted as stable.
- **Planned** — architecture target without a completed implementation.
