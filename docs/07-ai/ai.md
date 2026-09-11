# AI Product Design

## The Agent's Job

Compasso's AI agent has one job: make sure Marina never misses a fiscal deadline.

It does this by initiating contact, not waiting to be asked. The agent tracks every obligation, calculates deadlines, and sends a WhatsApp message before each one is due. When Marina responds with a proof document, the agent processes it and closes the loop.

This is not a chatbot. It's a compliance co-pilot that acts first.

## Why WhatsApp

The channel choice is a product decision, not a technical one.

Autonomous psychologists in Brazil check WhatsApp constantly. They do not open dedicated apps unless they have a reason. If we built a push notification system inside the app, we'd be asking users to grant notification permissions, keep the app installed, and remember we exist.

WhatsApp requires none of that. It's already open. The message arrives where attention already is.

## The Interaction Model

Every obligation follows the same three-message sequence:

**D-3 (3 days before deadline)**
> "Olá Marina! O Carnê-Leão de abril vence em 3 dias (31/05). Quando você tiver o comprovante de pagamento, é só me enviar aqui. Precisa de ajuda para gerar a guia?"
> "Hi Marina! April's Carnê-Leão is due in 3 days (31/05). Whenever you have the payment receipt, send me here. Do you need help generating the payment guide?"

**On document receipt**
> "Recebi o comprovante! Deixa eu verificar... ✓ Pagamento de R$ 412,00 confirmado. Vou registrar e gerar seu ticket agora."
> "Got it! Let me verify it... ✓ Payment of R$ 412,00 confirmed. Registering and generating your ticket now."

**On completion**
> "Tudo certo! Carnê-Leão de abril registrado. Seu ticket de comprovação foi gerado. ✅"
> "All good! April's Carnê-Leão registered. Here's your validation ticket ✅"

The agent adapts tone by obligation type: payment obligations get one flow, registration obligations (Receita Saúde) get a simpler confirmation flow, and overdue obligations generate daily alerts until resolved.

## Document Processing

When a user sends a proof document (PDF, image, or screenshot), the agent:

1. Receives the file via WhatsApp Business API
2. Runs OCR to extract text from the document
3. Uses a structured extraction prompt to identify: obligation type, reference period, amount paid, payment date, and issuing authority
4. Validates the extracted data against expected values for that obligation
5. Creates a timestamped ticket containing:
   - Obligation type and reference period
   - Amount paid and payment date
   - Consultation codes for government portals (e.g., DARF receipt number for Carnê-Leão and INSS/GPS, protocol number for Receita Saúde registrations, delivery receipt number for DIRPF)
   - Original proof document (stored for 5 years, matching the fiscal audit window under Brazilian tax law)
6. Marks the obligation as complete

Tickets are the product's long-term value layer. In a fiscal audit, Marina needs to prove not just that she paid, but *when* and *how much* — and be able to look it up on the Receita Federal, Meu INSS, or Receita Saúde portals. The ticket gives her those codes in one place, without digging through WhatsApp history or email attachments.

This pipeline is the technical core of the product. Everything else — the dashboard, the history view, the reports — is presentation of data this pipeline generates.

## What the Agent Does Not Do

Scope constraints matter as much as capabilities:

- **Does not give tax advice.** The agent confirms facts (deadlines, amounts, procedures) but never recommends a course of action on ambiguous situations.
- **Does not file on the user's behalf.** Marina always performs the action; the agent tracks and confirms.
- **Does not handle PJ obligations.** The agent is calibrated exclusively for Pessoa Física autonomous professionals. MEI, Simples Nacional, and CNPJ obligations are explicitly out of scope.
- **Does not replace an accountant.** For edge cases, the agent surfaces the question and suggests consulting a professional.

## Agent Personality

The agent communicates as a knowledgeable, calm assistant (not a corporate system and not a chatty bot.) 

Key tone attributes:
- **Direct:** Gets to the point. No filler.
- **Warm but not casual:** Uses first name, but doesn't use slang.
- **Confident:** Doesn't hedge on facts it knows. "O prazo é 31/05" — not "O prazo deve ser por volta de 31/05."
- **Proactive:** Always tells Marina what happens next.

The agent's name inside the product is "your Compasso". The platform itself, not a separate AI persona. This keeps the brand coherent and avoids the uncanny valley of a named AI character.

## Open Design Questions

These decisions are intentionally deferred to post-validation:

- **Escalation path:** What happens when Marina misses a deadline despite the D-3 alert? How aggressive should follow-up be?
- **Multi-obligation days:** When two obligations fall on the same day, do we send two separate messages or one combined message?
- **Onboarding conversation:** The current onboarding is a web form. Should it move to WhatsApp for users who prefer that channel?
- **Historical import:** Can a new user import past obligations she handled before joining Compasso?
