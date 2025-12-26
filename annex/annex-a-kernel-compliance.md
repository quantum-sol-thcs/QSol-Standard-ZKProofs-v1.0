Annex A — Kernel Compliance Requirements (KCA)
Normative Annex — QSol‑Standard‑ZKProofs‑v1.0
QSol LLC — Harmonic Systems Research Division

A.1 Purpose and Scope
This annex defines the mandatory compliance requirements for all implementations of the ZKProofs‑v1.0 Kernel‑Constitutional Architecture.
Compliance with this annex is required for:

certification

conformance testing

interoperability

security review

protocol mapping approval

No implementation may claim conformance to ZKProofs‑v1.0 unless it satisfies all requirements in this annex.

A.2 Kernel Exclusivity Principle
All witness‑dependent computation MUST occur exclusively inside one of the three kernels:

AK — Algebra Kernel

CK — Commitment Kernel

SK — System Kernel

No computation influencing:

witness values

commitments

openings

transcript entries

challenges

prover state

verifier state

may occur outside these kernels.

Any such off‑kernel computation constitutes a compliance violation.

A.3 Algebra Kernel (AK) Compliance
A.3.1 Allowed Operations
The AK is the only location where the following may occur:

Field arithmetic

Polynomial arithmetic

Constraint evaluation

Domain transformations

NTT/FFT operations

Inner products

Linear combinations

Witness‑dependent algebraic computation

A.3.2 Forbidden Operations
The AK MUST NOT:

Generate commitments

Derive challenges

Modify transcript state

Perform hashing

Perform serialization or encoding

Access randomness sources

Any such behavior is a violation.

A.4 Commitment Kernel (CK) Compliance
A.4.1 Allowed Operations
The CK is the only location where the following may occur:

Commitment generation

Opening generation

Opening verification

Binding checks

Deterministic commitment derivation

Polynomial commitment scheme operations

A.4.2 Forbidden Operations
The CK MUST NOT:

Perform algebraic witness computation

Derive challenges

Modify transcript state

Perform transcript hashing

Execute protocol logic

Commitments MUST be deterministic unless the profile explicitly specifies a randomness model.

A.5 System Kernel (SK) Compliance
A.5.1 Allowed Operations
The SK is the only location where the following may occur:

Transcript construction

Transcript hashing

Challenge derivation

Domain separation enforcement

Ordering and sequencing

Protocol‑level state transitions

A.5.2 Forbidden Operations
The SK MUST NOT:

Perform algebraic computation

Generate commitments

Verify openings

Execute constraint evaluation

Access witness values

The SK is a pure state‑transition engine.

A.6 Determinism Requirements
All kernel operations MUST be:

deterministic

reproducible

independent of environment

independent of execution order

independent of hardware or platform

Non‑determinism is permitted only when explicitly defined in the implementation profile.

A.7 Domain Separation Requirements
All transcript operations MUST include:

kernel‑level domain separation

protocol‑level domain separation

profile‑level domain separation

Domain separation MUST be:

explicit

unambiguous

collision‑resistant

stable across versions

A.8 Canonical Encoding Requirements
All kernel inputs and outputs MUST use:

canonical byte encoding

canonical field encoding

canonical polynomial encoding

canonical transcript encoding

Profiles MAY define additional encoding rules but MUST NOT violate canonical encoding.

A.9 Off‑Kernel Computation Prohibitions
The following MUST NOT occur outside AK/CK/SK:

witness‑dependent computation

commitment generation

opening generation

transcript hashing

challenge derivation

constraint evaluation

polynomial arithmetic

randomness generation (unless profile‑approved)

Any violation results in automatic conformance failure.

A.10 Error Semantics Compliance
All kernels MUST implement:

strict error boundaries

explicit failure modes

no silent fallback behavior

no implicit coercion

no environment‑dependent behavior

Errors MUST be:

deterministic

reproducible

profile‑consistent

A.11 Conformance Test Suite (CTS) Binding
Compliance with this annex is validated through:

AK kernel tests

CK kernel tests

SK kernel tests

determinism tests

mapping tests

Failure of any CTS category constitutes non‑conformance.

A.12 Certification Requirements
To be certified as ZKProofs‑v1.0 compliant, an implementation MUST:

satisfy all requirements in this annex

pass all CTS categories

provide a complete Certification Artifact Bundle (CAB)

declare a profile

undergo auditor review

Certification is issued exclusively by QSol LLC.

A.13 Amendment Boundary
This annex is normative.
Any modification requires:

a MINOR or MAJOR version increment

governance approval

canonical republication

A.14 Canonical Closure
This annex forms part of the QSol‑Standard‑ZKProofs‑v1.0 normative specification and is binding for all implementations, profiles, and certification processes.
