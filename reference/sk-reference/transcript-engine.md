# Transcript Kernel — Transcript Engine
QSol-Standard-ZKProofs-v1.0  
Harmonic Systems Research Division  
Status: Normative

---

## 1. Overview

This module defines the canonical transcript engine used by the Transcript
Kernel (SK). The transcript engine provides:

- absorption of items  
- domain-separated challenge derivation  
- deterministic hashing  
- reproducible Fiat–Shamir behavior  

All profiles MUST implement this engine.

---

## 2. Transcript Interface

A transcript engine MUST provide the following operations:

### `Init(pp) → T`
Initializes a transcript with profile-defined parameters.

### `Absorb(T, x)`
Absorbs an item `x` into the transcript.

Items MAY include:

- field elements  
- group elements  
- commitments  
- messages  
- byte strings  

All items MUST be encoded canonically before absorption.

### `Challenge(T, label) → c`
Derives a challenge using the rules in `challenge-derivation.md`.

---

## 3. Canonical Encoding Rules

Before absorption, each item MUST be encoded using:

- fixed-width field encodings  
- canonical group encodings  
- length-prefixed byte strings  
- profile-defined commitment encodings  

Encodings MUST be:

- unambiguous  
- deterministic  
- platform-independent  

---

## 4. Hash Function Requirements

The transcript engine MUST use a hash function that is:

- collision-resistant  
- deterministic  
- domain-separated  
- profile-defined  

Examples include:

- Poseidon  
- Blake2s  
- SHA-256  
- Rescue  

The hash function MUST NOT change within a profile.

---

## 5. Fiat–Shamir Transform

The transcript engine implements the Fiat–Shamir transform by:

1. Absorbing prover messages  
2. Deriving challenges  
3. Feeding challenges back into the protocol  

This MUST produce a non-interactive protocol equivalent to the interactive one.

---

## 6. Determinism Requirements

The transcript engine MUST be deterministic with respect to:

- input order  
- encoding rules  
- hash function  
- domain separators  

It MUST NOT depend on:

- memory layout  
- thread scheduling  
- randomness  
- hardware architecture  

---

## 7. Error Handling

The transcript MUST reject:

- malformed encodings  
- invalid group elements  
- out-of-range field elements  

Errors MUST be fatal and MUST NOT produce partial transcript states.

---

## 8. References

- `challenge-derivation.md`
- AK and CK reference modules

