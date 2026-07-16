# AXON-SRA Documentation

AXON-SRA is documented entirely through GitHub-native Markdown and Mermaid. There is no separate documentation website.

## Product and architecture

| Document | Purpose |
|---|---|
| [Project vision](vision.md) | Final product objective, intended users, and success criteria |
| [System architecture](architecture.md) | Layering, ownership, routing, reconstruction, and backend boundaries |
| [Runtime pipeline](runtime-pipeline.md) | End-to-end processing from D3D11 commands to Vulkan presentation |
| [Semantic reconstruction](semantic-reconstruction.md) | Depth, matrix, camera, motion, jitter, history, and confidence analysis |
| [Frame and resource model](frame-resource-model.md) | Frame lifecycle, stable identity, resource provenance, and sealed analysis data |
| [Backend interface](backend-interface.md) | Common temporal input contract and backend dispatch model |
| [Execution modes](execution-modes.md) | Native temporal, hybrid temporal, and spatial fallback behavior |

## Development and release

| Document | Purpose |
|---|---|
| [Development status](status.md) | Public state, current focus, completed foundations, and incomplete capabilities |
| [Roadmap to v1.0](roadmap.md) | Phased route from analysis infrastructure to public release |
| [Validation model](validation.md) | Evidence requirements, counters, workloads, and acceptance rules |
| [Compatibility policy](compatibility.md) | What “supported” means and how reports are evaluated |
| [Configuration model](configuration.md) | Planned backend, quality, profile, and diagnostic controls |
| [Release model](releases.md) | Research snapshots, experimental releases, previews, and stable releases |
| [FAQ](faq.md) | Scope, limitations, backend questions, and project independence |

All diagrams are rendered directly by GitHub.
