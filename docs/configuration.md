# Configuration model

The public configuration ABI is not yet stable. This document describes the intended control surface.

## Target controls

The final runtime should expose:

- global enable/disable;
- backend selection;
- execution-mode policy;
- quality mode;
- input/output resolution policy;
- sharpening;
- semantic-profile selection;
- confidence thresholds;
- diagnostic logging;
- overlay/debug visualization;
- history reset;
- per-title overrides.

## Proposed conceptual model

```ini
# Illustrative only. Names and values are not yet stable.

axon.enable = true
axon.backend = auto
axon.mode = auto
axon.quality = quality
axon.profile = auto
axon.diagnostics = normal
axon.overlay = false
```

Potential backend values:

```text
auto
fsr
xess
dlss
fsr4-interop
spatial
native
```

Potential mode values:

```text
auto
native-temporal
hybrid-temporal
spatial
```

## Policy

Configuration may restrict a decision, but it must not force a backend to consume invalid temporal inputs.

For example:

- requesting DLSS does not bypass missing-input checks;
- requesting native-temporal does not convert ambiguous motion into valid motion;
- a profile cannot override contradictory runtime evidence silently.

## Profiles

A semantic profile may contain:

- title and executable identity;
- version constraints;
- route fingerprints;
- shader/binding fingerprints;
- confidence adjustments;
- backend restrictions;
- known fallback policy;
- validation metadata.

Profile formats should be versioned before public release.
