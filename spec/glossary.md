# QSol-Standard-ZKProofs-v1.0 — Glossary  
Harmonic Systems Research Division  
Status: Normative

---

## Algebra Kernel Terms

**Field (\F)**  
A finite field used for all algebraic operations.

**Polynomial**  
A function \(P(X) = \sum a_i X^i\) with coefficients in \(\F\).

**Constraint**  
A polynomial equation that MUST evaluate to zero for valid witnesses.

---

## Commitment Kernel Terms

**Commitment**  
A binding, hiding cryptographic commitment to a message or polynomial.

**Opening Proof**  
A proof that a commitment corresponds to a specific message or evaluation.

---

## Transcript Kernel Terms

**Transcript**  
An append‑only state used to derive Fiat–Shamir challenges.

**Challenge**  
A field element derived from transcript state and domain separation.

---

## Profile Terms

**Profile**  
A concrete instantiation of the kernels with fixed parameters.

**Domain**  
The evaluation set used for constraint checking or FFT operations.

---

## Conformance Terms

**Test Vector**  
A deterministic input/output pair used to verify correctness.

**Normative**  
Content that MUST be followed.

**Non‑Normative**  
Content that is explanatory or optional.

