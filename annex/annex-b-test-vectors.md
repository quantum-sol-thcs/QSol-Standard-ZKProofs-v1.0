Annex B — Test Vectors
I’ll now deliver the full, publication‑grade content for:

Code
annex/annex-b-test-vectors.md
This annex defines the structure, format, and requirements for all kernel‑level test vectors used in the CTS. It does not contain the JSON vectors themselves — those live in /cts/test-vectors/ — but it defines how they must be interpreted, validated, and versioned.

Here is the complete canonical text.

Annex B — Kernel Test Vector Suite (KTVS)
Normative Annex — QSol‑Standard‑ZKProofs‑v1.0
QSol LLC — Harmonic Systems Research Division

B.1 Purpose and Scope
This annex defines the Kernel Test Vector Suite (KTVS) used by the Conformance Test Suite (CTS) to validate:

Algebra Kernel (AK) correctness

Commitment Kernel (CK) correctness

System Kernel (SK) correctness

Determinism

Canonical encoding

Domain separation

Transcript stability

The test vectors in this annex are normative.
All implementations MUST pass all applicable vectors to claim conformance.

B.2 Test Vector Structure
Each test vector is encoded as a canonical JSON document with the following fields:

id — unique test identifier

kernel — AK, CK, or SK

operation — specific operation under test

input — canonical input encoding

expected — canonical expected output

notes — optional clarifying information

version — test vector version

profile — optional profile‑specific applicability

Example structure:

json
{
  "id": "ak-f1-addition",
  "kernel": "AK",
  "operation": "field_add",
  "input": {
    "a": "0x01",
    "b": "0x02"
  },
  "expected": {
    "result": "0x03"
  },
  "version": "1.0.0"
}
All fields are mandatory unless explicitly marked optional.

B.3 Canonical Encoding Requirements
All test vectors MUST use:

canonical byte encoding

canonical field encoding

canonical polynomial encoding

canonical transcript encoding

Implementations MUST NOT reinterpret or coerce encodings.

Failure to parse canonical encoding constitutes test failure.

B.4 Algebra Kernel (AK) Test Vectors
AK vectors validate:

field addition

field multiplication

field inversion

polynomial evaluation

polynomial addition

polynomial multiplication

inner products

domain transformations

These vectors ensure that all algebraic operations are:

deterministic

canonical

profile‑independent

mathematically correct

The AK vectors are located in:

Code
cts/test-vectors/ak/
B.5 Commitment Kernel (CK) Test Vectors
CK vectors validate:

deterministic commitments

binding checks

opening generation

opening verification

These vectors ensure:

no randomness leakage

no off‑kernel algebra

deterministic commitment derivation

The CK vectors are located in:

Code
cts/test-vectors/ck/
B.6 System Kernel (SK) Test Vectors
SK vectors validate:

transcript construction

domain separation

challenge derivation

These vectors ensure:

transcript stability

deterministic hashing

correct ordering

no witness access

The SK vectors are located in:

Code
cts/test-vectors/sk/
B.7 Determinism Vectors
Determinism vectors validate:

reproducibility

environment independence

hardware independence

ordering independence

These vectors MUST be passed under:

different compilers

different hardware

different operating systems

different execution orders

Failure under any environment constitutes non‑conformance.

B.8 Versioning of Test Vectors
Test vectors follow the QSol Standards Versioning Model:

MAJOR — breaking changes

MINOR — new vectors, non‑breaking

PATCH — clarifications, encoding fixes

All vectors in this annex are versioned 1.0.0.

B.9 Profile‑Specific Extensions
Profiles MAY define additional test vectors, but:

they MUST NOT override canonical vectors

they MUST NOT weaken requirements

they MUST NOT introduce non‑determinism unless explicitly allowed

Profile‑specific vectors MUST be placed under:

Code
cts/test-vectors/<profile>/
B.10 Conformance Binding
Passing all vectors in this annex is mandatory for:

certification

profile approval

interoperability claims

public conformance declarations

Failure of any vector constitutes automatic non‑conformance.

B.11 Canonical Closure
This annex forms part of the QSol‑Standard‑ZKProofs‑v1.0 normative specification and is binding for all implementations, profiles, and certification processes.
