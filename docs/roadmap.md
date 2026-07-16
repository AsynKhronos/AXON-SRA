# Roadmap to v1.0

The roadmap is evidence-driven. A phase advances only when its diagnostics and failure behavior are stable enough to support the next layer.

## Block A — observation and provenance

### Phases 0–10

- [x] Legacy audit and authority cleanup
- [x] SR ownership skeleton
- [x] Canonical state interning
- [x] Chronological frame journal
- [x] Asynchronous frame sealing and bounded handoff
- [x] Frame model and resource graph
- [x] Present-bound scene routing
- [x] Present-root and root-writer diagnostics
- [x] Inter-frame ping-pong bridge
- [x] Persistent and versioned producer provenance
- [x] Shader semantic cache
- [x] Semantic bound-edge filtering
- [x] Indexed producer provenance
- [x] Bounded position backward dataflow
- [x] Unresolved-dataflow diagnostics
- [x] Interprocedural output-staging dataflow
- [x] Position constant-buffer binding resolution

## Block B — semantic reconstruction

### Phases 11–18

- [x] Position-related constant-buffer value observation
- [ ] Automatic position-constant classification
- [ ] Matrix reconstruction
- [ ] Matrix, camera, and projection classification
- [ ] Current-versus-previous transform detection
- [ ] Depth reconstruction
- [ ] Native motion-vector discovery
- [ ] Reconstructed or hybrid motion generation
- [ ] Jitter detection and normalization
- [ ] Camera-motion synthesis
- [ ] History and exposure classification
- [ ] Cross-title confidence calibration

## Block C — temporal SR infrastructure

### Phases 19–21

- [ ] Capability and confidence classifier
- [ ] Backend-neutral temporal input contract
- [ ] Temporal SR input synthesizer
- [ ] Native / Hybrid / Spatial execution-mode selection
- [ ] Backend lifecycle and capability negotiation
- [ ] Structured backend rejection and fallback reasons

## Block D — backend integration

### Phases 22–25

- [ ] FSR temporal backend
- [ ] XeSS backend
- [ ] DLSS backend
- [ ] Experimental FSR 4 / D3D12 interop path
- [ ] Backend-specific quality-mode validation
- [ ] History reset, resize, and device-loss handling
- [ ] Cross-backend image-quality and frame-cost comparison

## Block E — compatibility and release

### Phase 26

- [ ] Multi-engine D3D11 compatibility hardening
- [ ] Runtime performance budget and boundedness validation
- [ ] Configuration and profile format
- [ ] Diagnostic overlay and structured logs
- [ ] Reproducible source build
- [ ] Signed or verifiable binary packaging
- [ ] Versioned experimental release
- [ ] Compatibility database
- [ ] Public release documentation
- [ ] v1.0 release criteria and support policy

## v1.0 acceptance criteria

A stable release requires:

- reproducible builds;
- bounded runtime analysis;
- no silent journal or handoff loss;
- explicit ambiguity behavior;
- at least one validated temporal backend;
- documented fallback behavior;
- per-title compatibility evidence;
- clear licensing and redistribution compliance;
- versioned configuration and profile formats;
- release artifacts with integrity verification.

## Non-promise

The roadmap does not guarantee automatic temporal reconstruction for every D3D11 title. Some engines may remain spatial-only or unsupported when the required semantic evidence cannot be recovered safely.
