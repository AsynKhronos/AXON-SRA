# Security policy

## Supported versions

AXON-SRA has not reached a stable public release. Only the current public development baseline is considered for security review.

## Reporting a vulnerability

Do not open a public issue for a vulnerability involving:

- code execution;
- unsafe DLL loading;
- path traversal;
- privilege abuse;
- malicious profile or configuration parsing;
- untrusted shader-analysis memory safety;
- release-package tampering;
- SDK or interop boundary abuse.

Use GitHub private vulnerability reporting when available. If private reporting is unavailable, contact the maintainer through the GitHub profile before publishing technical details.

Include:

- affected commit or release;
- operating system;
- reproduction steps;
- expected and observed behavior;
- impact assessment;
- proof of concept when safe;
- suggested mitigation when known.

## Normal issue scope

General crashes, compatibility problems, image-quality defects, and performance regressions should use the standard issue templates.
