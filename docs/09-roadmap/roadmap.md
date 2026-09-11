# Roadmap

## Approach

Compasso's roadmap is organized around validation stages, not calendar quarters. Each phase has a specific question it needs to answer before moving forward. Shipping features before validating the previous phase is the most common way to build the wrong thing faster.

## Phase 0 — Prototype (Current)

**Question:** Does the interaction model make sense to real users?

**What exists:**
- Interactive single-file prototype (HTML/JS/CSS)
- Full obligation catalog for SP/PF psychologists
- Dashboard, history, reports, and obligation detail flows
- AI agent simulated via WhatsApp prototype flow
- Pricing page (R$19,90–R$24,90/month)

**What we're validating:**
- Does the push-based agent model reduce friction versus pull-based apps?
- Is the obligation catalog accurate and complete?
- Does the dashboard give Marina the right information at a glance?
- Is the pricing acceptable for early-career psychologists?

**Exit criteria:** 10+ prototype sessions with real psychologists, ≥70% task completion rate, qualitative signal that the WhatsApp interaction feels natural.

---

## Phase 1 — Private Beta

**Question:** Will people actually use it when money is on the line?

**Who:** 20–30 autonomous psychologists in São Paulo, invited manually.

**What we build:**
- Real WhatsApp Business API integration (not simulated)
- Basic document upload and OCR pipeline for Carnê-Leão and INSS
- User accounts and data persistence (no more localStorage)
- Payment processing (Stripe or PagSeguro)
- Manual obligation verification fallback (human-in-the-loop for edge cases)

**What we intentionally skip:**
- Mobile app
- Automated tax filing
- Support for obligations outside the SP/PF scope
- Self-serve onboarding (beta users are onboarded manually)

**Exit criteria:** ≥80% monthly obligation completion rate across beta users, ≥50% 3-month retention, at least 5 users paying without prompting.

---

## Phase 2 — Public Launch (SP/PF)

**Question:** Can we acquire and retain users without manual effort?

**What we build:**
- Self-serve onboarding via web
- Automated document processing for all tracked obligations
- Full ticket history with government portal consultation codes
- In-app support chat
- Referral program (psychologists refer psychologists)

**Distribution hypothesis:** The primary acquisition channel is word-of-mouth within CRP regional chapters and psychology supervision groups. Psychologists trust other psychologists, not ads.

**Exit criteria:** ≤R$80 customer acquisition cost, ≥6-month average retention, NPS ≥40.

---

## Phase 3 — Geographic and Professional Expansion

**Question:** Is the model replicable beyond SP psychologists?

**Two parallel bets:**
1. **New states:** Rio de Janeiro and Minas Gerais have similar obligation profiles to São Paulo. Expansion is primarily a catalog update (new municipal obligations, different CCM rules).
2. **New professions:** Autonomous nutritionists, physiotherapists, and speech therapists face near-identical obligations. The product architecture already supports profession-based profiles.

**We expand to a new segment only when:** The SP/PF psychologist cohort shows ≥12-month retention and positive unit economics.

---

## What Is Not on the Roadmap

**Automated tax filing:** Filing a DARF or GPS on the user's behalf requires power of attorney and creates significant legal liability. We track and confirm; we do not file.

**CNPJ / MEI support:** A deliberate out-of-scope decision. MEI has a different obligation structure, different tax regime (Simples Nacional), and a completely different user profile. Supporting it would split product focus without proportional return.

**Desktop app:** The product lives in WhatsApp and a browser. A native app adds distribution friction (app stores, OS permissions, update cycles) with no clear benefit for a task users perform monthly, not daily.

**Accountant marketplace:** Connecting users to human accountants is a adjacent business, not a product feature. If the product works, users shouldn't need an accountant for routine compliance.
