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

---

## Key Findings

### 1. The problem is both ignorance and fragmentation

Users generally don't know their obligations. The failure point is both
"I didn't know I had to pay INSS." and "I lost track of when, how much,
and whether I already did it this month."

Once these professionals graduate and start working, nobody give them
these informations. Also, every obligation lives on a separate government 
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

### 4. The biggest lost opportunity is Receita Saúde

Receita Saúde (the federal platform for healthcare professionals to log
patient sessions) is a weekly obligation that most users either forget or
underestimate. Missing it doesn't trigger an immediate fine, but creates
downstream risk in the annual DIRPF. Users consistently underreported
their Receita Saúde compliance rate when asked to self-assess.

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

→ Previous: [Problem](../01-problem/problem.md)  
→ Next: [Users](../03-users/users.md)
