# Validation model

AXON-SRA validation is evidence-based. Launch success is not enough.

## Primary workloads

### Persona 5 Royal

- API path: D3D11
- feature level: 11_0
- role: primary integration and regression workload

### Subnautica

- API path: D3D11
- feature level: 11_1
- role: secondary engine and workload-diversity target

### D3D9

D3D9 is outside the current acceptance criteria.

## Validation layers

### 1. Observation integrity

Verify:

- frame count;
- journal capacity;
- dropped events;
- sealed-frame handoff;
- dropped handoffs;
- state interning;
- stable IDs.

### 2. Routing integrity

Verify:

- present-root selection;
- root-writer pass;
- route stability;
- exact target-draw occurrence;
- exclusion of UI and unrelated off-screen work.

### 3. Semantic integrity

Verify:

- exact shader and binding context;
- position dataflow completeness;
- constant-buffer range resolution;
- matrix and value classification;
- depth/motion/jitter evidence;
- ambiguity and bound counters.

### 4. Input-contract integrity

Verify:

- current and previous frame pairing;
- dimensions;
- coordinate conventions;
- motion scale and direction;
- jitter units;
- resource lifetime and layout;
- reset/history behavior.

### 5. Backend integrity

Verify:

- capability negotiation;
- backend acceptance or rejection;
- resource transitions;
- dispatch;
- fallback;
- resize;
- history reset;
- device-loss recovery.

### 6. Image-quality and performance validation

Measure:

- temporal stability;
- ghosting;
- disocclusion;
- transparency/reactive behavior;
- fine-detail reconstruction;
- camera motion;
- object motion;
- frame cost;
- memory cost;
- CPU scheduling cost.

## Evidence policy

Published claims should include:

1. title and executable;
2. API path and feature level;
3. AXON-SRA commit or release;
4. DXVK-GPLALL baseline;
5. GPU and driver;
6. compiler and linker;
7. scene and duration;
8. frame count;
9. relevant counters;
10. exact acceptance criterion;
11. known limitations.

Screenshots without logs are insufficient for semantic-validation claims.

## Support threshold

A title becomes supported only after:

- repeatable route selection;
- stable semantic inputs;
- bounded analysis;
- no unexplained dropped work;
- reproducible backend behavior;
- documented configuration;
- known limitations;
- regression coverage.
