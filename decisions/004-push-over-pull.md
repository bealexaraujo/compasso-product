# PDR-004: Push-Based Agent Over Pull-Based App

**Status:** Decided  
**Date:** 2026-Q1

## Decision

Compasso is designed as a push-based system. The agent initiates contact with the user before deadlines. The user does not need to open the app or check a dashboard to stay compliant.

## Context

Most compliance tools are pull-based: they provide a dashboard the user must remember to open, a checklist the user must remember to consult. The user carries the cognitive burden of remembering to check.

## Options Considered

**Pull-based (dashboard-first)**
- User opens the app, sees their obligations, acts
- Standard pattern for productivity and compliance apps
- Fails when the user forgets to open the app — which is most of the time

**Push-based (agent-first)**
- Agent monitors deadlines and contacts the user proactively
- User only needs to respond when contacted
- The burden of remembering shifts from the user to the system

## Decision Rationale

Discovery research showed that psychologists miss fiscal deadlines not because they don't care, but because they forget. They are managing a full client schedule, session notes, and personal life — fiscal obligations are not top of mind until it's too late.

A pull-based product requires the user to change behavior (open a new app regularly). A push-based product works with existing behavior (respond to a WhatsApp message). Behavior change is hard; behavior reinforcement is easy.

## Trade-offs Accepted

- If WhatsApp messages are ignored or filtered, the system fails silently
- The dashboard becomes a secondary surface — users may undervalue the app itself
- Push frequency must be calibrated carefully to avoid being perceived as spam
