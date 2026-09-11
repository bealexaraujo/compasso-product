# PDR-002: PF Only — No MEI or CNPJ in MVP Scope

**Status:** Decided  
**Date:** 2026-Q1

## Decision

Compasso's MVP serves exclusively Pessoa Física (PF) autonomous professionals. MEI and CNPJ regimes are out of scope.

## Context

Brazilian psychologists can operate under three fiscal regimes: PF autônoma, MEI, or CNPJ (typically via a service company). Each regime has a completely different obligation structure, tax calculation method, and regulatory environment.

## Options Considered

**Serve all three regimes from the start**
- Larger addressable market at launch
- Requires building and maintaining three distinct obligation engines
- Increases onboarding complexity and support surface

**Serve PF only**
- Smaller initial market, but well-defined and homogeneous
- Single obligation engine to build and validate
- Clear user profile: solo practitioner, no employees, no accounting firm

**Serve PF + MEI**
- MEI has a simpler obligation structure (DAS monthly, DASN annually)
- But MEI is explicitly prohibited for psychologists by CFP regulations — this eliminates the option entirely for our target user

## Decision Rationale

MEI is legally prohibited for psychologists (CFP Resolution). That eliminates the middle option.

CNPJ professionals are a different story — but not our target. In Brazil, once a professional opens a CNPJ, they are legally required to work with a licensed accountant (contador). That obligation creates a natural support system: the accountant manages their fiscal compliance for them.

PF professionals have no such obligation. They are not required to hire an accountant — and most don't, because it's expensive relative to their income at early career stage. That is exactly where the problem starts. No accountant, no fiscal education after graduation, no tools built for their specific situation. They accumulate obligations they don't fully understand and pay fines they didn't know were coming.

Compasso exists in that gap: the PF professional who cannot afford an accountant and doesn't have one, but still has real fiscal obligations to manage.

## Trade-offs Accepted

- Users who operate under CNPJ cannot use Compasso in this phase — but they already have an accountant
- Some psychologists work across regimes (PF for some patients, company for others) — we do not serve hybrid scenarios
