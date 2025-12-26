Conformance Test Suite (CTS) Specification
Normative Document — QSol‑Standard‑ZKProofs‑v1.0
QSol LLC — Harmonic Systems Research Division

1. Purpose and Scope
The Conformance Test Suite (CTS) defines the mandatory tests required for an implementation to claim compliance with:

QSol‑Standard‑ZKProofs‑v1.0

The CTS ensures:

kernel correctness

determinism

canonical encoding

transcript stability

commitment correctness

mapping correctness

profile consistency

interoperability

Passing the CTS is required for certification.

2. CTS Structure
The CTS consists of five categories:

Kernel Tests (AK/CK/SK)

Determinism Tests

Mapping Tests

Encoding Tests

Transcript Tests

Each category is defined in a separate document:

Code
cts-kernel-tests.md
cts-determinism-tests.md
cts-mapping-tests.md
Machine‑readable vectors are located under:

Code
cts/test-vectors/
3. Test Vector Format
All test vectors MUST follow the canonical JSON structure:

Code
{
  "id": "<unique-id>",
  "kernel": "AK | CK | SK",
  "operation": "<operation-name>",
  "input": { ... },
  "expected": { ... },
  "version": "1.0.0",
  "profile": "<optional>"
}
Rules:

All fields are mandatory unless marked optional

All encodings MUST be canonical

All values MUST be deterministic

All vectors MUST be versioned

4. Execution Requirements
Implementations MUST:

parse all test vectors

execute all operations exactly as defined

produce outputs identical to expected

use canonical encoding

use deterministic behavior

reject malformed inputs

follow kernel boundaries

Any deviation constitutes test failure.

5. Kernel Test Requirements
5.1 Algebra Kernel (AK)
Tests validate:

field arithmetic

polynomial arithmetic

constraint evaluation

domain transformations

inner products

Vectors located in:

Code
cts/test-vectors/ak/
5.2 Commitment Kernel (CK)
Tests validate:

deterministic commitments

binding

opening generation

opening verification

Vectors located in:

Code
cts/test-vectors/ck/
5.3 System Kernel (SK)
Tests validate:

transcript construction

domain separation

challenge derivation

Vectors located in:

Code
cts/test-vectors/sk/
6. Determinism Test Requirements
Implementations MUST produce identical outputs across:

hardware

operating systems

compilers

execution orders

optimization levels

Determinism tests MUST be executed at least:

once per environment

once per compiler

once per optimization level

Any nondeterminism constitutes automatic failure.

7. Mapping Test Requirements
Mapping tests validate:

mapping invariants

mapping templates

mapping error semantics

mapping determinism

mapping correctness

Mappings MUST NOT:

violate kernel boundaries

introduce nondeterminism

alter transcript semantics

alter commitment semantics

8. Encoding Test Requirements
Implementations MUST use:

canonical byte encoding

canonical field encoding

canonical polynomial encoding

canonical transcript encoding

Encoding mismatches constitute test failure.

9. Transcript Test Requirements
Transcript tests validate:

ordering

hashing

domain separation

challenge derivation

stability

Transcript mismatches constitute test failure.

10. Test Execution Environment
Auditors MUST execute the CTS under:

at least two hardware architectures

at least two operating systems

at least two compilers

multiple optimization levels

Implementations MUST pass in all environments.

11. Failure Conditions
A test fails if:

output differs from expected

encoding is incorrect

determinism is violated

kernel boundaries are violated

transcript is incorrect

commitments are incorrect

openings are incorrect

mapping invariants are violated

Any failure results in non‑conformance.

12. Versioning
CTS version MUST match the Standard version:

1.0.0 for initial release

incremented on MINOR or MAJOR changes

regenerated on PATCH changes

13. Canonical Closure
This document defines the only valid Conformance Test Suite for QSol‑Standard‑ZKProofs‑v1.0.
All certified implementations MUST pass all CTS categories.
