# Semantic reconstruction

Semantic reconstruction converts low-level render observations into temporal roles.

## Evidence hierarchy

AXON-SRA should prefer stronger evidence over convenient heuristics.

From strongest to weakest:

1. exact shader dataflow and output semantics;
2. exact pass occurrence and resource provenance;
3. stable multi-frame value relationships;
4. binding and format constraints;
5. dimension and usage heuristics;
6. per-title profile knowledge.

A profile may reinforce evidence, but it should not erase contradictory runtime observations.

## Position and matrix analysis

The position path begins at exact `BuiltIn Position` stores and traces contributing values backward through immutable SPIR-V.

Target capabilities include:

- bounded interprocedural traversal;
- shader-input contributor classification;
- push-constant contributor classification;
- uniform-buffer binding resolution;
- byte-range and offset recovery;
- position-value observation;
- multi-frame constant classification;
- matrix reconstruction;
- current-versus-previous transform classification.

## Planned value classes

Observed position-related values may be classified as:

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

Classification should correlate values with:

- present size;
- render-target size;
- viewport size;
- shader identity;
- exact target draw;
- frame-to-frame changes.

## Camera and projection

The matrix resolver is intended to distinguish:

- object/world transforms;
- view transforms;
- projection transforms;
- view-projection combinations;
- current and previous variants;
- jittered and unjittered variants.

Classification requires structural evidence and temporal behavior. A four-by-four buffer region is not automatically a camera matrix.

## Depth

Depth reconstruction combines:

- depth-stencil binding history;
- shader reads;
- producer/consumer relationships;
- comparison or linearization behavior;
- scene-route proximity;
- dimensions and sample count;
- cross-frame stability.

The selected depth input must match the exact scene route used for reconstruction.

## Motion

Motion may come from:

1. a native motion-vector render target;
2. shader outputs derived from current and previous positions;
3. reconstructed position deltas;
4. a hybrid path combining camera motion with depth and object evidence.

The classifier must distinguish camera-only motion from full per-pixel motion.

## Jitter

Jitter detection is intended to correlate:

- projection terms;
- viewport and render resolution;
- recurring subpixel sequences;
- current and previous frame state;
- target draw occurrence.

Jitter must be normalized into the coordinate convention expected by the selected backend.

## History, exposure and reactive evidence

History analysis uses inter-frame provenance and resource recurrence.

Exposure and reactive/disocclusion evidence may derive from:

- shader semantics;
- post-process pass relationships;
- luminance or adaptation resources;
- transparency/material behavior;
- backend-specific synthesis rules.

These signals remain optional or backend-dependent until validated.

## Confidence model

Each semantic result should record:

- role;
- source;
- exact frame/pass/binding context;
- supporting observations;
- conflicting observations;
- completeness;
- confidence;
- bounds reached;
- profile influence.

Confidence is a decision input, not a cosmetic score.
