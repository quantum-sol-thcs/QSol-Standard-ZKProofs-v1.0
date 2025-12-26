Versioning Model — QSol‑Standard‑ZKProofs‑v1.0
Normative Governance Document
QSol LLC — Harmonic Systems Research Division

1. Purpose and Scope
This document defines the official versioning model for:

QSol‑Standard‑ZKProofs‑v1.0

The versioning model ensures:

stability

predictability

auditability

compatibility

institutional continuity

canonical publication discipline

All future versions MUST follow this model.

2. Version Format
The Standard uses semantic versioning, extended with institutional constraints:

Code
MAJOR.MINOR.PATCH
Where:

MAJOR — breaking changes

MINOR — non‑breaking additions

PATCH — non‑breaking corrections

All three components MUST be integers ≥ 0.

3. Version Categories
3.1 PATCH Version
PATCH increments apply to:

typographical fixes

formatting corrections

non‑normative clarifications

manifest corrections

metadata corrections

PDF layout fixes

annex formatting fixes

PATCH versions MUST NOT:

change normative meaning

modify kernel rules

modify transcript rules

modify commitment rules

modify mapping invariants

modify certification requirements

PATCH versions MUST NOT break compatibility.

3.2 MINOR Version
MINOR increments apply to:

new annexes

new profiles

new CTS categories

new examples

new templates

non‑breaking clarifications

non‑breaking expansions

MINOR versions MUST NOT:

break compatibility

modify kernel rules

modify transcript rules

modify commitment rules

modify mapping invariants

MINOR versions MAY add new normative content, as long as it is strictly additive.

3.3 MAJOR Version
MAJOR increments apply to:

kernel rule changes

transcript rule changes

commitment rule changes

mapping invariant changes

certification rule changes

governance rule changes

repository structure changes

any breaking change

MAJOR versions require:

unanimous Governance Council approval

full republication

new canonical PDF

new manifest

new signatures

MAJOR versions MUST be rare and deliberate.

4. Versioning of Artifacts
The following MUST be versioned:

the Standard (spec/ZKProofs-v1.0.md)

all annexes

all CTS documents

all test vectors

all profiles

all certification documents

the canonical PDF

the hash manifest

the signature bundle

All artifacts MUST share the same version number.

5. Versioning Rules for Test Vectors
Test vectors MUST follow the same version as the Standard.

Adding new vectors → MINOR

Fixing encoding errors → PATCH

Changing expected outputs → MAJOR

Test vectors MUST NOT be modified retroactively.

6. Versioning Rules for Profiles
Profiles MUST follow the Standard version.

Adding a new profile → MINOR

Fixing profile formatting → PATCH

Changing profile semantics → MAJOR

Profiles MUST NOT weaken kernel rules.

7. Versioning Rules for Certification Documents
Certification documents MUST follow the Standard version.

Updating CAB template → MINOR

Fixing CAB formatting → PATCH

Changing certification requirements → MAJOR

Certification documents MUST remain aligned with the Standard.

8. Versioning Rules for Governance Documents
Governance documents MUST follow the Standard version.

Fixing formatting → PATCH

Adding new governance clarifications → MINOR

Changing governance structure → MAJOR

Governance changes require unanimous GC approval.

9. Versioning Workflow
9.1 Proposal
A version increment MUST be proposed via the amendment process.

9.2 Review
The Editorial Board, Technical Council, and Governance Council MUST review the proposal.

9.3 Approval
Approval requirements:

PATCH → EB + TC

MINOR → EB + TC + GC

MAJOR → TC + unanimous GC

9.4 Publication
A new version MUST include:

updated Markdown

updated PDF

updated manifest

updated signatures

updated release notes

9.5 Archival
All versions MUST be archived permanently.

10. Versioning of the Canonical PDF
The canonical PDF MUST:

embed the version number on the cover

embed the version number in metadata

embed the version number in the footer

match the manifest version

match the repository version

The PDF is the authoritative version.

11. Versioning of the Hash Manifest
The manifest MUST:

include the version number

include all files in the release

be signed

be stable across platforms

Any change to the manifest requires a version increment.

12. Canonical Version Identifier
The canonical version identifier is:

Code
ZKProofs-v<MAJOR>.<MINOR>.<PATCH>
Example:

Code
ZKProofs-v1.0.0
This identifier MUST appear in:

the PDF

the Markdown

the manifest

the signatures

the release notes

13. Amendment Boundary
This document is normative.
Any modification requires:

governance approval

version increment

canonical republication

14. Canonical Closure
This document defines the only valid versioning model for QSol‑Standard‑ZKProofs‑v1.0.
All future versions MUST follow these rules.
