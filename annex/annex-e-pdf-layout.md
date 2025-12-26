Annex E — Canonical PDF Layout & Publication Rules
Normative Annex — QSol‑Standard‑ZKProofs‑v1.0
QSol LLC — Harmonic Systems Research Division

E.1 Purpose and Scope
This annex defines the canonical PDF layout for the ZKProofs‑v1.0 Standard.
The PDF is the authoritative citation artifact for all public, academic, and institutional references.

This annex ensures:

consistent publication quality

long‑term archival stability

institutional identity preservation

deterministic rendering across platforms

reproducible PDF builds

All official PDFs MUST comply with this annex.

E.2 Canonical PDF Location
The canonical PDF MUST be located at:

Code
publication/pdf/ZKProofs-v1.0.pdf
No other file name or path is permitted.

E.3 PDF Generation Requirements
The canonical PDF MUST be generated from:

publication/latex/main.tex

publication/latex/macros.tex

publication/latex/cover.tex

publication/latex/toc.tex

publication/latex/annexes.tex

The PDF MUST be built using:

LaTeX (XeLaTeX or LuaLaTeX)

deterministic font embedding

deterministic image embedding

stable page numbering

The PDF MUST NOT depend on:

external fonts

external URLs

remote assets

system‑dependent packages

E.4 Cover Page Requirements
The cover page MUST include:

QSol LLC institutional identity

Standard title:
“ZKProofs‑v1.0: The Kernel‑Constitutional Standard for Zero‑Knowledge Proof Systems”

Publication date

Version number

Canonical seal (canonical-seal.svg)

QSol logo (qsol-logo.svg)

The cover MUST NOT include:

draft markings

watermarks

unofficial logos

personal branding

E.5 Table of Contents Requirements
The PDF MUST include a fully expanded table of contents with:

section numbers

subsection numbers

annex references

page numbers

The TOC MUST be generated automatically from LaTeX.

E.6 Section Layout Requirements
All sections MUST follow:

hierarchical numbering (1–36)

consistent heading levels

1.15–1.25 line spacing

justified text

embedded fonts

no widows or orphans

Margins MUST be:

1.0 inch left

1.0 inch right

1.0 inch top

1.0 inch bottom

E.7 Annex Layout Requirements
Annexes MUST:

appear after Section 36

be labeled Annex A, Annex B, …

use separate page numbering (A‑1, A‑2, …)

include titles matching repository filenames

include normative/non‑normative labels

Annexes MUST NOT be interleaved with the main specification.

E.8 Asset Embedding Requirements
The following assets MUST be embedded:

Code
publication/assets/canonical-seal.svg
publication/assets/qsol-logo.svg
publication/assets/publication-banner.png
All assets MUST be:

embedded as vector (SVG) when possible

embedded as PNG only when rasterization is required

included at 300 DPI minimum

No external image references are permitted.

E.9 Page Numbering Requirements
The PDF MUST use:

Roman numerals (i, ii, iii…) for front matter

Arabic numerals (1, 2, 3…) for main matter

Annex numbering (A‑1, B‑1…) for annexes

Page numbering MUST be continuous within each region.

E.10 Hyperlink & Metadata Requirements
The PDF MUST include:

internal hyperlinks for TOC entries

internal hyperlinks for annex references

embedded metadata:

Code
Title: ZKProofs-v1.0 Standard
Author: QSol LLC — Harmonic Systems Research Division
Subject: Zero-Knowledge Proof Systems Standard
Keywords: ZKProofs, QSol, Kernel-Constitutional Architecture
The PDF MUST NOT include:

external hyperlinks

tracking metadata

authoring tool metadata

E.11 Canonical PDF Hashing
The canonical PDF MUST be included in:

Code
metadata/hash-manifest.txt
using SHA3‑256.

Any change to the PDF requires:

regeneration of the manifest

regeneration of signatures

version increment (PATCH, MINOR, or MAJOR)

E.12 Publication Integrity Requirements
Before publication, QSol LLC MUST:

Build the PDF deterministically

Verify all embedded assets

Verify all fonts are embedded

Confirm page numbering

Confirm annex ordering

Hash the PDF

Sign the manifest

Publish the PDF and signatures

Any deviation invalidates the release.

E.13 Amendment Boundary
This annex is normative.
Any modification requires:

governance approval

version increment

canonical republication

E.14 Canonical Closure
This annex defines the only valid PDF layout for QSol‑Standard‑ZKProofs‑v1.0.
All official publications MUST comply with this specification.
