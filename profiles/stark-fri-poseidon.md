STARK‑FRI‑Poseidon Profile
Normative Profile — QSol‑Standard‑ZKProofs‑v1.0
QSol LLC — Harmonic Systems Research Division

1. Profile Identity
Profile Name: stark-fri-poseidon  
Profile Family: STARK
Field: Large prime field (profile‑specific modulus)
Commitment Scheme: FRI (Fast Reed–Solomon IOPP)
Transcript Hash: Poseidon
Version: 1.0.0

This profile defines a deterministic, kernel‑pure STARK system using FRI commitments and Poseidon hashing.

2. Algebraic Environment
The Algebra Kernel (AK) MUST operate over:

a large prime field (≥ 2²⁵⁴)

canonical field encoding

canonical polynomial encoding

canonical evaluation domains

Supported operations:

field arithmetic

polynomial evaluation

polynomial addition and multiplication

low‑degree extension (LDE)

evaluation domain generation

All witness‑dependent algebra MUST occur inside AK.

3. Commitment Scheme — FRI
This profile uses deterministic FRI commitments, consisting of:

LDE of the trace

Merkle commitments

query positions

decommitments

low‑degree tests

Requirements:

Merkle roots MUST be deterministic

query selection MUST be transcript‑driven

decommitments MUST be canonical

no randomness leakage

no off‑kernel algebra

All commitment operations MUST occur inside CK.

4. Transcript Rules
Transcript construction MUST follow:

canonical ordering

canonical encoding

Poseidon hashing

domain separation for each round

deterministic challenge derivation

Transcript phases:

Trace Commitment Phase

Constraint Commitment Phase

FRI Round Phases

Query Phase

Verification Phase

Transcript operations MUST occur inside SK.

5. Mapping Rules
Mappings MUST follow STARK constraints:

trace generation

boundary constraints

transition constraints

composition polynomial construction

LDE expansion

FRI folding steps

Mapping invariants:

no off‑kernel computation

no nondeterminism

no hidden randomness

canonical polynomial construction

canonical domain selection

Mappings MUST NOT modify kernel rules.

6. Domain Separation Rules
Domain separators MUST be applied at:

trace commitment

constraint commitment

each FRI round

query phase

verification phase

Each separator MUST be unique and canonical.

Example separators:

"STARK_TRACE"

"STARK_CONSTRAINT"

"STARK_FRI_ROUND_i"

"STARK_QUERY"

"STARK_VERIFY"

7. Determinism Model
This profile requires:

deterministic Merkle commitments

deterministic transcript hashing

deterministic FRI folding

deterministic query selection

deterministic decommitments

deterministic verification

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

STARK mapping tests

FRI commitment tests

determinism tests

encoding tests

Profile‑specific CTS vectors MUST be used where applicable.

9. Security Considerations
This profile inherits security from:

the prime field

Merkle commitments

FRI low‑degree testing

Poseidon hashing

transcript determinism

Security requirements:

no randomness leakage

no off‑kernel computation

no transcript manipulation

no commitment malleability

no weakening of LDE or FRI parameters

10. Version Declaration
This profile conforms to:

Code
QSol‑Standard‑ZKProofs‑v1.0
Profile Version: 1.0.0
11. Canonical Closure
This document defines the only valid STARK‑FRI‑Poseidon profile for QSol‑Standard‑ZKProofs‑v1.0.
All implementations declaring this profile MUST follow these rules exactly.
