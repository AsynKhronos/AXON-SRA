# Compatibility policy

## Target matrix

| Area | Status | Notes |
|---|---|---|
| D3D11 through DXVK | Primary target | Core project scope |
| Feature level 11_0 | Validation target | Persona 5 Royal |
| Feature level 11_1 | Validation target | Subnautica |
| D3D9 | Not a current acceptance target | May be evaluated separately later |
| Native D3D12 | Not the primary runtime target | Relevant only to experimental interop work |
| Vulkan-native games | Outside the current semantic-reconstruction scope | No D3D11 translation layer to analyze |
| FSR | Planned temporal backend | First open reference path |
| XeSS | Planned backend | Common-contract consumer |
| DLSS | Planned backend | Hardware and SDK requirements apply |
| FSR 4 / D3D12 interop | Experimental target | Subject to technical and licensing viability |

## Compatibility states

| State | Meaning |
|---|---|
| **Unverified** | No reproducible evidence |
| **Observed** | Frame capture and routing operate |
| **Analyzed** | Relevant semantic candidates are reproducible |
| **Temporal-ready** | Required temporal inputs pass validation |
| **Backend-validated** | A named backend passes defined tests |
| **Supported** | Documented configuration, limitations, and regression coverage |
| **Spatial-only** | Temporal requirements are not met safely |
| **Unsupported** | Known technical incompatibility or insufficient evidence |

## Reporting requirements

A compatibility report should include:

- game and executable;
- game version;
- D3D feature level;
- GPU and driver;
- operating system;
- DXVK-GPLALL build;
- AXON-SRA commit or release;
- overlays or proxy layers;
- test scene;
- test duration and frame count;
- structured AXON-SRA logs;
- selected route and execution mode;
- backend and quality mode;
- reproducibility notes.

## Compatibility principle

AXON-SRA prefers an honest `Spatial-only` or `Unsupported` result over a temporal path built from unreliable evidence.
