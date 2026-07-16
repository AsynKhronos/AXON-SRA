<p align="center">
  <img src="assets/axon-sra-logo.svg" width="120" alt="AXON-SRA logo">
</p>

<h1 align="center">AXON-SRA</h1>

<p align="center">
  Semantic Render Analysis and temporal reconstruction infrastructure
  for DXVK-based D3D11 workloads.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/status-experimental-orange">
  <img src="https://img.shields.io/badge/platform-DXVK-blue">
  <img src="https://img.shields.io/badge/API-D3D11%20%7C%20Vulkan-blueviolet">
  <img src="https://img.shields.io/badge/license-MIT-green">
</p>

> [!WARNING]
> AXON-SRA is under active development. It is not currently intended
> for production use, general game compatibility, or performance comparisons.

## Overview

AXON-SRA is an experimental framework for identifying and tracking
rendering semantics inside DXVK-translated D3D11 workloads.

Rather than relying exclusively on game-specific integrations, AXON-SRA
aims to reconstruct temporal rendering information by analyzing shader
behavior, resource relationships, frame history, and presentation flow.

The long-term objective is to provide stable inputs for interchangeable
temporal reconstruction and super-resolution backends.
