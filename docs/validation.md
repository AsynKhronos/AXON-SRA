# Validation

AXON-SRA validation is currently engineering-focused. The purpose is to verify boundedness, provenance correctness, event retention, and semantic evidence quality before any reconstruction backend is introduced.

## Primary workloads

### Persona 5 Royal

- API path: D3D11
- feature level: 11_0
- role: primary integration and regression workload

### Subnautica

- API path: D3D11
- feature level: 11_1
- role: secondary engine and workload diversity

### D3D9

D3D9 is not part of the current acceptance criteria. Portal 2 may be used later as an optional compatibility exercise, but it does not gate current milestones.

## Phase 8.2 diagnostic snapshot

A 6,144-frame run recorded:

| Metric | Value |
|---|---:|
| Frames analyzed | 6,144 |
| Memory-index lookups | 2,183,445 |
| Memory-index entries scanned | 437,284 |
| Memory-index rebuilds | 1 |
| Memory ambiguities | 0 |
| Dropped handoffs | 0 |
| Dropped journal events | 0 |

Derived scan density:

```text
437,284 / 2,183,445 ≈ 0.2003 entries per lookup
```

## Interpretation

This snapshot supports the following limited conclusions:

- indexed provenance remained bounded in the tested run;
- the tested run reported no provenance ambiguity;
- no scheduled handoffs were dropped;
- the frame journal reported no dropped events.

It does **not** demonstrate:

- universal correctness across games;
- final frame-time overhead;
- reconstruction quality;
- motion-vector accuracy;
- production stability.

## Evidence policy

Published claims should include:

1. title and API path;
2. build or commit identifier;
3. frame count;
4. relevant counters;
5. exact acceptance criterion;
6. known limitations.

Screenshots without logs are insufficient for semantic-analysis validation.
