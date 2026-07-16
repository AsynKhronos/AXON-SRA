# Release model

## Research snapshots

Purpose:

- share architecture and diagnostics;
- validate specific phases;
- collect expert feedback.

Characteristics:

- no compatibility guarantee;
- interfaces may change immediately;
- source-first;
- explicit commit identity.

## Experimental releases

Purpose:

- publish reproducible runtime builds;
- validate one or more backends in controlled titles.

Requirements:

- build instructions;
- checksums;
- known limitations;
- compatibility list;
- structured logs;
- rollback instructions.

## Preview releases

Purpose:

- stabilize configuration, profiles, packaging, and backend behavior before v1.0.

Requirements:

- versioned configuration;
- versioned profile format;
- regression suite;
- upgrade notes;
- release integrity verification.

## Stable releases

A stable release requires:

- defined support policy;
- reproducible source build;
- versioned binary package;
- documented compatible titles;
- validated fallback behavior;
- licensing and redistribution review;
- integrity verification;
- changelog and migration guidance.

## Release artifacts

Planned artifacts may include:

- DXVK runtime DLLs;
- configuration template;
- semantic profiles;
- symbol/debug package;
- source archive;
- checksums;
- release notes;
- compatibility manifest.
