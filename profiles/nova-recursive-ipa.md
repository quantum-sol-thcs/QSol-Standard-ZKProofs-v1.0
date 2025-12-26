Nova‑Recursive‑IPA Profile
Normative Profile — QSol‑Standard‑ZKProofs‑v1.0
QSol LLC — Harmonic Systems Research Division

1. Profile Identity
Profile Name: nova-recursive-ipa  
Profile Family: Recursive (Nova‑style)
Field: Large prime field (profile‑specific modulus)
Commitment Scheme: Pedersen Vector Commitments
Transcript Hash: Poseidon or Blake2s
Version: 1.0.0

This profile defines a deterministic, kernel‑pure recursive folding system using:

an IPA‑based commitment scheme

a deterministic transcript

a canonical folding operation

a recursion‑safe mapping model

It is designed for incremental verifiable computation (IVC) and recursive proof composition.

2. Algebraic Environment
The Algebra Kernel (AK) MUST operate over:

a large prime field (≥ 2²⁵⁴)

canonical field encoding

canonical vector encoding

canonical polynomial encoding

Supported operations:

field arithmetic

vector inner products

multi‑scalar multiplication (MSM)

polynomial evaluation

folding operations (profile‑specific)

All witness‑dependent algebra MUST occur inside AK.

3. Commitment Scheme — Pedersen (Recursive‑Safe)
This profile uses deterministic Pedersen vector commitments, with recursion‑safe constraints:

commitment: 
𝐶
=
∑
𝑖
𝑣
𝑖
𝐺
𝑖
+
𝑟
𝐻

randomness 
𝑟
 MUST be deterministic and transcript‑bound

generators MUST be canonical and recursion‑safe

MSM MUST be canonical

Requirements:

commitments MUST be deterministic

openings MUST be deterministic

folding commitments MUST be deterministic

no randomness leakage

no off‑kernel algebra

All commitment operations MUST occur inside CK.

4. Transcript Rules
Transcript construction MUST follow:

canonical ordering

canonical encoding

domain separation

deterministic challenge derivation

recursion‑safe transcript transitions

Transcript phases:

Base Step Commitment Phase

Folding Step Phase

Recursive Accumulator Phase

Verification Phase

Transcript operations MUST occur inside SK.

5. Mapping Rules
Mappings MUST follow Nova‑style recursive constraints:

base step mapping

step circuit mapping

accumulator mapping

folding mapping

challenge‑driven recursion

canonical accumulator updates

Mapping invariants:

no off‑kernel computation

no nondeterminism

no hidden randomness

canonical accumulator encoding

canonical folding operations

recursion MUST be transcript‑driven

Mappings MUST NOT modify kernel rules.

6. Folding Rules
The recursive folding operation MUST be:

deterministic

canonical

kernel‑pure

transcript‑driven

Folding MUST:

combine two commitments into one

combine two witnesses into one

update the accumulator deterministically

derive challenges from the transcript

preserve soundness

Folding MUST NOT:

introduce randomness

depend on environment

depend on execution order

7. Domain Separation Rules
Domain separators MUST be applied at:

base step

each folding step

accumulator update

final verification

Each separator MUST be unique and canonical.

Example separators:

"NOVA_BASE"

"NOVA_FOLD_i"

"NOVA_ACCUMULATOR"

"NOVA_VERIFY"

8. Determinism Model
This profile requires:

deterministic Pedersen commitments

deterministic transcript hashing

deterministic folding

deterministic accumulator updates

deterministic challenge derivation

deterministic MSM

Implementations MUST produce identical outputs across:

hardware

operating systems

compilers

optimization levels

9. CTS Requirements
Implementations MUST pass:

AK kernel tests

CK kernel tests

SK kernel tests

recursive mapping tests

folding tests

accumulator tests

determinism tests

encoding tests

Profile‑specific CTS vectors MUST be used where applicable.

10. Security Considerations
This profile inherits security from:

the prime field

Pedersen commitments

IPA soundness

Nova‑style folding soundness

transcript determinism

Security requirements:

no randomness leakage

no off‑kernel computation

no transcript manipulation

no commitment malleability

no weakening of folding parameters

accumulator MUST be canonical and binding

11. Version Declaration
This profile conforms to:

Code
QSol‑Standard‑ZKProofs‑v1.0
Profile Version: 1.0.0
12. Canonical Closure
This document defines the only valid Nova‑Recursive‑IPA profile for QSol‑Standard‑ZKProofs‑v1.0.
All implementations declaring this profile MUST follow these rules exactly.
