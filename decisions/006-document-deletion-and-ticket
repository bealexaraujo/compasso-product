# PDR-006: Delete Proof Documents After Processing — Introduce the Compasso Ticket

**Status:** Decided  
**Date:** 2026-Q1

## Decision

Proof documents sent by the user via WhatsApp are deleted immediately after the agent extracts and validates the relevant data. Compasso does not store the original documents. Instead, the agent generates a structured Compasso ticket containing the extracted information and the consultation codes needed to verify the obligation on government portals.

## Context

When a user sends a proof document — a DARF receipt, a GPS payment confirmation, a Receita Saúde protocol — the agent needs to process it. The question is what happens to that file after processing.

## Options Considered

**Store the original document**
- User has access to the original file inside Compasso
- Requires secure document storage infrastructure
- Creates long-term liability: we are holding sensitive financial documents on behalf of users
- LGPD compliance becomes complex — data minimization principle requires justification for every piece of data retained

**Delete the document, generate a ticket**
- Original document is discarded after extraction
- No sensitive documents stored on Compasso's servers
- Compasso generates a structured ticket with the extracted data and the consultation codes (DARF receipt number, GPS protocol, Receita Saúde registration code) that allow the user to verify the obligation directly on government portals
- User does not need to retrieve the document from Compasso — they can look it up at the source

## Decision Rationale

Storing proof documents would make Compasso a document vault — a responsibility we did not design for and do not want. Financial documents are sensitive. Holding them creates legal exposure, increases infrastructure complexity, and makes us a higher-value target for a data breach.

The insight that unlocked this decision: the document itself is not what Marina needs long-term. What she needs is the ability to prove compliance if audited — which the government portals already provide. The Compasso ticket gives her the consultation codes to do exactly that, without us holding the underlying file.

This reframed the ticket from "a copy of the document" to "a key that unlocks the official record." The original document is processed and discarded. The ticket is what Compasso issues and stores.

## What the Ticket Contains

- Obligation type and reference period
- Amount paid and payment date
- Consultation codes for the relevant government portal
- Timestamp of agent validation
- Agent confirmation status

## Trade-offs Accepted

- If the government portal is unavailable or changes its structure, the consultation codes may not resolve
- Users who expect to retrieve their original documents from Compasso will not find them — this must be communicated clearly during onboarding
- The OCR extraction must be reliable; if data is extracted incorrectly and the document is deleted, the error is difficult to recover from
