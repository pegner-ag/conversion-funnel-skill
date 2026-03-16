---
name: conversion-funnel
description: >
  Use when building landing pages, sales funnels, opt-in pages, checkout flows,
  email sequences, or lead magnets. Use when the user asks to "create a funnel",
  "build a landing page", "design a lead magnet", "write a sales page",
  "set up email nurture sequence", "optimize conversion rate", "create a tripwire",
  "write sales copy", "build a webinar funnel", or "design a checkout flow".
version: 0.1.0
---

# Conversion Funnel Architect

Design and implement high-converting sales funnels. Combines Russell Brunson's Value Ladder & funnel architecture with Sabri Suby's "Sell Like Crazy" 8-phase system.

## Core Principle

Never sell a high-ticket offer to cold traffic. Warm them up through escalating value exchanges:

```
TRAFFIC (cold/warm/hot)
  → [1] DREAM BUYER ID        — Who exactly are you targeting?
  → [2] BAIT (Lead Magnet)    — Free, irresistible, solves ONE problem
  → [3] GODFATHER (Tripwire)  — Low-cost, no-brainer, proves value
  → [4] CORE OFFER            — Your main product/service
  → [5] PROFIT MAXIMIZER      — Upsell, cross-sell, premium tier
  → [6] RETURN PATH           — Email, retargeting, community
  → [7] REFERRAL LOOP         — Turn customers into advocates
```

## Phase 1: Dream Buyer

Before writing code or copy, complete the Dream Buyer Canvas:

- **Demographics:** Industry, role, company size, revenue, geography
- **Psychographics (more important):** Biggest frustration, what they've tried that failed, dream outcome, what they'd pay anything to solve
- **Brunson's 4 Questions:** (1) WHO is your dream customer? (2) WHERE do they congregate? (3) What BAIT attracts them? (4) What unique RESULT can you give them?
- **Pain-Desire Bridge:** Current state (hell) → Desired state (heaven) → The gap = your product

Apply Suby's "Herd" principle: identify 100 places buyers already gather (podcasts, newsletters, LinkedIn groups). Redirect existing audiences, don't create new ones.

## Phase 2: The Bait (Lead Magnet)

Suby's HVCO (High Value Content Offer) rules:
1. Solves a specific problem — not "10 Tips" but "The Exact Template That Generated $2.4M"
2. Delivers a quick win — consumable in under 10 minutes
3. Demonstrates expertise — positions you as authority
4. Creates an "aha" moment — changes how they see their problem
5. Naturally leads to paid offer

Lead magnet types by conversion rate: Quiz/Assessment (40-60%), Checklist (30-50%), Calculator/Tool (35-55%), Report/Guide (20-40%), Video Training (15-30%).

Opt-in page anatomy: Pre-headline (qualifier) → Headline (big promise + specificity) → Sub-headline (address objection) → Hero image (mockup) → 3-5 bullet fascinations → Social proof → Form (2 fields max) → CTA button (NEVER "Submit" — use "Send Me The Guide")

For cold traffic, use Suby's Magic Lantern: Content first → Retarget with opt-in → Lead magnet.

## Phase 3: Godfather Offer (Tripwire)

Make an offer so good they'd feel stupid saying no.

- Price: $1-$47 (B2C) or free trial (SaaS)
- Purpose: NOT profit — convert a lead into a BUYER (10x more likely to buy again)
- Value disparity: deliver $500+ perceived value for $7-27

Suby's formula: `[Irresistible Result] + [Compressed Timeframe] + [Risk Reversal] = Godfather Offer`

After purchase, immediately present One-Time Offer (OTO) on thank-you page. One-click upsell, no re-entering payment info.

## Phase 4: Core Offer

Use Brunson's Stack Slide — don't just present the product, STACK all value:
- Core Product: Value $X,XXX
- Bonus 1-4: Value $XXX each
- Total Value: $X,XXX → Today's Investment: $XXX

Sales page structure: Hook (pattern interrupt) → Story (Epiphany Bridge) → Content (break & rebuild beliefs) → Offer (the stack) → Risk Reversal (better-than-money-back guarantee) → Urgency (must be real) → CTA (one action, repeat 3-5x) → FAQ (objections disguised as questions)

For the Epiphany Bridge story script and copy formulas, read `references/copy-formulas.md`.

Match sales mechanism to price: $0-50 sales page, $50-500 VSL/webinar, $500-2K webinar+application, $2K-10K phone call, $10K+ in-person.

## Phase 5: Profit Maximizer

Brunson's Value Ladder: FREE → $7-47 tripwire → $97-497 core → $997-4,997 premium → $5K-100K high-ticket. Each rung sells the rung above it.

Upsell flow: Immediate OTO (thank-you page) → Cross-sell email (day 3-7) → Ascension offer (day 14-30) → High-ticket application (day 30-90).

## Phase 6: Email Sequences

Three sequence types — see `references/email-sequences.md` for full templates:

1. **Soap Opera Sequence** (Brunson, days 1-5): Serialized storytelling. Backstory → Turning Point → Epiphany → Hidden Benefits → Urgency.
2. **Seinfeld Sequence** (day 6+, ongoing): Entertaining daily emails with product plug. Story → Lesson → CTA.
3. **Godfather Sequence** (Suby, for unconverted): Value → Case study → Objection crusher → Godfather Offer → Last chance → Breakup email.

The breakup email ("Should I remove you?") is counterintuitively one of the highest-converting emails.

## Phase 7: Traffic

Brunson's 3 types: Traffic you CONTROL (paid ads → send to squeeze page, never homepage), Traffic you DON'T control (SEO, social → convert to owned), Traffic you OWN (email list = most valuable).

Rule: always convert controlled and uncontrolled traffic into owned traffic.

## Funnel Types

1. **Lead Squeeze:** Ad → Squeeze Page → Thank You
2. **Free + Shipping:** Ad → Sales Page → Order Form → OTO → Confirmation
3. **Webinar:** Ad → Registration → Confirmation → Webinar → Replay → Sales
4. **Product Launch:** PL Video 1 → 2 → 3 → Cart Open → Cart Close
5. **Application (High-Ticket):** Ad → Long Sales Page → Application → Call Booking → Call
6. **Challenge:** Ad → Registration → 5-14 Day Challenge → Offer → Sales

## A/B Testing Priority (by impact)

1. THE OFFER ITSELF (2-5x improvement possible)
2. Headline (20-50%)
3. CTA button (10-30%)
4. Social proof (10-25%)
5. Form fields (5-20%)
6. Page length (variable — cold=longer, warm=shorter)

Suby's 80/20: if conversion is below 1%, change the offer before tweaking button colors.

## Technical Implementation

For HTML skeletons, GA4 tracking patterns, UTM preservation, and checkout flow code, read `references/technical-patterns.md`.

For the complete launch checklist, read `references/launch-checklist.md`.

## Red Flags

NEVER: send paid traffic to homepage, use fake scarcity, hide B2B pricing, skip follow-up emails, optimize vanity metrics over revenue, launch without a working email sequence.

ALWAYS: test the entire flow yourself, track source attribution (UTM), send breakup emails to non-responders, calculate max allowable CAC before spending on ads.
