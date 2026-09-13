# Product Requirements Document
## Compasso — Condensed Version

> Full PRD available upon request. This document covers the core problem, solution, scope, and key decisions. The full version includes WhatsApp agent interaction specs, LGPD compliance implementation, fiscal obligation catalog, onboarding flow, and agent behavior rules.

---

## 1. The Problem

Autonomous psychologists in Brazil start clinical practice with no practical preparation for fiscal bureaucracy. Universities train them to treat patients — not to deal with Receita Federal, Carnê-Leão, INSS, Receita Saúde, and municipal obligations.

The result is predictable: professionals who don't know what they owe, miss deadlines, pay fines, and develop chronic anxiety about "doing something wrong." Most don't have an accountant because it's expensive at early stage career, and PF professionals are not legally required to hire one. That's precisely where the problem compounds: no accountant, no fiscal education, no tools built for their specific situation.

**The root cause is not the absence of accounting software. It's the absence of operational clarity and active follow-through.**

---

## 2. The Solution

Compasso is a web platform + conversational agent (WhatsApp) that manages fiscal compliance for autonomous psychologists operating as Pessoa Física (PF) in Brazil.

**Three pillars:**

**Pillar 1 — Configuration (Web)**
Guided onboarding identifies which fiscal obligations apply to the user's specific profile. The platform generates a personalized checklist with every applicable obligation: description, deadline, official system, step-by-step instructions, and direct link.

**Pillar 2 — Execution (WhatsApp Agent)**
The agent initiates contact before deadlines, the user does not need to open the app or remember anything. When an obligation is due, the agent sends a WhatsApp message with clear instructions. The user completes the obligation on the official government portal and sends back a proof document. The agent validates it via computer vision, extracts the government authentication codes, generates a Compasso ticket, and marks the obligation complete. The original document is discarded immediately (never stored).

**Pillar 3 — Record (Web)**
Dashboard with progress tracking, fiscal calendar, and history. All generated tickets are accessible at any time, containing the codes needed to verify each obligation on government portals.

---

## 3. Strategic Direction

**This is an active platform, not a passive one.** Compasso initiates contact. The user responds. The cognitive burden of remembering shifts from the professional to the system.

**Why WhatsApp:** Autonomous psychologists check WhatsApp dozens of times per day. They do not proactively open compliance apps. The channel choice is a behavior decision, not a technical one. Document upload happens natively in the same conversation, zero navigation required.

**Why proof-of-completion over self-reporting:** A checkbox creates no fiscal evidence. A validated document upload creates a ticket with government authentication codes the professional can use in an audit years later. The friction is intentional and worth it.

**Why no document storage:** Processing proof documents in memory and discarding them minimizes LGPD exposure, eliminates document storage infrastructure, and reduces liability. The Compasso ticket (which contains only extracted metadata and authentication codes) is what gets stored, not the underlying file.

---

## 4. Target Users

**Primary segment:** Autonomous psychologists operating as Pessoa Física (PF), without CNPJ, practicing in São Paulo/SP. Monthly revenue R$1,500–R$3,000. No accountant.

**Three profile types within segment:**
- Recent graduates (0–2 years): starting practice, no fiscal knowledge, anxious about compliance
- CLT-to-autonomous transition (2–5 years): left employment, facing fiscal obligations for the first time
- Established autonomous (5+ years): managing alone, no accountant, wants organization

**Primary persona — Marina, 28, São Paulo**
Graduated 2024. Sees 5 patients/week in shared office. Monthly income R$3,500. Has never filed Carnê-Leão. Doesn't know she needs to register on Receita Saúde. Has chronic anxiety about "doing something wrong fiscally." Doesn't have an accountant because she can't afford one yet.

What she needs: to know exactly what to do, when to do it, and to have something that activates her memory before she forgets.

---

## 5. MVP Scope

**In scope (São Paulo/SP, PF only):**

| Obligation | Frequency | System |
|---|---|---|
| Carnê-Leão | Monthly | Receita Federal / e-CAC |
| Receita Saúde — receipt registration | Weekly | Receita Federal App |
| Receita Saúde — monthly review | Monthly | Receita Federal App |
| INSS — Plano Simplificado | Monthly | Meu INSS |
| DIRPF — Income tax return | Annual (Apr 30) | Receita Federal |
| Anuidade CRP | Annual (Mar 31) | CRP-SP Portal |
| CCM — Cadastro de Contribuinte Mobiliário | One-time | Prefeitura SP |

**Out of scope (explicit):**
- CNPJ / MEI (different fiscal regime, different user profile)
- NFS-e issuance
- Automated tax calculation
- Integration with government systems (agent guides, doesn't file)
- Document storage
- Cities outside São Paulo
- Professions other than psychology
- Native mobile app

---

## 6. The Compasso Ticket

The ticket is Compasso's primary compliance artifact, generated after each validated obligation and stored permanently in the user's history.

**Contents:**
- Obligation name and reference period
- Amount paid and payment date
- Government authentication code (DARF receipt number, GPS protocol, Receita Saúde registration code, etc.)
- SHA-256 hash reference of the original document
- Unique Compasso reference code

**Why it matters:** In a fiscal audit, the professional needs to prove not just that they paid, but when, how much, and with what reference code, and be able to look it up on the official government portal. The ticket provides all of that without Compasso storing any sensitive document.

---

## 7. Business Model

**Pricing:**
- Monthly plan: R$24,90/month
- Annual plan: R$19,90/month (billed R$238,80/year — 20% discount)

**Trial:** 30 days, full access, no credit card required at signup. The 30-day window guarantees the user experiences at least one full monthly obligation cycle (the core value loop). During onboarding, Compasso shows the exact date of the first agent alert ("Your first Compasso message arrives on [date]"), setting the expectation and anchoring the trial to a concrete moment of value.

**Retention hypothesis:** Unlike a productivity app that teaches something once, Compasso creates operational dependency. The user begins to expect the agent's messages. After 3 months of the agent managing their fiscal routine, discontinuing the subscription means returning to the state of anxiety and disorganization that brought them to Compasso in the first place.

**Break-even:** ~19 paying subscribers cover the estimated R$442/month baseline infrastructure cost.

---

## 8. Success Metrics

**North Star:** Monthly obligation completion rate — % of due obligations completed on time across active users. Target: ≥90% for users active 3+ months.

**Retention signal:** 3-month consecutive 100% completion streak — users who complete all obligations for three months in a row.

**Value metric:** Cumulative fines avoided (R$) — displayed in the dashboard. Converts abstract compliance into concrete financial value.

**Acquisition:** Trial-to-paid conversion rate; time to first completed obligation (users who complete an obligation within 7 days of signup convert at significantly higher rates).

---

## 9. Key Technical Constraints

- No proof documents are stored. Processing happens in memory; files are discarded immediately after validation.
- The agent operates via WhatsApp Business API (Meta). All obligation alerts are outbound templates approved by Meta.
- Government obligations are executed by the user on official portals — Compasso guides and validates, never files on behalf of the user.
- LGPD compliance: explicit opt-in for WhatsApp processing; data export (Art. 15) and deletion (Art. 18) endpoints implemented; 5-year metadata retention per CTN requirements.
- Agent response target: ≤30 seconds from document receipt to ticket generation in ≥95% of cases.
