# FAQ

## Is AXON-SRA an upscaler?

The final system includes super-resolution backend execution, but its defining component is the semantic reconstruction layer that produces validated temporal inputs.

## Does it already add DLSS, FSR, or XeSS to every D3D11 game?

No. Those backends are final architecture targets. Universal compatibility is not claimed.

## Why integrate inside DXVK?

DXVK can observe translated shaders, bindings, resources, passes, barriers, and presentation flow. This provides a stronger semantic observation point than a late full-frame post-processing injector.

## Does AXON-SRA modify the game?

The default objective is to operate without modifying the original game source code.

## What happens when motion or depth cannot be reconstructed?

The classifier should downgrade to hybrid temporal, spatial fallback, native-resolution pass-through, or unsupported status. It must not fabricate authoritative data.

## Why not hard-code resource IDs?

Resource handles are transient and may differ across frames, runs, versions, and titles. AXON-SRA targets stable semantic relationships and repeatable evidence.

## What is FSR 4 / D3D12 interop?

It is an experimental future path that may use DXVK's D3D11-on-12 and Vulkan interop surfaces. It is not a current production feature.

## Is AXON-SRA an official DXVK or Khronos project?

No. It is independent and is not endorsed by DXVK, Khronos, Microsoft, NVIDIA, AMD, Intel, or any game publisher.

## Why are there no downloads yet?

The source tree, build process, licensing notices, and release packaging are being prepared before public publication.

## Will every title be supported?

No. Some engines may not expose enough recoverable semantic evidence for safe temporal reconstruction.
