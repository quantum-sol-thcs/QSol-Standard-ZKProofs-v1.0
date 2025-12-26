publication/README.md
Canonical Publication Directory Overview — QSol‑Standard‑ZKProofs‑v1.0
QSol LLC — Harmonic Systems Research Division

1. Purpose of the Publication Directory
The publication/ directory contains all materials required to produce the canonical, signed, institutionally sealed release of:

QSol‑Standard‑ZKProofs‑v1.0

This directory defines:

the canonical PDF

the LaTeX source

the publication assets

the institutional seal

the banner

the logo

the publication pipeline

No canonical release may be produced without this directory.

2. Directory Structure
Code
publication/
  assets/
    canonical-seal.svg
    publication-banner.png
    qsol-logo.svg
  latex/
    annexes.tex
    cover.tex
    macros.tex
    main.tex
    toc.tex
  pdf/
    ZKProofs-v1.0.pdf
Each component has a specific institutional role.

3. Assets
3.1 canonical-seal.svg
The official QSol institutional seal.
Applied to the cover and final page of the PDF.

3.2 publication-banner.png
Used for repository presentation, website integration, and release headers.

3.3 qsol-logo.svg
The official QSol LLC logo.
Used on the cover page and in the PDF metadata.

Assets MUST NOT be altered without a MAJOR amendment.

4. LaTeX Source
The LaTeX directory contains the full source for the canonical PDF.

4.1 main.tex
The master document.
Includes all sections, annexes, macros, and structural elements.

4.2 cover.tex
Defines the canonical cover page, including:

QSol logo

canonical seal

version number

publication metadata

4.3 macros.tex
Defines:

canonical formatting

theorem environments

math macros

institutional styling

4.4 toc.tex
Defines the table of contents.

4.5 annexes.tex
Includes all annexes in canonical order.

All LaTeX files MUST be deterministic and build‑stable.

5. Canonical PDF
The file:

Code
publication/pdf/ZKProofs-v1.0.pdf
is the authoritative, canonical version of the Standard.

It MUST:

embed the version number

embed the publication date

embed the QSol logo

embed the canonical seal

match the Markdown source exactly

match the manifest exactly

be signed by QSol LLC

The PDF is the only legally binding version of the Standard.

6. Publication Pipeline
A canonical release MUST follow this sequence:

Update Markdown source

Update LaTeX source

Build canonical PDF

Generate hash manifest

Apply canonical seal

Sign release

Publish tagged version

Archive release notes

No step may be skipped.

7. Modification Rules
Changes to the publication directory follow the versioning rules:

PATCH — formatting fixes, asset compression, LaTeX cleanup

MINOR — new annexes, new sections, new publication assets

MAJOR — changes to seal, logo, publication structure, or PDF format

MAJOR changes require unanimous Governance Council approval.

8. Canonical Closure
This document defines the only valid structure for the publication directory.
All canonical releases MUST follow these rules.
