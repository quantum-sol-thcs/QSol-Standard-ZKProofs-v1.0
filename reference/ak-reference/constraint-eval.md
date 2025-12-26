# Algebra Kernel — Constraint Evaluation
QSol-Standard-ZKProofs-v1.0  
Harmonic Systems Research Division  
Status: Normative

---

## 1. Overview

This module defines the canonical rules for evaluating algebraic constraints
within the Algebra Kernel (AK). All constraint systems MUST follow these rules
to ensure deterministic prover and verifier behavior across all profiles.

Constraint evaluation is defined over a field \(\F\) and operates on:
- witness assignments,
- selector polynomials,
- constraint polynomials,
- and evaluation points.

---

## 2. Constraint System Model

A constraint system consists of:
- A set of variables \(x_1, \dots, x_n\)
- A set of constraints \(C_1, \dots, C_m\)
- A field \(\F\)
- A witness assignment \(w : \{1,\dots,n\} \to \F\)

Each constraint \(C_i\) is a polynomial over \(\F[x_1,\dots,x_n]\).

A witness assignment satisfies the system iff:



\[
C_i(w_1,\dots,w_n) = 0 \quad \forall i.
\]



---

## 3. Selector-Based Evaluation

Selectors are polynomials \(s_i(X)\) used to activate or deactivate constraints.

A constraint is active at point \(X\) iff:



\[
s_i(X) = 1.
\]



The evaluated constraint polynomial is:



\[
E_i(X) = s_i(X) \cdot C_i(w(X)).
\]



All profiles MUST ensure:



\[
E_i(X) = 0 \quad \forall X \in \text{domain}.
\]



---

## 4. Domain and Evaluation Rules

The evaluation domain MUST be:
- a multiplicative subgroup of \(\F^\times\), or
- an affine coset thereof.

All constraints MUST be evaluated over the full domain.

---

## 5. Soundness Requirements

A constraint system MUST satisfy:
- **Completeness:** valid witnesses satisfy all constraints.
- **Soundness:** invalid witnesses violate at least one constraint on the domain.
- **Determinism:** evaluation MUST NOT depend on implementation details.

---

## 6. References

- `field-ops.md`
- `polynomial-ops.md`
