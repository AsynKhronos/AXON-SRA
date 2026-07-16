# Compatibility

## Current target matrix

| Area | Status | Notes |
|---|---|---|
| D3D11 through DXVK | Primary target | Current acceptance path |
| Feature level 11_0 | Validated workload | Persona 5 Royal |
| Feature level 11_1 | Validated workload | Subnautica |
| D3D9 | Out of scope for current milestones | May be revisited later |
| Native D3D12 | Not a current target | Outside the present DXVK-D3D11 scope |
| Vulkan-native games | Not a current target | No D3D11 translation semantics to reconstruct |
| Vendor upscaler SDKs | Planned backend work | No production integration claim |

## Compatibility definition

A title is not considered supported merely because it launches.

Meaningful validation requires:

- stable frame capture;
- no journal overflow;
- no dropped analysis handoffs;
- bounded provenance cost;
- repeatable scene routing;
- identifiable semantic candidates;
- reproducible logs across runs.

## Reporting a title

Use the compatibility-report issue template and include:

- game and executable;
- D3D feature level;
- GPU and driver;
- DXVK-GPLALL build identifier;
- AXON-SRA phase or commit;
- relevant logs;
- reproducible scene and duration;
- whether overlays, ReShade, or other proxy layers were active.
