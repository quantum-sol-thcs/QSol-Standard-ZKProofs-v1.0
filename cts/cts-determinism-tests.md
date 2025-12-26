CTS Determinism Tests
Normative Document — QSol‑Standard‑ZKProofs‑v1.0
QSol LLC — Harmonic Systems Research Division

1. Purpose and Scope
This document defines the Determinism Test Suite (DTS), a mandatory component of the Conformance Test Suite (CTS).
Determinism tests validate that an implementation produces identical outputs across all environments, including:

hardware architectures

operating systems

compilers

optimization levels

execution orders

runtime environments

Determinism is a hard requirement for certification.

2. Determinism Requirements
An implementation MUST:

produce identical outputs for identical inputs

produce identical transcripts

produce identical commitments

produce identical openings

produce identical challenges

produce identical kernel outputs

produce identical error semantics

Determinism MUST hold across:

CPU architectures (x86_64, ARM64, etc.)

operating systems (Linux, macOS, Windows)

compilers (clang, gcc, msvc, rustc, etc.)

optimization levels (-O0, -O1, -O2, -O3, -Os)

execution orders (parallel vs sequential)

runtime environments (debug vs release)

Any deviation constitutes automatic non‑conformance.

3. Determinism Test Categories
Determinism tests are divided into four categories:

Kernel Determinism Tests

Transcript Determinism Tests

Commitment Determinism Tests

Mapping Determinism Tests

Each category validates a different layer of the implementation.

4. Kernel Determinism Tests
Auditors MUST verify:

AK operations produce identical outputs across environments

CK commitments and openings are identical across environments

SK transcript and challenge derivation is identical across environments

Kernel determinism is validated by re‑running all kernel vectors under multiple environments.

Failure of any kernel vector under any environment constitutes test failure.

5. Transcript Determinism Tests
Auditors MUST verify:

transcript ordering is identical

transcript hashing is identical

domain separation is identical

challenge derivation is identical

Transcript determinism MUST hold even when:

execution order changes

concurrency changes

compiler optimizations change

Transcript mismatches constitute test failure.

6. Commitment Determinism Tests
Auditors MUST verify:

commitments are deterministic

openings are deterministic

opening verification is deterministic

If a profile allows randomness, auditors MUST verify:

randomness is profile‑approved

randomness is transcript‑bound

randomness does not leak

randomness does not affect determinism of verification

Any deviation constitutes test failure.

7. Mapping Determinism Tests
Auditors MUST verify:

mapping invariants are deterministic

mapping templates produce identical outputs

mapping error semantics are deterministic

mapping does not introduce nondeterminism

Mapping determinism MUST hold across all environments.

8. Execution Requirements
Determinism tests MUST be executed under:

8.1 Hardware Variants
At least:

one x86_64 machine

one ARM64 machine

8.2 Operating Systems
At least:

Linux

macOS or Windows

8.3 Compilers
At least:

clang

gcc

rustc (if applicable)

msvc (if applicable)

8.4 Optimization Levels
At least:

-O0

-O2

-O3

8.5 Execution Orders
At least:

sequential

parallel

Outputs MUST be identical across all combinations.

9. Failure Conditions
A determinism test fails if:

outputs differ

transcripts differ

commitments differ

openings differ

challenges differ

error semantics differ

ordering differs

encoding differs

environment affects behavior

Any failure results in non‑conformance.

10. Versioning
Determinism tests are versioned:

1.0.0 for initial release

incremented on MINOR or MAJOR changes

regenerated on PATCH changes

Implementations MUST use the determinism tests matching the Standard version.

11. Canonical Closure
This document defines the only valid Determinism Test Suite for QSol‑Standard‑ZKProofs‑v1.0.
All certified implementations MUST pass all determinism tests.
