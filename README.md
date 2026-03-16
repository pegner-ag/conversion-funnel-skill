# Conversion Funnel Architect

**A Claude Code skill that turns your AI assistant into a sales funnel strategist.**

Build high-converting funnels using the combined frameworks of Russell Brunson (*DotCom Secrets*) and Sabri Suby (*Sell Like Crazy*) — without reading 600 pages first.

## What it does

When you say "build me a landing page" or "create a sales funnel", Claude Code activates this skill and guides you through:

- **Dream Buyer profiling** — demographics, psychographics, Dream 100 targeting
- **Lead magnet design** — HVCOs that convert at 30-60%
- **Tripwire & core offer architecture** — Value Ladder positioning with Godfather Offers
- **Sales copy** — Epiphany Bridge scripts, headline formulas, bullet fascinations, price anchoring
- **Email sequences** — Soap Opera (days 1-5), Seinfeld (ongoing), Godfather (unconverted leads), Breakup emails
- **Technical implementation** — HTML skeletons, GA4 conversion tracking, UTM persistence, checkout flows
- **Launch checklist** — 60+ items from pre-build through post-launch week 1

## Install

```bash
npx skills add pegner-ag/conversion-funnel-skill
```

## Trigger phrases

The skill activates automatically when you ask Claude Code to:

> "create a funnel", "build a landing page", "design a lead magnet", "write a sales page", "set up email nurture sequence", "optimize conversion rate", "create a tripwire", "write sales copy", "build a webinar funnel", "design a checkout flow"

## What's inside

```
skills/conversion-funnel/
  SKILL.md                         # Core skill (7 phases + funnel types + A/B testing)
  references/
    copy-formulas.md               # Headlines, CTAs, Epiphany Bridge, guarantees, price anchoring
    email-sequences.md             # Soap Opera, Seinfeld, Godfather sequences + deliverability
    technical-patterns.md          # HTML skeleton, GA4 events, UTM tracking, metrics dashboard
    launch-checklist.md            # 60+ items: pre-build, build, email, tracking, legal, launch
```

## Philosophy

> "If your funnel isn't converting, change the **offer** before you change the button color."
> — The 80/20 rule baked into every recommendation.

**Never:** send paid traffic to a homepage, use fake scarcity, skip follow-up emails, or optimize vanity metrics over revenue.

**Always:** test the entire flow yourself, track source attribution, send breakup emails to non-responders, and calculate max allowable CAC before spending on ads.

## Credits

Frameworks synthesized from:
- Russell Brunson — *DotCom Secrets*, *Expert Secrets* (Value Ladder, Epiphany Bridge, Soap Opera Sequence)
- Sabri Suby — *Sell Like Crazy* (8-Phase System, HVCO, Godfather Offer, Dream 100)

## License

MIT
