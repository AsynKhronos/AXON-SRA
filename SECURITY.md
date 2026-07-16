# Security policy

## Supported versions

AXON-SRA has not reached a stable release. Only the current development baseline is considered for security review.

## Reporting a vulnerability

Do not open a public issue for a vulnerability that could enable code execution, unsafe DLL loading, privilege abuse, or malicious shader/input handling.

Use GitHub's private vulnerability-reporting feature when it is enabled. If private reporting is unavailable, contact the maintainer through the GitHub profile before disclosing technical details publicly.

Include:

- affected commit or build;
- operating system;
- reproduction steps;
- expected and observed behavior;
- impact assessment;
- proof of concept when safe.

## Scope

Security reports may include:

- unsafe file or profile parsing;
- path traversal;
- untrusted shader-analysis failures;
- integer overflow leading to memory unsafety;
- race conditions affecting memory safety;
- unsafe DLL or backend discovery;
- release-package tampering.

General crashes, compatibility problems, and performance regressions should use the normal issue templates.
