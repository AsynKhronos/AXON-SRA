# Roadmap

The roadmap is evidence-driven. A milestone advances only when its diagnostics are stable enough to support the next layer.

## Completed foundation

- [x] Layered SR subsystem with explicit interfaces
- [x] Controlled DXVK ownership and observation hooks
- [x] Stable render-entity identifiers
- [x] Bounded frame journal
- [x] Normalized frame model
- [x] Immutable sealed-frame snapshots
- [x] Resource graph and producer provenance
- [x] Scene routing
- [x] Analysis scheduling
- [x] Shader semantic cache
- [x] Semantic bound-edge filtering
- [x] Indexed producer provenance

## Active milestone

### Position-source reconstruction

- [x] Identify position writers
- [x] Identify exact `BuiltIn Position` stores
- [ ] Complete bounded backward SPIR-V dataflow
- [ ] Classify contributing shader inputs
- [ ] Classify push-constant contributors
- [ ] Resolve uniform-buffer ranges and byte offsets
- [ ] Validate dynamic and ambiguous pointer paths
- [ ] Establish regression counters across target titles

## Near-term semantic milestones

- [ ] Camera and projection transform classification
- [ ] Current-versus-previous transform detection
- [ ] Jitter-pair inference
- [ ] Depth producer and consumer classification
- [ ] History and feedback-role detection
- [ ] Motion-related output classification
- [ ] Presentation and final-composite identification
- [ ] Confidence calibration across multiple engines

## Reconstruction milestones

- [ ] Define a backend-neutral temporal input contract
- [ ] Build temporal input synthesis and validation views
- [ ] Introduce a reference reconstruction backend
- [ ] Add backend capability negotiation
- [ ] Evaluate DLSS, FSR, XeSS, and custom backends independently
- [ ] Add fallback behavior when required inputs are absent
- [ ] Measure image stability, ghosting, disocclusion, and frame cost

## Release-hardening milestones

- [ ] Publish reproducible source baseline
- [ ] Publish authoritative build instructions
- [ ] Add CI builds and static analysis
- [ ] Establish compatibility-report format
- [ ] Add versioned semantic-profile format
- [ ] Publish first experimental binary release
- [ ] Define API and profile compatibility policy

## Non-goal

The roadmap does not promise that every D3D11 game can be integrated automatically. Some titles may not expose sufficient information for reliable temporal reconstruction.
