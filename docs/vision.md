# Project vision

## Purpose

AXON-SRA exists to solve the missing-integration problem between legacy D3D11 rendering workloads and modern temporal super-resolution systems.

A native temporal integration normally knows:

- which render target contains the main scene;
- which texture is depth;
- where motion vectors are written;
- how the camera and projection change;
- which jitter sequence is active;
- which resources represent history, exposure, reactive regions, or disocclusion.

DXVK can observe translated shaders, views, resources, bindings, draw calls, barriers, passes, and presentation flow—but those observations do not arrive with semantic labels.

AXON-SRA is designed to reconstruct those labels.

## Final objective

The final runtime should autonomously:

1. identify the present-bound main scene route;
2. isolate the exact pass occurrence that contributes to the final image;
3. bind the relevant shader set, resources, views, and constant-buffer state;
4. reconstruct depth, camera, projection, motion, jitter, exposure, and history semantics;
5. synthesize a backend-neutral temporal input set;
6. assign confidence, completeness, and capability classifications;
7. select a native-temporal, hybrid-temporal, or spatial execution mode;
8. dispatch to FSR, XeSS, DLSS, or an experimental FSR 4 / D3D12 interop path;
9. present through Vulkan without requiring game-source modification.

## Product definition

AXON-SRA is not merely an image-scaling pass.

Its core product is the **semantic reconstruction layer** that temporal backends normally receive from a native engine integration.

```text
Render observations
        ↓
Semantic evidence
        ↓
Validated temporal inputs
        ↓
Backend-neutral dispatch
        ↓
Super-resolution execution
```

## Intended user experience

The final user-facing workflow is intended to be:

1. install the AXON-enabled DXVK runtime;
2. select `auto` or a preferred backend;
3. launch a compatible D3D11 title;
4. allow AXON-SRA to identify and validate the required rendering semantics;
5. use the best qualified execution mode;
6. expose a clear diagnostic reason when a backend is rejected or downgraded.

## Success criteria

A release is successful only when it can demonstrate:

- repeatable main-scene routing;
- stable semantic classification across runs;
- bounded runtime and memory cost;
- explicit handling of ambiguity;
- correct backend capability negotiation;
- reproducible image-quality and performance validation;
- no silent use of invalid temporal inputs;
- documented compatibility per title and configuration.

## Boundaries

Some D3D11 titles may not expose enough information for reliable temporal reconstruction. AXON-SRA must remain useful in those cases by falling back safely rather than pretending that incomplete data is authoritative.
