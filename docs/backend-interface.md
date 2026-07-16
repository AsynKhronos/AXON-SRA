# Backend interface

The backend interface separates semantic reconstruction from vendor-specific execution.

## Contract goals

The common contract should:

- describe required and optional inputs;
- expose formats, dimensions, layouts, and coordinate conventions;
- carry current and previous frame relationships;
- include confidence and provenance;
- describe execution mode;
- expose backend capabilities and rejection reasons;
- avoid leaking AXON-SRA internal graph structures into backend code.

## Candidate input contract

```text
AxonSrInputs
├── currentColor
├── outputTarget
├── depth
├── motion
├── jitter
├── exposure
├── reactiveMask
├── disocclusionMask
├── currentTransforms
├── previousTransforms
├── inputDimensions
├── outputDimensions
├── frameIndex
├── resetHistory
├── executionMode
└── confidence / provenance
```

The concrete C++ ABI is not yet stable.

## Capability negotiation

Each backend should declare:

- supported GPU/vendor path;
- required API or SDK;
- required temporal inputs;
- accepted formats;
- quality modes;
- dynamic-resolution support;
- reset/history requirements;
- resource-state and queue requirements.

The classifier compares these requirements against the synthesized input set.

## Backend lifecycle

A backend implementation is expected to support:

1. capability query;
2. feature/context creation;
3. resize or reconfiguration;
4. dispatch;
5. history reset;
6. diagnostics;
7. teardown;
8. device-loss or failure recovery.

## FSR

FSR is intended to serve as the first open temporal reference path behind the common contract.

The integration should validate:

- input conventions;
- motion scale;
- jitter units;
- exposure behavior;
- reactive/disocclusion inputs;
- quality modes;
- frame cost.

## XeSS

XeSS should consume the same normalized input contract while retaining backend-specific capability checks and resource handling.

## DLSS

DLSS requires NVIDIA hardware and backend-specific SDK integration. The common contract must provide the required temporal inputs without coupling semantic discovery to DLSS-specific types.

## FSR 4 / D3D12 interop

The experimental FSR 4 path may use DXVK's D3D11-on-12 / Vulkan interop surfaces where technically viable.

The interop layer may need access to:

- `VkInstance`
- `VkPhysicalDevice`
- `VkDevice`
- `VkQueue`
- `VkImage`
- `VkImageLayout`
- resource acquire/release synchronization

This path remains experimental and subject to API, SDK, licensing, and distribution constraints.

## Backend rejection

A backend must return a structured reason when it cannot run.

Examples:

- unsupported hardware;
- missing SDK/runtime;
- missing required semantic input;
- confidence below threshold;
- incompatible format;
- unsupported dimensions;
- synchronization requirement not met;
- profile policy restriction.

The runtime may then choose another backend or a safer execution mode.
