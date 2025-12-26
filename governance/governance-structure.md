Governance Structure — QSol‑Standard‑ZKProofs‑v1.0
Normative Governance Document
QSol LLC — Harmonic Systems Research Division

1. Purpose and Scope
This document defines the institutional governance structure responsible for:

maintaining the Standard

approving amendments

overseeing certification

preserving authorship and intent

ensuring long‑term stability

managing canonical publication

This governance structure is binding for all future versions of the Standard.

2. Governance Principles
The governance model is built on six constitutional principles:

Kernel Sovereignty — kernel rules cannot be weakened.

Determinism Preservation — nondeterminism cannot be introduced.

Authorship Protection — original intent and structure must be preserved.

Canonical Publication — only one canonical version may exist at a time.

Institutional Continuity — governance persists beyond individual contributors.

Security Primacy — security considerations override convenience or preference.

All governance decisions MUST uphold these principles.

3. Governance Bodies
The governance structure consists of three bodies:

Editorial Board (EB)

Technical Council (TC)

Governance Council (GC)

Each body has distinct responsibilities and approval authority.

4. Editorial Board (EB)
4.1 Responsibilities
The Editorial Board is responsible for:

formatting

clarity

consistency

non‑normative corrections

repository hygiene

publication preparation

4.2 Authority
The EB may approve:

PATCH amendments

non‑normative clarifications

formatting corrections

metadata fixes

The EB may NOT:

modify kernel rules

modify transcript rules

modify commitment rules

modify mapping invariants

modify certification requirements

5. Technical Council (TC)
5.1 Responsibilities
The Technical Council is responsible for:

kernel boundary integrity

determinism preservation

transcript stability

commitment correctness

mapping invariants

security analysis

CTS design and maintenance

5.2 Authority
The TC may approve:

PATCH amendments

MINOR amendments

new profiles

new CTS categories

new annexes

The TC may NOT:

modify governance structure

modify versioning rules

approve MAJOR amendments alone

6. Governance Council (GC)
6.1 Responsibilities
The Governance Council is responsible for:

institutional alignment

long‑term stability

authorship protection

canonical publication

versioning decisions

emergency amendments

6.2 Authority
The GC may approve:

MINOR amendments

MAJOR amendments

emergency amendments

new canonical releases

version increments

governance changes

MAJOR amendments require unanimous GC approval.

7. Decision Flow
Amendments follow this approval flow:

Amendment Type	EB	TC	GC
PATCH	✔️	✔️	—
MINOR	✔️	✔️	✔️
MAJOR	—	✔️	✔️ (unanimous)
Emergency	—	—	✔️ (immediate)
No amendment is valid until all required bodies approve.

8. Membership and Terms
8.1 Appointment
Members of EB, TC, and GC are appointed by:

QSol LLC — Harmonic Systems Research Division

8.2 Term Length
EB: 2 years

TC: 3 years

GC: 4 years

Terms are renewable.

8.3 Removal
Members may be removed for:

conflict of interest

breach of confidentiality

violation of governance rules

failure to uphold constitutional principles

9. Conflict of Interest Policy
Members MUST disclose:

financial conflicts

employment conflicts

research conflicts

personal conflicts

Members with conflicts MUST recuse themselves from relevant decisions.

10. Transparency Requirements
The following MUST be published:

amendment proposals

approval decisions

version increments

release notes

certification revocations

Internal deliberations MAY remain confidential.

11. Emergency Powers
The GC may issue emergency amendments only when:

a security vulnerability is discovered

a correctness issue threatens interoperability

certification is blocked by a critical error

Emergency amendments MUST be:

published immediately

added to the manifest

signed

archived

12. Canonical Publication Authority
Only the GC may authorize:

new canonical releases

new PDF publications

new manifest versions

new signature bundles

No other entity may publish canonical versions.

13. Amendment Boundary
This document is normative.
Any modification requires:

unanimous GC approval

version increment

canonical republication

14. Canonical Closure
This document defines the only valid governance structure for QSol‑Standard‑ZKProofs‑v1.0.
All future modifications MUST follow these rules.
