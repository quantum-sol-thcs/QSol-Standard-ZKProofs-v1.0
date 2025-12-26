# Algebra Kernel — Field Operations
QSol-Standard-ZKProofs-v1.0  
Harmonic Systems Research Division  
Status: Normative

---

## 1. Overview

This module defines the canonical field operations required by the Algebra
Kernel (AK). All profiles MUST implement these operations over a finite field
\(\F\) of prime or prime-power order.

---

## 2. Field Definition

A field \(\F\) MUST support:

- Addition  
- Subtraction  
- Multiplication  
- Inversion  
- Zero and one elements  

All operations MUST be total and deterministic.

---

## 3. Canonical Operations

### Addition


\[
a + b \in \F
\]



### Subtraction


\[
a - b \in \F
\]



### Multiplication


\[
a \cdot b \in \F
\]



### Inversion


\[
a^{-1} \quad \text{MUST be defined for all } a \neq 0.
\]



### Zero and One


\[
0_\F,\; 1_\F
\]



---

## 4. Equality and Comparison

Equality MUST be bit‑exact:



\[
a = b \iff \text{their canonical encodings match}.
\]



No ordering is required or permitted.

---

## 5. Encoding Requirements

Field elements MUST have:
- a canonical byte encoding,
- a canonical bitstring encoding,
- no ambiguity or multiple representations.

Profiles MUST specify:
- modulus,
- encoding endianness,
- reduction rules.

---

## 6. References

- `polynomial-ops.md`
- `constraint-eval.md`

