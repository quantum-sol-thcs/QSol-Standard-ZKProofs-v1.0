# Commitment Kernel — Commitment Scheme
QSol-Standard-ZKProofs-v1.0  
Harmonic Systems Research Division  
Status: Normative

---

## 1. Overview

This module defines the canonical commitment scheme interface for the
Commitment Kernel (CK). All profiles MUST implement a commitment scheme that
satisfies the properties defined in this document.

A commitment scheme provides two core operations:

- **Commit** — bind to a value while keeping it hidden  
- **Open** — reveal the value and prove correctness  

The CK defines the abstract interface; profiles instantiate concrete schemes
(e.g., KZG, Pedersen, IPA-based commitments).

---

## 2. Commitment Interface

A commitment scheme consists of the following algorithms:

### `Commit(pp, m, r) → C`

- `pp`: public parameters  
- `m`: message (field element, vector, or polynomial)  
- `r`: randomness  
- `C`: commitment  

The algorithm MUST be:

- deterministic given `(m, r)`,
- binding,
- hiding (computational or information-theoretic, profile-defined).

### `Open(pp, m, r) → π`

Produces an opening proof `π` that authenticates the committed message.

### `Verify(pp, C, m, π) → {0,1}`

Verification MUST return:

- `1` if `(C, m, π)` is valid  
- `0` otherwise  

Verification MUST be deterministic.

---

## 3. Binding and Hiding Requirements

### Binding

A scheme is binding if:



\[
\Pr[(m, r) \neq (m', r') \land \Commit(m, r) = \Commit(m', r')] = 0
\]



or negligible, depending on the profile.

### Hiding

A scheme is hiding if:



\[
\Commit(m, r) \approx \Commit(m', r')
\]



for all valid messages, under the profile’s security assumptions.

---

## 4. Polynomial Commitments

If the scheme commits to polynomials:

- the polynomial MUST be over \(\F[X]\),
- degree bounds MUST be explicit,
- evaluation proofs MUST be supported.

Profiles MUST specify:

- evaluation domain,
- opening strategy,
- batching rules.

---

## 5. Public Parameters

Public parameters MUST include:

- group generators or field modulus,
- SRS elements (if applicable),
- domain definitions,
- hash functions (if applicable).

Parameters MUST be:

- canonical,
- profile-specific,
- immutable after generation.

---

## 6. Security Requirements

A CK-compliant scheme MUST satisfy:

- **Binding**
- **Hiding**
- **Correctness**
- **Deterministic verification**
- **Profile-defined soundness assumptions**

---

## 7. References

- `opening-verification.md`
- AK reference modules
