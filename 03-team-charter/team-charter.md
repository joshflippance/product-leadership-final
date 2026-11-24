# Team Charter: Plumb: AI integration platform

> Module 3 · Set the Habits That Make a Team Faster

**Cross-team tension:** Plumb's drift watch holds messages when a customer's EHR changes, and AI Mapping proposes a fix. But that fix affects the design partner's product: its diet codes, textures, allergy lists, and what each customer site sends. Today nobody clearly owns approving the fix, or deciding when held diet orders and allergies are released. Plumb knows the mapping and the platform, the partner knows its app and its customers' codes, and a wrong call could put an allergy in front of the wrong patient.

## 1. What We Own

> **We own:** The Plumb platform end to end: connectors, drift detection, held messages, AI Mapping proposals with per-field confidence, templates and per-site overrides, the audit log, encryption, and regional hosting. We own the technical accuracy of every fix, meaning the right source field is parsed, transformed, and delivered with zero lost messages. We record how every held message was resolved.
>
> **Out of scope:** What diet codes, textures, and allergy terms mean, and how each site's values map onto them (the partner's product team). Each site's EHR, its configuration changes, and EHR access (the customer site's IT team). Talking to customer sites (the partner's support team). Plumb never contacts a site unless the partner asks.
>
> **Joint calls:** Any fix that touches diet orders, textures, or allergies needs two sign-offs before it goes live: Josh confirms the mapping is technically correct, and the partner's named Approver confirms the clinical meaning. Releasing held messages with those fields needs the same two sign-offs, and allergies are never released automatically at any confidence score. Changes to a shared template used by more than one site, and changes to what triggers a hold, are also joint calls.

## 2. How We Decide

> **Who decides scope:** Josh decides Plumb's scope with one test: does it move KR1, KR2, or KR3 this quarter? For fields with no clinical meaning, such as room numbers or meal schedules, Josh can apply a high-confidence fix alone and tell the partner the same day. The partner alone decides scope inside its own product, including which codes and sites go live first.
>
> **How cross-team conflicts escalate:** Either side raises a conflict as a comment on the held-message record in Plumb, which alerts the other side. The other side answers within 2 hours for allergies and before the next meal service for diet orders. If there's still no agreement, the partner's head of product makes the final call on what codes mean and when held messages are released, and Josh makes the final call on platform behaviour. Until then, messages stay held and the partner tells affected sites to use their paper or phone backup.
