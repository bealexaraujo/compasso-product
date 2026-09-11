# Technical Architecture

## Overview

Compasso is a single-page web application built for simplicity and fast iteration. The architecture was deliberately chosen to minimize infrastructure complexity during the discovery and validation phase. The goal was a working, testable prototype, not production-grade engineering.

## Stack

| Layer | Technology | Rationale |
|---|---|---|
| Frontend | Vanilla JS + CSS (single HTML file) | Zero build toolchain; instant iteration |
| Server | Node.js (Express-style, ~30 lines) | Static file server, no database needed |
| AI Agent | WhatsApp Business API (simulated) | Meets users where they already are |
| Storage | Browser localStorage | Stateless prototype; no backend required |
| Hosting | Local / localhost:3001 | MVP validation before cloud deployment |

## Architecture Decisions

### Single-file prototype
The entire frontend (HTML, CSS, and JavaScript) lives in one file (`prototipo.html`, ~490KB). This was an intentional choice: it removes all build dependencies, makes the prototype shareable as a single artifact, and lets a non-engineer PM iterate directly on the UI without a compile step.

**Trade-off accepted:** Not scalable to production. The refactor path is clear (component-based React or Vue with a real backend) but that comes after problem/solution validation.

### Push-based agent via WhatsApp
The AI agent doesn't live inside the app. It contacts the user via WhatsApp before deadlines. This decision was driven by behavior research: users don't open compliance apps proactively. The agent initiates; the user responds by uploading a proof document.

**Implication:** The product's core value delivery happens outside the app UI. The app is the record, not the primary touchpoint.

### No backend in MVP
There is no database, no API, no authentication server. User state is stored in `localStorage` (key: `fp_tasks_v2`). This allows full prototype fidelity with zero infrastructure cost during the validation phase.

**Constraint:** Multi-device sync and data persistence are not possible. Accepted for the prototype; production would require a proper backend.

### Proof-of-completion model
Obligations are only marked complete when a proof document is uploaded (or explicitly confirmed for non-document obligations like Receita Saúde weekly check-ins). The agent receives the document, extracts the data, and generates a ticket. No self-reporting.

**Why this matters technically:** The WhatsApp agent needs document parsing capability (OCR / structured data extraction from PDFs and images). This is the most technically complex piece of the product, and the one that creates the most defensible moat.

## Production Path (Post-Validation)

When moving from prototype to production, the key transitions are:

1. **Frontend:** Refactor single-file to component-based SPA (React/Vue)
2. **Backend:** REST API + PostgreSQL for user data, obligation state, and document storage
3. **Agent:** Real WhatsApp Business API integration with document parsing pipeline (OCR + LLM extraction)
4. **Auth:** OAuth (Google) — psychologists already use Google Workspace
5. **Hosting:** Cloud provider with Brazilian data residency (LGPD compliance)

## What This Phase Proved

The prototype successfully validated:
- The interaction model (push notifications + document upload) is intuitive to the target user
- The obligation catalog is accurate and complete for SP/PF psychologists
- The dashboard information architecture is understood without training
- Pricing sensitivity: R$19,90–R$24,90/month is in the acceptable range
