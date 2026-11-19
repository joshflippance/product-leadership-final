# Product Strategy & OKRs

> Module 1 · Write a Strategy That Can Survive a Test

**Scenario:** My own initiative, Plumb: AI integration platform.

Plumb is an integration platform I'm building that uses AI to connect different business systems. Software vendors have to connect their product to each customer's existing systems, and every customer runs a different system and data format. Each connection becomes a custom project. It needs a scarce integration engineer, takes weeks or months, and breaks quietly when the other system changes. Current tools are either heavy enterprise engines that need specialists (Mirth, Rhapsody, MuleSoft) or app automation tools that don't handle older formats like HL7, flat files, or SOAP. My starting market is dining software vendors serving hospitals and senior living. They need admissions, diet orders, and allergies from every customer's EHR, and a missed allergy is a patient safety risk. Constraints: I'm a team of one working with AI, I have no design partner yet, and Plumb only uses synthetic data so far. Real patient data needs PHIPA/HIPAA agreements and SOC 2 first. Today Plumb supports HL7 v2, CSV, and JSON over MLLP and HTTPS. It has AI Mapping with a measured confidence score for every field (0.5% silent errors in a blind benchmark) and a template and setup wizard in demo mode.

## 1. Playing to Win cascade

| Question | Your choice |
|---|---|
| **Winning aspiration** | Plumb is the integration platform software vendors use to connect their product to any customer's systems. We win first with dining software vendors in healthcare: a new hospital or senior living site goes live in days, without an integration engineer, and every message is accounted for. |
| **Where to play** | Dining and food software vendors (10 to 50 people, no integration team) selling into hospitals and senior living in Canada and the US. We start with care-to-dining workflows from the EHR: admissions, discharges, and transfers, diet orders with textures and allergies, and a daily census. We leave out hospital IT departments, distributors, food-service operators, and other industries until this segment is working. The platform stays generic so it can grow into them later. |
| **How to win** | Three things a generic tool can't easily copy. First, published evidence: AI Mapping shows a measured confidence for every field, and we publish our silent error rate (0.5%), which incumbents don't do. Second, a learning loop: every field a person approves or corrects improves the next mapping in this domain. Third, ready-made templates for care-to-dining workflows, so an implementation person can finish setup alone instead of starting from a blank channel. Vendors embed Plumb in their own product and pay per live connection, which costs far less than an interface engineer. |
| **Capabilities required** | Care-to-dining templates and a setup wizard a non-engineer can finish alone. AI Mapping extended to FHIR R4, with corrections feeding back into future mappings. Connectors only as far as the design partner's EHR needs (FHIR R4, SFTP, REST with OAuth2). A faster route to EHR access: a ready-made security review pack for each customer site, and either an outbound-only on-site agent or the EHR's own marketplace, so a site needs no VPN or inbound firewall rule. Drift watch that catches EHR changes and holds messages before they're lost. And the compliance basics that let us handle real patient data: a BAA, PHIPA first, then SOC 2. |
| **Management systems** | Weekly, until we have a partner: number of dining vendor conversations, and what we learned about trust and willingness to pay. Weekly, once live: time to live, share of fields needing human review, and silent error rate. Always-on health checks: zero lost messages, and every held message has a reason. Monthly: pipeline review and compliance progress. |

## 2. Your one hard no

> **Hard no:** We will not sell AI Mapping on its own as a plug-in for teams already using Mirth, Rhapsody, or Redox, even though it's the fastest way to revenue and avoids running production infrastructure. Incumbents can bundle AI mapping for free, so a plug-in has no lasting moat. The value is the whole path: template, mapping, live delivery, and drift watch. That's what lets a vendor's implementation person do the job alone.

## 3. OKR cascade

> **Objective:** Make Plumb the way a dining software vendor connects a new customer's EHR, without an integration engineer.
>
> - **KR1:** One dining software vendor is signed as a design partner by March 31, 2027.
> - **KR2:** In a demo, a vendor's implementation person takes a care-to-dining template from synthetic EHR sample to first live message in under 30 minutes, without help.
> - **KR3:** A vendor's implementation person sets up a second sample site from the same template in under 1 hour, without help.
>
> _Updated in Module 2: I don't expect to sign a design partner for at least 3 months, so KR1 now targets signing, and "live and paying" moves to next quarter. KR2 and KR3 now measure the wizard and template reuse in demos until a partner is live. The real-site version of KR2 (first live message within 5 working days of EHR access, with access time under 4 weeks) moves to next quarter._

## 4. AI pressure-test

**Most valid challenge:** The access point. I assumed mapping is the slow part, but going live at a new site also depends on EHR access, security reviews, and the customer's IT queue, which I don't control. If that takes weeks, my "live in days" promise and KR2 both fail, no matter how good AI Mapping is.

**What I will change and what I will defend:** Change: I added access to Capabilities Required (a security review pack for customers, and the on-site agent or the EHR's own marketplace as the route in). KR2 now measures from the day access is granted to the first live message, and I track access time separately. I also replaced the design partner signatures in KR1 with "the partner sends every new customer site through Plumb." Defend: the hard no stays for now. A plug-in would get data faster, but supporting two products as a team of one would split my focus before either one works. I'll revisit it if I have no design partner by the end of Q1 2027.
