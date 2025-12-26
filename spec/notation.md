# QSol-Standard-ZKProofs-v1.0 — Notation  
Harmonic Systems Research Division  
Status: Normative

---

## 1. Fields and Sets

- \(\F\) — finite field  
- \(\Z\) — integers  
- \(\N\) — natural numbers  
- \(\G\), \(\Hh\) — groups  

---

## 2. Vectors and Matrices

- \(\vecx, \vecy, \vecz\) — vectors  
- \(\matA, \matB\) — matrices  

---

## 3. Polynomials

- \(P(X)\) — polynomial in variable \(X\)  
- \(\deg(P)\) — degree of polynomial  
- \(P(w)\) — evaluation at point \(w\)  

---

## 4. Operators

- \(\inner{a}{b}\) — inner product  
- \(\norm{x}\) — norm  
- \(\Span(S)\) — span of set \(S\)  
- \(\poly(n)\) — polynomial in \(n\)  
- \(\negl(n)\) — negligible in \(n\)  

---

## 5. Cryptographic Notation

- \(\Commit(m)\) — commitment to message \(m\)  
- \(\Prove(\cdot)\) — prover algorithm  
- \(\Verify(\cdot)\) — verifier algorithm  
- \(\Transcript\) — transcript engine  

---

## 6. Domain Separation

Domain separators are written as:



\[
\text{DS} = \text{“label”}
\]



and MUST be encoded canonically.

