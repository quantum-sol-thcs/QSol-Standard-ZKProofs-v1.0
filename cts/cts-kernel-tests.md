CTS Kernel Tests
Normative Document — QSol‑Standard‑ZKProofs‑v1.0
QSol LLC — Harmonic Systems Research Division

1. Purpose and Scope
This document defines the Kernel Test Suite (KTS), a mandatory component of the Conformance Test Suite (CTS).
These tests validate the correctness and determinism of:

AK — Algebra Kernel

CK — Commitment Kernel

SK — System Kernel

Passing all kernel tests is required for certification.

2. Test Vector Sources
Kernel tests rely on machine‑readable JSON vectors located in:

Code
cts/test-vectors/ak/
cts/test-vectors/ck/
cts/test-vectors/sk/
Each vector is normative and MUST be executed exactly as written.

3. Algebra Kernel (AK) Tests
AK tests validate all algebraic operations permitted inside the Algebra Kernel.

3.1 Field Arithmetic Tests
Vectors:

ak-f1-addition.json

ak-f2-multiplication.json

ak-f3-inversion.json

These tests validate:

canonical field encoding

correct arithmetic

deterministic behavior

correct error semantics (e.g., inversion of zero MUST error)

3.2 Polynomial Arithmetic Tests
Vectors:

ak-p1-eval.json

ak-p2-add.json

ak-p3-mul.json

These tests validate:

polynomial evaluation

polynomial addition

polynomial multiplication

canonical polynomial encoding

domain consistency

3.3 Inner Product Tests
Vector:

ak-fd1-inner-product.json

Validates:

correct inner product computation

deterministic ordering

canonical encoding of vectors

3.4 AK Compliance Requirements
Implementations MUST:

perform all witness‑dependent algebra inside AK

reject malformed encodings

produce deterministic outputs

follow Annex A kernel boundaries

Any deviation constitutes test failure.

4. Commitment Kernel (CK) Tests
CK tests validate commitment correctness, binding, and opening behavior.

4.1 Deterministic Commitment Tests
Vector:

ck-d1-deterministic.json

Validates:

deterministic commitment generation

no randomness leakage

canonical encoding

4.2 Binding Tests
Vector:

ck-b1-binding.json

Validates:

binding property

inability to open a commitment to multiple values

correct error semantics

4.3 Opening Tests
Vector:

ck-o1-opening.json

Validates:

correct opening generation

correct opening verification

canonical encoding of openings

4.4 CK Compliance Requirements
Implementations MUST:

perform all commitment operations inside CK

use deterministic commitments unless profile specifies otherwise

reject malformed openings

follow Annex A kernel boundaries

Any deviation constitutes test failure.

5. System Kernel (SK) Tests
SK tests validate transcript construction, hashing, and challenge derivation.

5.1 Transcript Tests
Vector:

sk-t1-transcript.json

Validates:

correct transcript ordering

correct hashing

canonical transcript encoding

5.2 Domain Separation Tests
Vector:

sk-ds1-domain-separator.json

Validates:

correct domain separation

correct prefixing

correct transcript state transitions

5.3 Challenge Derivation Tests
Vector:

sk-ch1-challenge.json

Validates:

deterministic challenge derivation

correct hashing

correct transcript state

5.4 SK Compliance Requirements
Implementations MUST:

perform all transcript operations inside SK

use canonical encoding

enforce domain separation

produce deterministic challenges

Any deviation constitutes test failure.

6. Execution Rules
For all kernel tests:

Inputs MUST be parsed using canonical encoding

Outputs MUST match expected values exactly

Errors MUST match expected error semantics

No nondeterminism is permitted

No off‑kernel computation is permitted

No environment‑dependent behavior is permitted

Failure of any test results in non‑conformance.

7. Environment Requirements
Kernel tests MUST be executed under:

multiple hardware architectures

multiple operating systems

multiple compilers

multiple optimization levels

Outputs MUST be identical across all environments.

8. Versioning
Kernel test vectors are versioned:

1.0.0 for initial release

incremented on MINOR or MAJOR changes

regenerated on PATCH changes

Implementations MUST use the vectors matching the Standard version.

9. Canonical Closure
This document defines the only valid Kernel Test Suite for QSol‑Standard‑ZKProofs‑v1.0.
All certified implementations MUST pass all kernel tests.
