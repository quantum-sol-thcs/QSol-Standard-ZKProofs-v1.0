Annex D — Hash Manifest Specification
Normative Annex — QSol‑Standard‑ZKProofs‑v1.0
QSol LLC — Harmonic Systems Research Division

D.1 Purpose and Scope
This annex defines the Hash Manifest, a canonical integrity artifact used to:

authenticate official releases

verify repository integrity

detect tampering or corruption

bind the canonical PDF to the Markdown source

support long‑term archival preservation

enable certification and audit workflows

The Hash Manifest is normative.
All official releases MUST include a complete and correct manifest.

D.2 Manifest Location
The manifest MUST be located at:

Code
metadata/hash-manifest.txt
No other location is permitted.

D.3 Hash Function Requirements
All canonical hashes MUST use:

SHA3‑256 for file‑level hashing

SHA3‑512 for optional extended integrity bundles

SHA2, BLAKE2, Keccak‑f variants, or profile‑specific hashes MAY be included as supplemental entries but MUST NOT replace SHA3‑256.

D.4 Manifest Format
The manifest is a plain‑text file with one entry per line:

Code
<sha3-256-hex>  <relative-path>
Example:

Code
a3f9c1e4...  spec/ZKProofs-v1.0.md
b8d4e2c9...  publication/pdf/ZKProofs-v1.0.pdf
Rules:

Hex MUST be lowercase

Paths MUST be relative to repository root

No trailing whitespace

No comments

No blank lines

The manifest MUST be stable across platforms.

D.5 Files That MUST Be Included
The following MUST appear in the manifest:

spec/ZKProofs-v1.0.md

all annexes

all CTS specification files

all JSON test vectors

all certification documents

all governance documents

all profiles

all reference implementations

the canonical PDF

all LaTeX sources

all assets

all metadata files (except the manifest itself)

The manifest MUST NOT include:

.git directories

editor temporary files

build artifacts

local environment files

D.6 Canonical PDF Binding
The canonical PDF:

Code
publication/pdf/ZKProofs-v1.0.pdf
MUST be included in the manifest.

This binds the PDF to:

the Markdown source

the annexes

the CTS

the governance rules

the profiles

the publication assets

This ensures that the PDF is cryptographically anchored to the entire Standard.

D.7 Release Integrity Requirements
Before publication, QSol LLC MUST:

Generate the manifest

Verify all entries

Sign the manifest using institutional keys

Publish signatures under:

Code
metadata/signatures/
Publish the manifest with the release

Any mismatch between manifest and repository contents invalidates the release.

D.8 Signature Requirements
Signatures MUST use:

Ed25519 (primary)

P‑256 (secondary)

Each signature file MUST contain:

signature bytes (base64)

key identifier

manifest version

timestamp

Example:

Code
sig-ed25519-v1.txt
sig-p256-v1.txt
Signatures MUST NOT be embedded inside the manifest.

D.9 Manifest Versioning
The manifest version MUST match the Standard version:

1.0.0 for the initial release

incremented on every MINOR or MAJOR version

regenerated on every PATCH version

The manifest MUST NOT be reused across versions.

D.10 Auditor Requirements
Auditors MUST:

verify all hashes

verify all signatures

confirm manifest completeness

confirm canonical PDF binding

confirm no extraneous files exist

confirm no required files are missing

Failure of any check constitutes non‑conformance.

D.11 Amendment Boundary
This annex is normative.
Any modification requires:

governance approval

version increment

canonical republication

D.12 Canonical Closure
This annex defines the only valid hash manifest format for QSol‑Standard‑ZKProofs‑v1.0.
All official releases MUST comply with this specification.
