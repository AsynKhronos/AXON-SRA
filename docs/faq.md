# FAQ

## Is AXON-SRA an upscaler?

Not yet. It is currently analysis and reconstruction infrastructure intended to identify and synthesize the inputs an upscaler would require.

## Does it already provide DLSS, FSR, or XeSS in every D3D11 game?

No. Vendor-neutral backend integration is a roadmap target. The project does not currently claim universal production integration.

## Why integrate inside DXVK?

DXVK sees translated shaders, resource bindings, view relationships, passes, and presentation flow. This is a stronger observation point than a late post-processing injector for reconstructing render semantics.

## Why not hard-code resource IDs?

Resource IDs are transient and may vary between runs. AXON-SRA targets semantic relationships and repeatable evidence.

## Why is analysis bounded?

Unbounded graph and shader traversal is unacceptable inside a graphics runtime. Journal capacity, lookup cost, node count, and recursion depth require explicit limits.

## Is this an official DXVK project?

No. AXON-SRA is independent and is not endorsed by DXVK or its maintainers.

## Why are there no end-user downloads?

The public repository is being established before the implementation baseline is published as a reproducible release.
