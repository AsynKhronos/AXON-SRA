# Contributing to AXON-SRA

AXON-SRA is an early graphics-research project with moving internal interfaces. Contributions must be narrow, reproducible, bounded, and evidence-based.

## High-value contributions

Current high-value work includes:

- minimized SPIR-V and resource-graph cases;
- D3D11 compatibility evidence;
- matrix, depth, motion, and jitter classification;
- bounded graph/dataflow algorithms;
- temporal input validation;
- backend-contract review;
- diagnostic and regression tooling;
- documentation corrections.

## Open an issue first

Open an issue before submitting:

- architecture changes;
- new DXVK hook points;
- ownership or threading changes;
- semantic-confidence changes;
- new backend integrations;
- profile-format changes;
- broad refactors.

Small documentation corrections may be submitted directly.

## Technical requirements

A change should explain:

1. the problem;
2. affected layer or phase;
3. why existing behavior is insufficient;
4. ownership and threading impact;
5. boundedness limits;
6. ambiguity and failure behavior;
7. validation method;
8. before/after diagnostics;
9. known limitations.

## Scope discipline

Do not combine unrelated work in one pull request.

A pull request should normally address one:

- semantic-analysis capability;
- reproducible bug;
- bounded performance problem;
- validation tool;
- backend-contract change;
- documentation topic.

## Runtime principles

- Keep DXVK hooks minimal and explicit.
- Prefer immutable analysis data.
- Bound journals, scans, graph traversal, dataflow, and pointer resolution.
- Preserve evidence and confidence provenance.
- Do not silently resolve ambiguity.
- Avoid game-specific raw resource IDs in core logic.
- Keep semantic discovery independent from one vendor backend.
- Follow the surrounding DXVK coding style.

## Validation information

Runtime changes should include:

- game and executable;
- game version;
- D3D feature level;
- GPU and driver;
- compiler and linker;
- DXVK-GPLALL baseline;
- AXON-SRA commit;
- scene and frame count;
- relevant counters;
- before/after result;
- active overlays or proxy layers.

## Licensing

By contributing, you agree that your original contribution may be distributed under the repository's applicable license terms.

Do not submit proprietary SDK files, restricted redistributables, or third-party code without clear licensing authority.
