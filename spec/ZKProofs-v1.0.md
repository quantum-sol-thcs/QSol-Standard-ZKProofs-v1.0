# QSol-Standard-ZKProofs-v1.0  
Harmonic Systems Research Division  
QSol LLC  
Status: Normative

---

## 1. Introduction

The **QSol-Standard-ZKProofs-v1.0** specification defines a unified,
kernel‑centric architecture for zero‑knowledge proof systems. The Standard
provides:

- a canonical Algebra Kernel (AK)  
- a canonical Commitment Kernel (CK)  
- a canonical Transcript Kernel (SK)  
- a profile system for concrete instantiations  
- conformance and test vector requirements  

This document is the normative source for all kernel definitions.

---

## 2. Kernel Architecture Overview

The Standard defines three foundational kernels:

### **Algebra Kernel (AK)**
Defines:
- field operations  
- polynomial operations  
- constraint evaluation  
- evaluation domains  

### **Commitment Kernel (CK)**
Defines:
- commitment interface  
- polynomial commitments  
- opening and verification rules  

### **Transcript Kernel (SK)**
Defines:
- transcript engine  
- challenge derivation  
- Fiat–Shamir transform  

Each kernel is self‑contained and profile‑agnostic.

---

## 3. Profiles

Profiles instantiate the kernels with concrete parameters.  
This version includes:

- plonkish‑381‑kzg  
- ipa‑pedersen  
- nova‑recursive‑ipa  
- stark‑fri‑poseidon  
- profile‑template  

Profiles MUST specify:
- field modulus  
- domain rules  
- commitment scheme  
- transcript hash  
- evaluation strategy  

---

## 4. Conformance Requirements

A conforming implementation MUST:

- implement all three kernels  
- follow all normative rules  
- pass the Kernel Test Vector Suite  
- satisfy profile‑specific constraints  

---

## 5. Annexes

The Standard includes:

- Annex A — Kernel Compliance (Normative)  
- Annex B — Kernel Test Vector Suite (Normative)  
- Annex C — Profile Definitions (Normative)  
- Annex D — Security Notes (Non‑Normative)  
- Annex E — Change Log and Version History (Non‑Normative)  

---

## 6. Versioning

This document corresponds to:

**Version: v1.0.0**  
**Status: Published**  

