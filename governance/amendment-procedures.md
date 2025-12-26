Amendment Procedures — QSol‑Standard‑ZKProofs‑v1.0
Normative Governance Document
QSol LLC — Harmonic Systems Research Division

1. Purpose and Scope
This document defines the mandatory procedures for proposing, reviewing, approving, and publishing amendments to:

QSol‑Standard‑ZKProofs‑v1.0

These procedures ensure:

institutional continuity

version stability

canonical publication

auditability

protection of authorship and intent

No amendment may bypass these procedures.

2. Amendment Categories
Amendments fall into three categories:

2.1 PATCH Amendments
Fix typographical errors

Fix formatting issues

Fix non‑normative clarifications

Fix manifest or metadata inconsistencies

PATCH amendments MUST NOT change normative meaning.

2.2 MINOR Amendments
Add new annexes

Add new profiles

Add new CTS categories

Add new examples or templates

Add non‑breaking clarifications

MINOR amendments MUST NOT break compatibility.

2.3 MAJOR Amendments
Modify kernel rules

Modify transcript rules

Modify commitment rules

Modify mapping invariants

Modify certification requirements

Modify governance structure

Modify repository structure

MAJOR amendments require full governance review.

3. Amendment Proposal Requirements
A valid amendment proposal MUST include:

amendment category (PATCH, MINOR, MAJOR)

rationale

proposed text

affected sections

compatibility analysis

security impact analysis

version impact

implementation impact

CTS impact

Incomplete proposals are rejected.

4. Review Process
All proposals undergo a three‑stage review:

4.1 Stage 1 — Editorial Review
Checks:

formatting

clarity

completeness

category correctness

4.2 Stage 2 — Technical Review
Checks:

kernel boundary integrity

determinism preservation

transcript stability

commitment correctness

mapping invariants

security impact

4.3 Stage 3 — Governance Review
Checks:

institutional alignment

long‑term stability

compatibility with QSol’s mission

authorship protection

publication integrity

All three stages MUST approve the amendment.

5. Approval Requirements
5.1 PATCH Amendments
Require:

editorial approval

technical approval

5.2 MINOR Amendments
Require:

editorial approval

technical approval

governance approval

5.3 MAJOR Amendments
Require:

unanimous governance approval

full republication

version increment

updated hash manifest

updated signatures

MAJOR amendments MUST be published as a new canonical release.

6. Publication Requirements
Approved amendments MUST be:

Incorporated into the Markdown source

Incorporated into the canonical PDF

Added to the CHANGELOG.md

Added to the metadata/hash-manifest.txt

Signed using institutional keys

Published as a tagged release

No amendment is valid until published.

7. Amendment Rejection
Amendments may be rejected for:

violating kernel boundaries

introducing nondeterminism

weakening security

breaking compatibility

conflicting with governance rules

lacking sufficient rationale

lacking technical clarity

Rejections MUST include a written explanation.

8. Emergency Amendments
Emergency amendments may be issued only when:

a security vulnerability is discovered

a critical correctness issue is found

a certification‑blocking error exists

Emergency amendments require:

immediate governance approval

immediate republication

immediate manifest update

immediate signature update

Emergency amendments MUST be labeled as such.

9. Amendment Archival
All amendments MUST be archived under:

Code
metadata/release-notes/
Each amendment MUST include:

version

date

summary

rationale

affected sections

signatures

Archival is permanent.

10. Canonical Closure
This document defines the only valid amendment process for QSol‑Standard‑ZKProofs‑v1.0.
All future modifications MUST follow these procedures.
