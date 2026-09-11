# Strategy

## Product Vision

Compasso makes fiscal compliance invisible for autonomous professionals.

Not easier. Not faster. **Invisible**, meaning the professional never has
to think about whether they forgot something, because the product is already
ahead of them.

---

## The Strategic Bet

Most compliance tools are built around a dashboard: a list of things to do,
which the user must remember to open, check, and act on.

Compasso bets against that model.

The core hypothesis is that **the job is not "manage my obligations", it's
"not have to think about my obligations."** A dashboard still requires the
user to initiate. An AI assistant can be the one that initiates.

This shapes everything: the interaction model, the notification design, the
completion logic, and the AI architecture. The product is not a dashboard
with an AI bolt-on. It is an assistant that happens to have a dashboard for
reference.

---

## Positioning

**What Compasso is:**
An AI-powered compliance assistant for autonomous professionals in Brazil,
starting with psychologists operating as Pessoa Física in São Paulo.

**What Compasso is not:**
- An accounting tool (no calculations, no bookkeeping)
- A generic to-do app with reminders
- A government portal aggregator
- A financial planning product

The positioning is narrow by design. A product that claims to solve
compliance for every professional type solves it reliably for none.
Starting with one well-defined segment means the obligation logic,
the language, the onboarding, and the AI behavior can all be built
specifically for that segment.

---

## MVP Scope

**Who:** Autonomous psychologists, Pessoa Física, São Paulo/SP only.

**Why this segment first:**
- Shared, well-defined obligation profile (same set of obligations for all)
- No existing dedicated tooling
- Reachable community (CRP registration creates a traceable segment)
- Early-career professionals with constrained margins — price-sensitive
  enough to make a low-cost product viable without enterprise sales

**What the MVP does:**
1. Onboards the user and maps their specific obligation profile
2. Tracks deadlines for each obligation across the calendar
3. Sends proactive reminders before deadlines (D-3 and D-1)
4. Validates completion through document upload and AI extraction
5. Maintains a compliance history the user can reference or export

**What the MVP does not do:**
- Calculate taxes (Carnê-Leão amounts must be entered by the user)
- Connect to government portals (no API access, links only)
- Make payments for the user
- Support CNPJ / PJ professionals
- Operate outside São Paulo

---

## The Retention Problem

Fiscal compliance is seasonal. Most obligations are monthly, with annual
spikes around DIRPF (April) and CRP renewal (March). A user who completes
their obligations has no reason to open the app.

This is the core retention challenge: the product succeeds by making itself
unnecessary to actively use.

The strategic response is to position Compasso as an **ongoing operational
companion**, not a task manager. This means:

- The AI logs every action, creating a compliance history that has value
  beyond the current month
- The annual summary and tax-season preparation become high-value moments
  that bring users back
- The product accumulates context over time (a user's history, their
  specific profile, their completion patterns) making it harder to replace
  with a generic reminder app

**The goal:** Users stay not because they have tasks to complete, but
because Compasso holds their compliance history and they trust it to
tell them when something needs attention.

---

## Key Product Decisions

### 1. AI validation over manual check-off

The decision to require document upload (not just a "mark as done" button)
for payment-based obligations is a deliberate trade-off: it creates friction
at completion, but generates proof and builds trust in the system's record.

### 2. Obligation-specific onboarding

Rather than showing all possible obligations to all users, Compasso maps
each user's profile during onboarding and shows only the obligations that
apply to them. This requires more upfront investment in the obligation logic
but reduces cognitive load at every subsequent interaction.

### 3. Plain language as a product feature

Every obligation in Compasso has a plain language description written for
someone who has never heard of it. It is the educational layer that addresses 
the root cause of the problem. A user who understands what Carnê-Leão is and 
why they owe it will comply more reliably than one who is just reminded to pay.

### 4. Segment-first expansion

Post-MVP expansion follows the same playbook: one new professional segment
at a time, each with its own obligation profile fully mapped before launch.
Dentists, therapists, and other healthcare professionals operating as PF
are the natural adjacent segments.

---

→ Previous: [Users](../03-users/users.md)
→ Next: [Product Design](../05-product-design/product-design.md)
