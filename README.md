# AXON-SRA (Semantic Render Analysis)

**AXON-SRA** ist eine autonome, semantische Render-Rekonstruktions-Layer für DXVK, die darauf spezialisiert ist, hochwertige temporale Inputs (Depth, Motion, Camera Semantics) aus nativen D3D11-Rendering-Pipelines zu extrahieren, ohne auf manuelle Game-Profile angewiesen zu sein.

## Überblick
Moderne Upscaling-Techniken (DLSS, FSR, XeSS) sind auf präzise semantische Daten angewiesen, die viele Legacy-Titel nicht nativ bereitstellen. **AXON-SRA** schließt diese Lücke, indem es die Grafik-Pipeline zur Laufzeit beobachtet, Shader-Datenflüsse mathematisch analysiert und die benötigten Informationen autonom rekonstruiert.

Das System arbeitet als **asynchrone Middleware** innerhalb des DXVK-Stacks. Es ist darauf ausgelegt, die Render-Performance nicht zu beeinträchtigen, während es im Hintergrund die "Wahrheit" über die Szene beweist.

## Kern-Features
* **Autonome Discovery:** Keine manuelle Konfiguration von Buffer-Offsets oder Shader-Hashes. AXON-SRA identifiziert die Main Scene, Depth und Camera-Transformations durch mathematische Beweisführung.
* **Asynchrone Analyse:** Die rechenintensive semantische Untersuchung findet entkoppelt vom Render-Pfad statt. Kein Stutter, kein Present-Stall.
* **Consumer-Local Overlay:** Anstatt globale Game-Ressourcen zu verändern, injiziert AXON-SRA Daten gezielt dort, wo sie gebraucht werden (z.B. Jitter-Injektion via Binding Overlay), wodurch UI, Schatten und Reflexionen unangetastet bleiben.
* **SPIR-V Dataflow Tracking:** Analyse des Shader-Outputs direkt im Byte-Code, um Position-Daten und Projektionsmatrizen mit absoluter Präzision zu lokalisieren.

## Architektur
AXON-SRA basiert auf dem Prinzip: **Beobachten statt Raten.**
Durch die Integration direkt in den `DxvkContext` agiert das System als "Nervensystem" der Engine. Es versteht die Topologie des Frames und garantiert, dass die an den Upscaler übermittelten Daten physikalisch plausibel sind.

## Tech-Stack
* **Sprache:** C++23 (Clang/LLVM)
* **Basis:** DXVK-GPLALL
* **Threading:** OneTBB & Lock-Free Queues
* **Mathematik:** Strict-FP compliant Resolver-Kern

## Status
Das Projekt befindet sich in der aktiven Entwicklungsphase (Phase 0).
