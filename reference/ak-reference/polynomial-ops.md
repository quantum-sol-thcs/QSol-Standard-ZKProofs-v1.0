# Algebra Kernel — Polynomial Operations
QSol-Standard-ZKProofs-v1.0  
Harmonic Systems Research Division  
Status: Normative

---

## 1. Overview

This module defines the polynomial operations required by the Algebra Kernel
(AK). All polynomial arithmetic MUST be performed over the field \(\F\).

---

## 2. Polynomial Representation

A polynomial \(P(X)\) MUST be represented as:



\[
P(X) = \sum_{i=0}^{d} a_i X^i
\]



with coefficients \(a_i \in \F\).

Representations MUST be:
- dense or sparse (profile‑defined),
- deterministic,
- canonical.

---

## 3. Canonical Operations

### Addition


\[
(P + Q)(X) = P(X) + Q(X)
\]



### Subtraction


\[
(P - Q)(X) = P(X) - Q(X)
\]



### Multiplication


\[
(P \cdot Q)(X) = P(X) \cdot Q(X)
\]



### Evaluation


\[
P(w) = \sum_{i=0}^{d} a_i w^i
\]



### Division (Exact)
If \(Q\) divides \(P\):



\[
P = Q \cdot H
\]



Profiles MUST specify whether exact division is required.

---

## 4. FFT and Evaluation Domains

If a profile uses FFT‑based evaluation:
- the domain MUST be a multiplicative subgroup,
- the generator MUST be fixed and canonical,
- bit‑reversal ordering MUST be explicitly defined.

---

## 5. Zero‑Knowledge Masking

If masking polynomials are used:
- they MUST be sampled uniformly from \(\F[X]\),
- degree bounds MUST be profile‑defined,
- masking MUST NOT affect soundness.

---

## 6. References

- `field-ops.md`
- `constraint-eval.md`

