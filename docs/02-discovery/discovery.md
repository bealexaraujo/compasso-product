# Discovery

## Approach

Discovery for Compasso focused on understanding how autonomous psychologists
actually manage their fiscal obligations today. Not what they think they need,
but what they do, what breaks, and what it costs them cognitively.

The process combined:

- **Problem interviews** with autonomous psychologists operating as Pessoa Física
- **Jobs-to-be-Done (JTBD) framework** to identify the underlying motivation
  behind compliance behavior
- **Behavioral observation** of how users navigate government portals
- **Competitive analysis** of existing tools in the market
- **User journey mapping** to identify the moments of highest friction

---

## Who We Talked To

**Primary segment:** Autonomous psychologists (psicólogos autônomos) operating
as Pessoa Física in São Paulo, Brazil.

This segment was chosen because:

- They have a well-defined, shared set of fiscal obligations
- They operate without dedicated financial support (no accountant, no HR)
- They are highly educated but receive zero training on fiscal management
during their academic formation
- The CRP (Federal Council of Psychology) creates a traceable, organized
professional community, making the segment reachable

**Research group:**
A WhatsApp group of 58 psychologists from the same graduating class, ranging
from 22 to 60+ years old. Approximately 25 members participated actively in
the conversations around fiscal compliance. The conversations were not
structured interviews. They emerged when the founder raised the topic, and
the group reaction (immediate, spontaneous, and unanimous) became one
of the most revealing data points in the research.

The full methodology is documented in [Research](./research.md).

---

## Key Findings

### 1. The problem is both ignorance and fragmentation

Users generally don't know their obligations. The failure point is both
"I didn't know I had to pay INSS." and "I lost track of when, how much,
and whether I already did it this month."

Once these professionals graduate and start working, nobody give them
this information. Also, every obligation lives on a separate government 
portal. Every portal has its own login, its own interface, and its own 
deadline logic. There is no unified view.

### 2. Compliance anxiety is real and recurring

Psychologists described a recurring cycle: forget → panic → scramble →
pay (sometimes late) → forget again. The emotional cost of this loop was
mentioned unprompted by multiple users.

One recurring description: *"Todo mês eu fico com aquela sensação de que
esqueci alguma coisa."* ("Every month I have that feeling that I forgot
something.")

### 3. Tools built for businesses don't fit solo professionals

Users who attempted to use accounting software (Contabilizei, QuickBooks,
Omie) reported that the tools assumed CNPJ registration, multiple clients
with invoices, or a dedicated operator, which is not affordable in the
beginning of their career. Solo PF professionals felt like second-class 
users in tools not designed for them.

### 4. Receita Saúde was the most common unknown obligation

Receita Saúde (the federal platform for healthcare professionals to log
patient sessions) emerged as the obligation most participants were either
unaware of or significantly behind on. Missing it doesn't trigger an immediate
fine, but creates downstream risk in the annual DIRPF.

What was striking was not that people forgot to file, it was that many
didn't know the obligation existed at all. When the topic came up in
conversation, the typical reaction was confusion first, then concern.
The obligation had simply never appeared in their professional formation.

### 5. "Proof of completion" is the missing primitive

When asked "how do you know you've completed an obligation?", the most
common answer was: "I think I did." Receipts were stored across WhatsApp,
email, phone photos, and browser downloads, with no consistent system.

---

## Jobs-to-be-Done

**Primary job:**
> When I'm an autonomous psychologist managing my own practice,
> I want to know what I need to do this month and confirm I've done it,
> so I can focus on my patients without worrying about missing a deadline.

**Secondary jobs:**
- Understand what a specific obligation actually requires, in plain language
- Know in advance when a deadline is approaching
- Have evidence that I completed something, in case I'm ever questioned
- Feel confident I'm not forgetting something important

---

## Competitive Analysis

| Tool | Category | Gap |
|---|---|---|
| Mobills / Organizze | Personal finance | No concept of fiscal obligations |
| Contabilizei | Accounting SaaS | Assumes CNPJ / accountant-operated |
| QuickBooks | Accounting SaaS | Overkill for solo PF professionals |
| Google Calendar | Reminders | No obligation logic, no proof tracking |
| Planilhas manuais | Self-managed | No automation, high maintenance |
| Nenhuma ferramenta | No tool | The most common answer |

**Conclusion:** No tool in the Brazilian market addresses the specific
compliance needs of autonomous Pessoa Física professionals. The gap is
structural. Existing tools were built for different jobs.

---

## What Discovery Shaped

1. **Scope:** MVP limited to São Paulo / Pessoa Física, the most common and
   well-defined profile
2. **Core feature:** A personalized obligation checklist, not a generic
   to-do list
3. **Key differentiator:** Proof-of-completion via document upload, replacing
   manual check-off
4. **Tone:** Plain language explanations of each obligation
5. **AI opportunity:** An AI assistant that proactively surfaces the right task
   at the right time, rather than waiting for the user to remember to check

---

## What We Got Wrong

### First version: a checklist the user manages

The initial product concept was a structured checklist: the user would see
their obligations, complete them through government portals, and mark each
one as done inside the product. A simple check-off model.

This seemed reasonable. It was better than a spreadsheet or a calendar event.
But it had a structural problem: it still required the user to initiate. They
had to remember to open the product, find the obligation, complete it
elsewhere, come back, and mark it done. The cognitive load was lower, but
it was still on the user.

Discovery broke this model in two ways.

**First:** the research made clear that autonomous psychologists don't open
compliance tools proactively. The recurring pattern was forget → panic →
scramble → pay (sometimes late) → forget again. A product that waits to be
opened reproduces that cycle. The problem isn't that users lack a checklist.
It's that the obligation doesn't exist in their mental model until something
external forces it to.

**Second:** a checkbox creates no evidence. An obligation marked "done" by the
user is just a boolean. It can't be used in a fiscal audit. It can't prove
amount, date, or reference period. And crucially, it can't prevent
self-reporting errors — a user could mark an obligation complete without
having paid it, intentionally or not.

### What replaced it

The pivot was to invert the interaction model entirely. Instead of the user
managing their checklist, an AI agent initiates contact before each deadline
via WhatsApp, receives the proof document the user uploads in response, extracts
the relevant data through OCR, and closes the obligation with a verifiable
ticket.

This change did three things at once:

1. Removed the requirement for the user to remember or initiate (removed mental overload)
2. Generated actual fiscal evidence instead of a checkbox state
3. Made self-reporting impossible for payment obligations (you either send
the document or the obligation stays open)

→ Previous: [Problem](../01-problem/problem.md)  
→ Next: [Users](../03-users/users.md)
