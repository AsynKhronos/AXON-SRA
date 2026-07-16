# Semantic analysis

Shader analysis is the bridge between observed resource flow and actual rendering meaning.

## Why shader semantics matter

Resource dimensions and bind flags are useful but insufficient. Two textures with identical dimensions may represent color, depth, velocity, history, bloom, UI, or an intermediate post-process result.

Shader behavior provides stronger evidence:

- which resources are sampled;
- which outputs are written;
- whether position is generated;
- which constant-buffer ranges contribute to position;
- whether values recur across frames;
- whether a resource participates in a feedback or history relationship.

## Shader semantic cache

`sr_shader_semantic_cache` stores analysis results keyed by stable shader identity.

The cache currently tracks evidence including:

- target-shader readiness;
- position writers;
- exact position stores;
- constant-buffer bindings used by relevant stores;
- semantic observations required by scheduled analysis.

Caching prevents immutable SPIR-V from being rescanned on every draw.

## Phase 8 findings

The validated Phase 8 baseline identified:

- four target shaders ready for deeper analysis;
- two position writers;
- two exact `BuiltIn Position` stores;
- two used constant-buffer bindings.

Phase 8.1 added semantic bound-edge filtering. Phase 8.2 replaced broad producer scans with indexed provenance lookups.

## Phase 9: bounded backward dataflow

Phase 9 starts at an exact `BuiltIn Position` store and walks backward through immutable SPIR-V.

The analysis recognizes direct and structure-member position outputs and tracks contributors such as:

- shader inputs;
- uniform-buffer loads;
- push constants;
- composite operations;
- copies, selections, and phi nodes where resolution remains safe;
- pointer chains and byte offsets when statically recoverable.

## Bounded execution

The implementation uses explicit limits rather than unbounded graph traversal:

| Limit | Purpose |
|---|---|
| Trace-node bound | Prevent pathological shader graphs from consuming unbounded work |
| Trace-depth bound | Prevent excessive recursive dependency chains |
| Pointer-depth bound | Prevent complex pointer resolution from escaping the analysis budget |

When limits or ambiguity are encountered, the result is marked incomplete or imprecise instead of being promoted to a false semantic certainty.

## Next semantic steps

After position contributors are stable, the next work is expected to classify:

- camera and projection transforms;
- current and previous transforms;
- jitter pairs;
- depth production and consumption;
- motion-related outputs;
- history feedback;
- presentation and final-composite roles.

These features remain research targets, not completed public guarantees.
