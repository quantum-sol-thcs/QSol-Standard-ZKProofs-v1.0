Annex C — Canonical Repository Structure
Normative Annex — QSol‑Standard‑ZKProofs‑v1.0
QSol LLC — Harmonic Systems Research Division

C.1 Purpose and Scope
This annex defines the canonical repository structure for the QSol‑Standard‑ZKProofs‑v1.0 publication.
All official releases, mirrors, and archival copies MUST follow this structure exactly.

The structure ensures:

institutional consistency

auditability

long‑term maintainability

deterministic publication

compatibility with certification workflows

clarity for implementers and auditors

No file or directory may be removed, renamed, or repurposed without a MINOR or MAJOR version increment.

C.2 Top‑Level Directory Layout
The root of the repository MUST contain:

Code
AUTHORS
CHANGELOG.md
LICENSE
README.md
VERSION
spec/
annex/
cts/
certification/
governance/
profiles/
reference/
metadata/
publication/
These files and directories form the identity layer of the Standard.

C.3 Specification Directory (spec/)
Contains the normative text of the Standard:

Code
spec/
    ZKProofs-v1.0.md
    glossary.md
    notation.md
    changelog.md
ZKProofs-v1.0.md is the canonical Markdown source of the Standard.

glossary.md and notation.md provide normative definitions.

changelog.md tracks spec‑level changes.

C.4 Annex Directory (annex/)
Contains all normative annexes:

Code
annex/
    annex-a-kernel-compliance.md
    annex-b-test-vectors.md
    annex-c-repository-structure.md
    annex-d-hash-manifest.md
    annex-e-pdf-layout.md
Annexes are binding and versioned with the Standard.

C.5 Conformance Test Suite (cts/)
Contains the CTS specification and machine‑readable test vectors:

Code
cts/
    cts-spec.md
    cts-kernel-tests.md
    cts-mapping-tests.md
    cts-determinism-tests.md
    test-vectors/
        ak/
        ck/
        sk/
Each subdirectory contains canonical JSON vectors.

C.6 Certification Directory (certification/)
Contains certification requirements and templates:

Code
certification/
    cab-template.md
    auditor-guidelines.md
    certification-process.md
These files define the Certification Artifact Bundle (CAB) and auditor workflow.

C.7 Governance Directory (governance/)
Defines the long‑term institutional governance model:

Code
governance/
    amendment-procedures.md
    governance-structure.md
    versioning.md
These documents are normative and govern all future revisions.

C.8 Profiles Directory (profiles/)
Contains implementation profiles:

Code
profiles/
    plonkish-381-kzg.md
    stark-fri-poseidon.md
    ipa-pedersen.md
    nova-recursive-ipa.md
    profile-template.md
Profiles MUST NOT modify kernel rules.

C.9 Reference Implementations (reference/)
Contains minimal correctness oracles:

Code
reference/
    ak-reference/
        field-ops.md
        polynomial-ops.md
        constraint-eval.md
    ck-reference/
        commitment-scheme.md
        opening-verification.md
    sk-reference/
        transcript-engine.md
        challenge-derivation.md
These are non‑normative but strongly recommended.

C.10 Metadata Directory (metadata/)
Contains cryptographic integrity artifacts:

Code
metadata/
    hash-manifest.txt
    signatures/
    release-notes/
hash-manifest.txt is normative.

Signatures authenticate canonical releases.

Release notes document version history.

C.11 Publication Directory (publication/)
Contains the canonical PDF and its LaTeX source:

Code
publication/
    pdf/
        ZKProofs-v1.0.pdf
    latex/
        main.tex
        macros.tex
        cover.tex
        toc.tex
        annexes.tex
    assets/
        canonical-seal.svg
        qsol-logo.svg
        publication-banner.png
The PDF is the authoritative citation artifact.

C.12 Modification Rules
The following actions require a MAJOR version increment:

removing directories

renaming directories

altering canonical file paths

restructuring annexes

modifying CTS directory layout

The following actions require a MINOR version increment:

adding new profiles

adding new annexes

adding new CTS categories

adding new reference implementations

PATCH versions may update content but MUST NOT alter structure.

C.13 Canonical Closure
This annex defines the only valid repository structure for QSol‑Standard‑ZKProofs‑v1.0.
All official releases MUST conform to this structure.
