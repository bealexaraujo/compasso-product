# PDR-005: Proof Required — No Self-Reporting

**Status:** Decided  
**Date:** 2026-Q1

## Decision

An obligation is only marked complete when a proof document is uploaded and validated by the agent, or explicitly confirmed via a dedicated button for obligations that do not generate documents. Self-reporting ("I paid it, trust me") is not accepted.

## Context

We needed to define what "done" means for an obligation. The simplest approach would be a checkbox the user ticks. The more complex approach requires actual proof.

## Options Considered

**Self-reporting (checkbox)**
- Minimal friction for the user
- No document processing required
- No way to verify completion or extract consultation codes
- Tickets are unverifiable — useless in a real fiscal audit

**Proof required (document upload)**
- Higher friction at the moment of completion
- Enables data extraction: amount, date, reference period, consultation codes
- Creates a verifiable, timestamped record
- Tickets are actual fiscal evidence, not just app records

## Decision Rationale

The core value of Compasso is not just reminding Marina to pay — it's giving her proof that she paid, in a format she can use years later if audited. A checkbox produces no evidence. A validated document upload produces a ticket with the DARF receipt number, GPS protocol, or Receita Saúde registration code that she can look up on government portals.

The friction of uploading a document is worth it because the alternative (a checkbox) would make Compasso a reminder app, not a compliance platform.

## Trade-offs Accepted

- Users who lose or misplace their proof documents cannot close the obligation in Compasso
- Document upload adds a step the user might find annoying in the short term
- The OCR pipeline must be reliable — a failed extraction creates a bad experience at the most important moment
