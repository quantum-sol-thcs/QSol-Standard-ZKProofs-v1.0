Profiles Directory — QSol‑Standard‑ZKProofs‑v1.0
Normative Directory Overview
QSol LLC — Harmonic Systems Research Division

1. Purpose of Profiles
Profiles define protocol‑level specializations of the Kernel‑Constitutional Architecture.
A profile specifies:

the algebraic environment

the commitment scheme

the transcript rules

the mapping rules

the domain separation scheme

the determinism model

the CTS subset required for certification

Profiles allow the Standard to support:

PLONKish systems

STARK systems

IPA‑based systems

recursive systems (Nova‑style)

custom research systems

while preserving kernel purity, determinism, and interoperability.

2. Profile Structure
Each profile MUST include:

Profile Identity

Algebraic Environment

Commitment Scheme

Transcript Rules

Mapping Rules

Domain Separation Rules

Determinism Model

CTS Requirements

Security Considerations

Version Declaration

Profiles MUST be:

deterministic

canonical

kernel‑pure

self‑contained

versioned

Profiles MUST NOT:

modify kernel rules

weaken determinism

bypass transcript rules

bypass commitment rules

introduce off‑kernel computation

3. Profile Naming Convention
Profiles MUST follow the naming pattern:

Code
<family>-<field>-<commitment>
Examples:

plonkish-381-kzg

stark-fri-poseidon

ipa-pedersen

nova-ipa-poseidon

Custom profiles MUST follow the same pattern.

4. Profile Versioning
Profiles MUST follow the Standard version:

Adding a new profile → MINOR

Fixing formatting → PATCH

Changing semantics → MAJOR

Profiles MUST NOT be modified retroactively.

5. Profile Certification
Implementations MUST:

declare exactly one profile

include the profile in the CAB

pass all CTS tests required by the profile

follow all mapping rules defined by the profile

Auditors MUST verify:

profile correctness

profile determinism

profile‑specific mapping invariants

profile‑specific transcript rules

profile‑specific commitment rules

6. Directory Contents
This directory contains:

Code
profiles/
  README.md                (this file)
  plonkish-381-kzg.md      (canonical PLONKish profile)
  stark-fri-poseidon.md    (canonical STARK profile)
  ipa-pedersen.md          (canonical IPA profile)
  nova-ipa-poseidon.md     (canonical recursive profile)
Additional profiles MAY be added via MINOR amendments.

7. Canonical Closure
This document defines the only valid structure for the Profiles directory.
All profiles MUST follow these rules.
