PLONKish‑381‑KZG Profile
Normative Profile — QSol‑Standard‑ZKProofs‑v1.0
QSol LLC — Harmonic Systems Research Division

1. Profile Identity
Profile Name: plonkish-381-kzg  
Profile Family: PLONKish
Curve / Field: BLS12‑381 scalar field
Commitment Scheme: KZG (Kate–Zaverucha–Goldberg)
Transcript Hash: Poseidon or Blake2s (profile‑specific)
Version: 1.0.0

This profile defines a deterministic, kernel‑pure PLONKish system using KZG commitments over BLS12‑381.

2. Algebraic Environment
The Algebra Kernel (AK) MUST operate over:

the BLS12‑381 scalar field

canonical field encoding (big‑endian, fixed‑width)

canonical polynomial encoding

canonical domain definitions

Supported operations:

field addition, subtraction, multiplication, inversion

polynomial evaluation

polynomial addition and multiplication

FFT/IFFT over supported domains

All witness‑dependent algebra MUST occur inside AK.

3. Commitment Scheme
This profile uses deterministic KZG commitments:

curve: BLS12‑381

commitment: G1

opening proof: G1

pairing check: e(C − f(τ)·G, G2) = e(π, τ·G2 − G2)

Requirements:

commitments MUST be deterministic

openings MUST be deterministic

verification MUST be deterministic

no randomness leakage

no off‑kernel algebra

Commitment operations MUST occur inside CK.

4. Transcript Rules
Transcript construction MUST follow:

canonical ordering

canonical encoding

domain separation for each phase

deterministic challenge derivation

Transcript phases:

Commit Phase

Evaluation Phase

Opening Phase

Verification Phase

Transcript operations MUST occur inside SK.

5. Mapping Rules
Mappings MUST follow PLONKish constraints:

gate constraints

copy constraints

permutation arguments

lookup arguments (if used)

quotient polynomial construction

evaluation at challenge points

Mapping invariants:

no off‑kernel computation

no nondeterminism

no hidden randomness

canonical polynomial construction

canonical domain selection

Mappings MUST NOT modify kernel rules.

6. Domain Separation Rules
Domain separators MUST be applied at:

commitment phase

evaluation phase

opening phase

verification phase

Each separator MUST be unique and canonical.

Example separators:

"PLONKISH_COMMIT"

"PLONKISH_EVAL"

"PLONKISH_OPEN"

"PLONKISH_VERIFY"

7. Determinism Model
This profile requires:

deterministic commitments

deterministic transcripts

deterministic polynomial construction

deterministic quotient computation

deterministic challenge derivation

deterministic opening proofs

Implementations MUST produce identical outputs across:

hardware

operating systems

compilers

optimization levels

8. CTS Requirements
Implementations MUST pass:

AK kernel tests

CK kernel tests

SK kernel tests

PLONKish mapping tests

PLONKish transcript tests

determinism tests

encoding tests

Profile‑specific CTS vectors MUST be used where applicable.

9. Security Considerations
This profile inherits security from:

BLS12‑381

KZG commitments

PLONKish constraint systems

Poseidon/Blake2s transcript hashing

Security requirements:

no trusted setup reuse across profiles

no randomness leakage

no off‑kernel computation

no transcript manipulation

no commitment malleability

10. Version Declaration
This profile conforms to:

Code
QSol‑Standard‑ZKProofs‑v1.0
Profile Version: 1.0.0
11. Canonical Closure
This document defines the only valid PLONKish‑381‑KZG profile for QSol‑Standard‑ZKProofs‑v1.0.
All implementations declaring this profile MUST follow these rules exactly.
