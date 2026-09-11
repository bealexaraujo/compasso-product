# Product Design

## Interaction Model

Compasso is built around a pull-to-push inversion.

Most compliance tools are **pull**: the user opens the app, checks what
needs to be done, and acts. Compasso is **push**: the assistant identifies
what needs to happen and brings it to the user.

The interaction sequence for a payment-based obligation looks like this:

Compasso → "Your INSS payment is due in 3 days. Here's how to pay."
User pays via Meu INSS.
User → uploads GPS receipt to Compasso.
Compasso → extracts date, amount, and competência from the document.
Compasso → "Payment confirmed. INSS for May is complete."


The user never had to remember the deadline, navigate to find the steps,
or manually mark anything as done. The product drove the interaction.

---

## Core Flows

### 1. Onboarding

The onboarding maps each user's specific obligation profile across 7 steps:

1. **Profile** — name, email, CPF, phone
2. **Introduction** — explains what Compasso will configure
3. **Location** — city, state, whether they have a physical office
4. **Professional structure** — PF status, CRP registration, CCM status
5. **Session documentation** — Receita Saúde usage, session volume, insurance
6. **Fiscal situation** — Carnê-Leão status, INSS enrollment, DIRPF history
7. **Summary** — shows the personalized obligation set and confirms setup

The outcome is a tailored checklist. A user without a physical office doesn't
see CCM. A user who doesn't use Receita Saúde doesn't see those obligations.
Every user sees exactly what applies to them, explained in plain language.

### 2. Dashboard

The dashboard is the daily reference view, not the primary interaction surface.

It shows:
- **Progress for the current month** — obligations completed vs. total
- **Current streak** — consecutive months of full compliance
- **Next deadline** — the nearest upcoming obligation
- **Overdue count** — obligations past their deadline

Below the stats, a filtered checklist organizes obligations into three
groups: this week, this month, and annual. Each obligation shows its
status, deadline, and quick-action buttons.

The dashboard intentionally does not try to teach. It is the at-a-glance
view for a user who already knows their obligations. The AI handles the
teaching when the obligation is due.

### 3. Obligation Detail

Each obligation has a dedicated detail view with:
- What it is, in plain language
- Who needs to do it (and who doesn't)
- The exact deadline and how fines are calculated if missed
- A step-by-step guide to completing it
- A direct link to the relevant government portal

This is the educational layer. The obligation detail exists so that a user
who has never heard of Carnê-Leão can understand it in 2 minutes, without
leaving the product.

### 4. History

The history view shows compliance across months, with a visual heatmap
by month and a detailed breakdown of completed and missed obligations
per period.

Users can generate a compliance report (PDF or CSV) for any date range.
This serves two purposes: personal record-keeping, and documentation
if a user is ever questioned about their compliance history.

### 5. AI Agent

The AI agent is the conversational layer. It handles:
- Proactive reminders at D-3 and D-1 before each deadline
- Document receipt and validation after upload
- Confirmation and ticket generation for completed obligations
- Alerts for overdue obligations (repeated daily until resolved)
- Questions about obligations in plain language

The agent does not replace the dashboard. It is the mechanism through
which the product initiates contact with the user — the push layer
that makes the dashboard useful without requiring the user to open it.

---

## Design Principles

**1. One thing at a time.**
The agent never presents multiple obligations at once. Each notification
focuses on a single obligation, with a single next action. Cognitive load
is the enemy.

**2. Proof over trust.**
The product does not accept "I did it" as a valid completion state for
payment obligations. Document upload is required. The record matters more
than the convenience of skipping it.

**3. Explain before asking.**
Before asking a user to complete an obligation, the product explains what
it is and why it matters. A user who understands Receita Saúde will not
ignore the reminder.

**4. Errors are expected.**
Government portals change. Payment dates shift. Users make mistakes. The
product is designed to handle incomplete states gracefully. An overdue
obligation surfaces as an alert, not a dead end.

---

## Visual Design

The design system follows a **pastel · flat · rounded** direction:

- **Color:** A green brand palette with neutral grays. No gradients.
  Status colors (green for complete, red for overdue, gray for pending)
  are semantic and consistent across every surface.
- **Typography:** Inter throughout. Hierarchy through weight and size,
  not color.
- **Components:** Rounded cards, no shadows, high whitespace. The interface
  is calm by design — the obligations themselves are stressful enough.
- **Icons:** Ionicons (iOS variant) for consistency with a mobile-first
  interaction model.

---

## Prototype

A high-fidelity interactive prototype covers all core flows: onboarding,
dashboard, obligation detail, history with report generation, and the
AI agent interaction.

The prototype is implemented as a single-file HTML application (vanilla JS,
no framework) and runs locally. It uses realistic mock data — a full year
of compliance history for the Marina Souza persona — to simulate the
experience of a returning user, not just a first-time visitor.

> Screenshots of the prototype are available in [`/assets/screenshots`](../../assets/screenshots/).

---

→ Previous: [Strategy](../04-strategy/strategy.md)
→ Next: [Technical Architecture](../06-technical/technical.md)
