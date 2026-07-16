# Contributing to AXON-SRA

AXON-SRA is an early research project with moving internal interfaces. Contributions must be narrow, reproducible, and evidence-based.

## Before opening a pull request

Open an issue first for:

- architectural changes;
- new DXVK hook points;
- changes to ownership or threading;
- changes to semantic confidence logic;
- new reconstruction backends;
- broad refactors.

Small documentation corrections do not require prior discussion.

## Development expectations

A technical change should include:

1. a precise problem statement;
2. the affected AXON-SRA phase or component;
3. why existing behavior is insufficient;
4. boundedness and ownership implications;
5. validation steps;
6. before/after diagnostics;
7. known failure cases.

## Scope discipline

Do not combine unrelated work in one pull request.

A pull request should normally address one of:

- one semantic-analysis capability;
- one reproducible bug;
- one validation tool;
- one documentation topic;
- one bounded performance issue.

## Validation

For runtime changes, include:

- game and executable;
- D3D feature level;
- GPU and driver;
- compiler and linker versions;
- DXVK-GPLALL baseline;
- AXON-SRA commit;
- frame count;
- relevant `[SR]` counters;
- regression comparison.

Persona 5 Royal and Subnautica are the current primary validation workloads. D3D9 is not a current acceptance criterion.

## Code principles

- Keep DXVK hooks minimal and explicit.
- Prefer immutable analysis data.
- Bound journals, scans, graph traversal, and shader dataflow.
- Preserve evidence and confidence provenance.
- Do not silently resolve ambiguity.
- Avoid game-specific resource IDs in core logic.
- Follow the surrounding DXVK coding style.

## Commit and pull-request quality

Use descriptive commits. Avoid generic messages such as `fix`, `update`, or `changes`.

The pull-request description must explain what changed, why it changed, how it was validated, and what remains unresolved.

## Licensing

By contributing, you agree that your contribution may be distributed under the repository's MIT License.
