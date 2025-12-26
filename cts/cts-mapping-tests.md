CTS Mapping Tests
Normative Document — QSol‑Standard‑ZKProofs‑v1.0
QSol LLC — Harmonic Systems Research Division

1. Purpose and Scope
This document defines the Mapping Test Suite (MTS), a mandatory component of the Conformance Test Suite (CTS).
Mapping tests validate that an implementation’s protocol‑level mapping:

preserves kernel boundaries

respects mapping invariants

follows mapping templates

produces deterministic outputs

uses canonical encoding

maintains transcript and commitment correctness

does not introduce off‑kernel computation

Passing all mapping tests is required for certification.

2. Mapping Test Vector Sources
Mapping tests rely on:

canonical mapping invariants (Sections 19–23 of the Standard)

profile‑specific mapping rules

SK transcript vectors

CK commitment vectors

AK algebra vectors

Mapping tests do not use a separate JSON directory; instead, they combine kernel vectors into mapping‑level scenarios.

3. Mapping Invariants Under Test
Mapping tests validate the following invariants:

3.1 Kernel Exclusivity
Mappings MUST NOT:

perform algebra outside AK

perform commitments outside CK

perform transcript operations outside SK

3.2 Determinism
Mappings MUST:

produce identical outputs across all environments

use deterministic transcript ordering

use deterministic challenge derivation

use deterministic commitment behavior

3.3 Canonical Encoding
Mappings MUST:

use canonical byte encoding

use canonical field encoding

use canonical polynomial encoding

use canonical transcript encoding

3.4 No Hidden State
Mappings MUST NOT:

introduce hidden randomness

introduce environment‑dependent behavior

introduce implicit state transitions

3.5 Template Conformance
Mappings MUST follow:

mapping templates (Section 21)

mapping examples (Section 22)

mapping error semantics (Section 23)

4. Mapping Test Categories
Mapping tests are divided into three categories:

Constraint Mapping Tests

Commitment Mapping Tests

Transcript Mapping Tests

Each category validates a different aspect of the mapping pipeline.

5. Constraint Mapping Tests
Constraint mapping tests validate:

correct translation of constraints into AK operations

correct polynomial construction

correct domain selection

correct evaluation ordering

correct error semantics

Auditors MUST verify:

no off‑kernel algebra

no witness leakage

deterministic constraint evaluation

canonical polynomial encoding

Failure of any condition constitutes test failure.

6. Commitment Mapping Tests
Commitment mapping tests validate:

correct commitment of mapped polynomials

correct opening generation

correct opening verification

correct binding behavior

correct transcript integration

Auditors MUST verify:

commitments are deterministic

openings match expected values

no off‑kernel algebra occurs

no randomness leakage occurs

canonical encoding is used

Any deviation constitutes test failure.

7. Transcript Mapping Tests
Transcript mapping tests validate:

correct transcript construction

correct domain separation

correct challenge derivation

correct ordering of transcript entries

correct integration of commitments and openings

Auditors MUST verify:

transcript is deterministic

transcript matches SK vectors

no witness values appear in transcript

no off‑kernel transcript operations occur

Transcript mismatches constitute test failure.

8. Mapping Error Semantics Tests
Mappings MUST:

reject malformed constraints

reject malformed commitments

reject malformed openings

reject malformed transcript entries

produce deterministic error messages

Error semantics MUST match Section 23 of the Standard.

9. Execution Rules
For all mapping tests:

Inputs MUST be canonical

Outputs MUST match expected values exactly

Errors MUST match expected error semantics

No nondeterminism is permitted

No off‑kernel computation is permitted

No environment‑dependent behavior is permitted

Failure of any test results in non‑conformance.

10. Environment Requirements
Mapping tests MUST be executed under:

multiple hardware architectures

multiple operating systems

multiple compilers

multiple optimization levels

Outputs MUST be identical across all environments.

11. Versioning
Mapping tests are versioned:

1.0.0 for initial release

incremented on MINOR or MAJOR changes

regenerated on PATCH changes

Implementations MUST use the mapping tests matching the Standard version.

12. Canonical Closure
This document defines the only valid Mapping Test Suite for QSol‑Standard‑ZKProofs‑v1.0.
All certified implementations MUST pass all mapping tests.
