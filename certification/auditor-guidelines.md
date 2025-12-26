Auditor Guidelines — QSol‑Standard‑ZKProofs‑v1.0
Normative Certification Document
QSol LLC — Harmonic Systems Research Division

1. Purpose and Scope
These guidelines define the mandatory procedures, responsibilities, and evaluation criteria for auditors performing conformance assessments of implementations claiming compliance with:

QSol‑Standard‑ZKProofs‑v1.0

Auditors MUST follow these guidelines exactly.
No deviation, reinterpretation, or omission is permitted.

2. Auditor Role and Authority
Auditors operate under the authority of:

QSol LLC — Harmonic Systems Research Division

Auditors are responsible for:

verifying full compliance with the Standard

validating all Certification Artifact Bundle (CAB) materials

executing the Conformance Test Suite (CTS)

confirming deterministic behavior

ensuring no off‑kernel computation

verifying canonical encoding

validating profile declarations

confirming hash and signature integrity

Auditors MUST remain neutral, independent, and technically rigorous.

3. Required Inputs
Auditors MUST receive the following from the implementer:

Certification Artifact Bundle (CAB)

Implementation Profile

Complete source code (or equivalent reproducible build artifacts)

Build instructions

Execution environment details

Declared kernel boundaries

Declared transcript format

Declared commitment scheme parameters

Declared domain separation scheme

Missing or incomplete inputs constitute automatic certification failure.

4. Certification Artifact Bundle (CAB) Requirements
The CAB MUST include:

implementation profile

kernel boundary declaration

transcript specification

commitment scheme specification

mapping specification

determinism declaration

environment declaration

CTS results

hash manifest of implementation artifacts

version declaration

auditor‑ready build instructions

The CAB MUST be complete, consistent, and self‑contained.

5. Conformance Test Suite (CTS) Execution
Auditors MUST execute:

AK kernel tests

CK kernel tests

SK kernel tests

determinism tests

mapping tests

All tests MUST pass exactly.
No partial credit is permitted.

Auditors MUST verify:

canonical encoding

deterministic outputs

correct error semantics

correct transcript ordering

correct domain separation

correct commitment behavior

Any deviation constitutes non‑conformance.

6. Kernel Boundary Verification
Auditors MUST confirm:

all witness‑dependent computation occurs inside AK

all commitment operations occur inside CK

all transcript/challenge operations occur inside SK

no off‑kernel computation exists

no hidden or implicit computation exists

no environment‑dependent behavior exists

Boundary violations are fatal.

7. Determinism Verification
Auditors MUST test the implementation under:

different hardware

different operating systems

different compilers

different execution orders

different optimization levels

Outputs MUST be identical across all environments.

Any nondeterminism constitutes automatic failure.

8. Transcript Verification
Auditors MUST verify:

transcript construction

transcript hashing

challenge derivation

domain separation

ordering

stability

Transcript mismatches are non‑conformant.

9. Commitment Scheme Verification
Auditors MUST verify:

deterministic commitments

binding properties

opening correctness

opening verification correctness

no off‑kernel algebra

no randomness leakage

Any deviation constitutes failure.

10. Mapping Verification
Auditors MUST verify:

mapping invariants

mapping templates

mapping error semantics

mapping determinism

mapping correctness

Mappings MUST NOT:

alter kernel rules

bypass kernel boundaries

introduce nondeterminism

11. Hash Manifest Verification
Auditors MUST:

verify SHA3‑256 hashes

verify manifest completeness

verify manifest correctness

verify signatures

confirm no extraneous files

confirm no missing files

Hash mismatches invalidate certification.

12. Certification Decision Criteria
Certification is granted ONLY if:

all CTS tests pass

all CAB materials are complete

all kernel boundaries are respected

all transcripts are correct

all commitments are correct

all mappings are correct

all hashes match

all signatures verify

no violations are found

Certification MUST be denied if any requirement fails.

13. Reporting Requirements
Auditors MUST produce:

a final certification report

a list of all tests executed

a list of all artifacts reviewed

a list of all findings

a final pass/fail decision

Reports MUST be archived by QSol LLC.

14. Amendment Boundary
These guidelines are normative.
Any modification requires:

governance approval

version increment

canonical republication

15. Canonical Closure
These guidelines define the only valid auditor workflow for ZKProofs‑v1.0 certification.
All auditors MUST comply fully.
