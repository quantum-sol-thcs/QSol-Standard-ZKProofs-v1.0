# Transcript Kernel — Challenge Derivation
QSol-Standard-ZKProofs-v1.0  
Harmonic Systems Research Division  
Status: Normative

---

## 1. Overview

This module defines the canonical challenge-derivation rules for the
Transcript Kernel (SK). All profiles MUST use these rules to ensure
deterministic, reproducible Fiat–Shamir challenge generation.

Challenge derivation transforms transcript state into field elements using a
domain-separated hash function.

---

## 2. Transcript State

The transcript maintains an ordered sequence of absorbed items:

- field elements  
- group elements  
- commitments  
- messages  
- domain separators  

The transcript state MUST be:

- append-only  
- deterministic  
- canonical in encoding  

No item may be removed or reordered.

---

## 3. Domain Separation

Every challenge MUST be derived under a domain separator:



\[
\text{DS} = \text{“challenge\_label”}
\]



Profiles MUST define:

- the label string  
- encoding rules  
- whether labels are hashed directly or length-prefixed  

Domain separation MUST prevent cross-protocol collisions.

---

## 4. Challenge Derivation Procedure

Given transcript state \(T\) and domain separator \(DS\):

1. Append `DS` to the transcript  
2. Hash the full transcript state  
3. Interpret the hash output as a field element  
4. Reduce modulo the field modulus if necessary  

Formally:



\[
c = H(T \parallel DS) \bmod |\F|
\]



The hash function MUST be:

- collision-resistant  
- deterministic  
- profile-defined (e.g., Poseidon, SHA-256, Blake2s)  

---

## 5. Multi-Challenge Derivation

If multiple challenges are required:



\[
c_i = H(T \parallel DS \parallel i) \bmod |\F|
\]



The index MUST be encoded canonically.

---

## 6. Reproducibility Requirements

Challenge derivation MUST be:

- deterministic across all implementations  
- independent of memory layout  
- independent of platform endianness  
- independent of prover randomness  

---

## 7. References

- `transcript-engine.md`
- AK and CK reference modules
