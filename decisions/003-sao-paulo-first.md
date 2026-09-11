# PDR-003: São Paulo First

**Status:** Decided  
**Date:** 2026-Q1

## Decision

The MVP targets autonomous psychologists in São Paulo/SP only. Other states are not in scope for the initial launch.

## Context

Fiscal obligations in Brazil have two layers: federal (same nationwide) and municipal (varies by city and state). The federal layer — Carnê-Leão, INSS, DIRPF — is identical for all PF psychologists regardless of location. The municipal layer — CCM, ISS, local health authority registrations — varies significantly.

## Decision Rationale

Building a product that handles municipal obligations accurately requires deep knowledge of each city's specific rules. São Paulo was chosen because:

1. It has the largest concentration of autonomous psychologists in Brazil (CRP-SP is the largest regional psychology council by membership)
2. The founding team has direct access to the SP psychologist network for user research and beta recruitment
3. São Paulo's municipal rules (CCM, ISS) are well-documented and stable

Starting with one city allows us to build a complete, accurate product for a well-defined audience rather than a partial product for everyone.

## Expansion Path

Rio de Janeiro and Minas Gerais have similar obligation profiles to São Paulo and are the natural next states. Expansion is primarily a catalog update — new municipal rules, different CCM equivalents — not a product rebuild.

## Trade-offs Accepted

- Psychologists in other states cannot use Compasso in this phase
- Some users who discover the product organically may be turned away
