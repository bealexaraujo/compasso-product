# PDR-001: WhatsApp Over In-App Push Notifications

**Status:** Decided  
**Date:** 2026-Q1

## Decision

Compasso's AI agent delivers all alerts and interactions via WhatsApp, not through in-app push notifications.

## Context

We needed to choose a primary channel for the agent to reach users before deadlines. The two main options were: (1) in-app push notifications, or (2) WhatsApp messages.

## Options Considered

**In-app push notifications**
- Requires the user to keep the app installed and grant notification permissions
- Notification fatigue is high — most users disable app notifications over time
- Open rates for push notifications average 5–15% across mobile apps

**WhatsApp**
- Already installed and checked constantly by the target demographic
- No permission friction beyond the initial opt-in
- Document upload happens natively in the same conversation thread
- The agent can receive a proof document without directing the user to another app

## Decision Rationale

Autonomous psychologists in Brazil do not open compliance apps proactively. They respond to things that arrive where their attention already is. WhatsApp is checked dozens of times per day; a dedicated app is opened only when prompted.

The channel choice also affects the document upload flow. If the alert is a push notification, the user must open the app, navigate to the obligation, and upload a file. With WhatsApp, the proof document is sent as a reply to the alert message — zero navigation required.

## Trade-offs Accepted

- Compasso depends on WhatsApp Business API availability and pricing
- The in-app experience becomes secondary to the WhatsApp experience
- Users who do not use WhatsApp are not served by the current model
