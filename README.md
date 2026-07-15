# AXON-SRA (Semantic Render Analysis)

![Build Status](https://img.shields.io/badge/status-development-yellow)
![C++ Standard](https://img.shields.io/badge/c%2B%2B-23-blue)
![License](https://img.shields.io/badge/license-MIT-green)

**AXON-SRA** is the definitive, autonomous reconstruction layer for D3D11 rendering pipelines. By integrating deeply into the DXVK stack, AXON-SRA eliminates the need for game-specific profiles, manual shader-hacking, or complex configuration files. It observes, proves, and synthesizes the rendering state, providing modern temporal upscaling backends (DLSS, FSR, XeSS) with native-quality data.

---

## 🚀 The Philosophy: "Don't Guess. Prove."
Traditional upscaling mods rely on heuristic guessing and hardcoded memory offsets. **AXON-SRA takes a different approach.** It operates as a first-class citizen of the rendering pipeline:
1. **Observe:** Captures the frame flow via non-intrusive, asynchronous context-level observation.
2. **Prove:** Mathematically reconstructs scene topology using SPIR-V dataflow analysis.
3. **Synthesize:** Provides a deterministic `SrFrameInputs` contract to any temporal backend.

---

## ⚙️ Core Technical Pillars

* **Autonomous Semantic Discovery:** No more broken profiles after game updates. AXON-SRA learns the scene structure on-the-fly.
* **Asynchronous Analysis:** Deep render analysis is decoupled from the render loop via `AnalysisScheduler`, ensuring zero frame-pacing impact.
* **Precision Binding Overlay:** Uses consumer-local binding overrides, ensuring injected jitter and camera changes never contaminate UI or non-main-scene geometry.
* **SPIR-V Dataflow Tracking:** Traces `BuiltIn Position` outputs through shader dataflow to achieve sub-byte-accurate matrix identification.

---

## 🛠 Prerequisites & Build
* **Toolchain:** MSYS2 CLANG64 (Clang/LLVM 22.1.8+)
* **Build System:** Meson + Ninja
* **Language:** C++23

*(Build instructions will follow as the project matures.)*

---

## ⚖️ License
Distributed under the MIT License. See `LICENSE` for more information.

---

## 🎖 Credits
Built by **[AsynKhronos](https://github.com/AsynKhronos)**.
*Designed as a tribute to the Khronos Group’s contributions to graphics standardization.*
