# Commitment Kernel — Opening and Verification
QSol-Standard-ZKProofs-v1.0  
Harmonic Systems Research Division  
Status: Normative

---

## 1. Overview

This module defines the canonical opening and verification procedures for
commitment schemes within the Commitment Kernel (CK). All profiles MUST follow
these rules to ensure deterministic verifier behavior.

Opening proofs authenticate:

- the committed message,
- the evaluation of a polynomial at a point,
- or both (depending on the scheme).

---

## 2. Opening Procedure

### `Open(pp, m, r) → π`

The opening algorithm MUST:

1. Take the committed message `m`  
2. Use the randomness `r`  
3. Produce a proof `π` that binds `m` to the commitment  

For polynomial commitments, `Open` MAY include:

- evaluation point `x`,
- evaluation value `m(x)`,
- auxiliary proof elements.

All components MUST be deterministic given `(m, r)`.

---

## 3. Verification Procedure

### `Verify(pp, C, m, π) → {0,1}`

Verification MUST check:

1. The proof `π` is well-formed  
2. The commitment `C` corresponds to `m`  
3. All algebraic relations required by the profile hold  

Verification MUST be:

- deterministic,
- stateless,
- independent of prover-side randomness.

---

## 4. Polynomial Evaluation Proofs

If the scheme supports evaluation proofs:

### Opening



\[
\pi = \text{OpenEval}(P, x)
\]



### Verification

The verifier MUST check:



\[
\VerifyEval(C, x, y, \pi) = 1
\]



where:

- `C` is the commitment to polynomial `P`,
- `x` is the evaluation point,
- `y = P(x)`.

Profiles MUST define:

- batching rules,
- multi-point evaluation rules,
- domain restrictions.

---

## 5. Soundness Requirements

A CK-compliant opening system MUST satisfy:

- **Correctness:** valid openings always verify  
- **Soundness:** invalid openings fail except with negligible probability  
- **Determinism:** verification MUST NOT depend on implementation details  

---

## 6. Error Handling

Verification MUST return `0` if:

- the proof is malformed,
- the message is out of range,
- the commitment does not match,
- the evaluation is inconsistent.

No partial acceptance is permitted.

---

## 7. References

- `commitment-scheme.md`
- AK reference modules

