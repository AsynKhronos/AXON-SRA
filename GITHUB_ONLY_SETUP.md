# Final GitHub-only repository setup

This package intentionally does **not** contain:

- GitHub Pages;
- MkDocs;
- a documentation deployment workflow;
- a separate website;
- a custom domain.

All content is rendered directly by GitHub through `README.md`, Markdown documents, Mermaid diagrams, issue forms, and repository metadata.

## About section

Set:

**Description**

```text
Experimental semantic render-analysis framework for DXVK that reconstructs temporal inputs from D3D11 workloads.
```

Leave the **Website** field empty.

## Topics

Recommended:

```text
dxvk
vulkan
directx11
d3d11
shader-analysis
spirv
dxbc
render-graph
temporal-upscaling
graphics-programming
translation-layer
cplusplus
```

Do not add `dlss`, `fsr`, or `xess` until actual backend integration exists.

## Repository features

Recommended:

- Issues: enabled
- Discussions: enabled
- Projects: optional
- Wiki: disabled
- GitHub Pages: disabled
- Sponsorships: disabled unless deliberately configured

## Branches

The current default branch is `Developing`.

A conventional structure can be introduced later:

```text
main        canonical public baseline
develop     integration work
feature/*   isolated development
```

Do not rename branches until the source baseline and references are updated consistently.

## Labels

Recommended:

```text
bug
compatibility
proposal
documentation
architecture
semantic-analysis
resource-graph
shader-analysis
validation
dependencies
blocked
needs-evidence
```

## Suggested commit

```text
docs: establish professional GitHub repository presentation
```
