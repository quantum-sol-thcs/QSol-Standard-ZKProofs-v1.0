IPA‑Pedersen Profile
Normative Profile — QSol‑Standard‑ZKProofs‑v1.0
QSol LLC — Harmonic Systems Research Division

1. Profile Identity
Profile Name: ipa-pedersen  
Profile Family: IPA (Inner‑Product Argument)
Field: Large prime field (profile‑specific modulus)
Commitment Scheme: Pedersen Vector Commitments
Transcript Hash: Poseidon or Blake2s
Version: 1.0.0

This profile defines a deterministic, kernel‑pure IPA system using Pedersen vector commitments and transcript‑driven challenge derivation.

2. Algebraic Environment
The Algebra Kernel (AK) MUST operate over:

a large prime field (≥ 2²⁵⁴)

canonical field encoding

canonical vector encoding

canonical polynomial encoding (for IPA reduction)

Supported operations:

field arithmetic

vector inner products

multi‑scalar multiplication (MSM)

polynomial evaluation (for IPA reduction)

All witness‑dependent algebra MUST occur inside AK.

3. Commitment Scheme — Pedersen
This profile uses deterministic Pedersen vector commitments:

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

generators 
𝐺
𝑖
,
𝐻
 MUST be canonical and profile‑defined

Requirements:

commitments MUST be deterministic

openings MUST be deterministic

MSM MUST be canonical

no randomness leakage

no off‑kernel algebra

All commitment operations MUST occur inside CK.

4. Transcript Rules
Transcript construction MUST follow:

canonical ordering

canonical encoding

domain separation

deterministic challenge derivation

Transcript phases:

Commit Phase

Round Reduction Phase

Inner‑Product Folding Phase

Verification Phase

Transcript operations MUST occur inside SK.

5. Mapping Rules
Mappings MUST follow IPA constraints:

vector commitment mapping

inner‑product reduction

logarithmic‑round folding

challenge‑driven recursion

final scalar verification

Mapping invariants:

no off‑kernel computation

no nondeterminism

no hidden randomness

canonical vector encoding

canonical folding operations

Mappings MUST NOT modify kernel rules.

6. Domain Separation Rules
Domain separators MUST be applied at:

commitment phase

each IPA round

final verification

Each separator MUST be unique and canonical.

Example separators:

"IPA_COMMIT"

"IPA_ROUND_i"

"IPA_VERIFY"

7. Determinism Model
This profile requires:

deterministic Pedersen commitments

deterministic transcript hashing

deterministic IPA folding

deterministic challenge derivation

deterministic MSM

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

IPA mapping tests

IPA folding tests

determinism tests

encoding tests

Profile‑specific CTS vectors MUST be used where applicable.

9. Security Considerations
This profile inherits security from:

the prime field

Pedersen commitments

inner‑product argument soundness

transcript determinism

Security requirements:

no randomness leakage

no off‑kernel computation

no transcript manipulation

no commitment malleability

no weakening of IPA parameters

10. Version Declaration
This profile conforms to:

Code
QSol‑Standard‑ZKProofs‑v1.0
Profile Version: 1.0.0
11. Canonical Closure
This document defines the only valid IPA‑Pedersen profile for QSol‑Standard‑ZKProofs‑v1.0.
All implementations declaring this profile MUST follow these rules exactly.
