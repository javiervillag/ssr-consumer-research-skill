# AI Consumer Research Skill — SSR Method

Run a simulated consumer survey on any product idea in minutes, for free. This Claude AI skill is built for business owners and founders who want a fast, directional read on whether an idea has legs — before spending thousands on a real research panel. No survey software, no agency, no wait. Just describe your product and Claude interviews a panel of synthetic consumers for you.

---

## The Problem

Real consumer research is expensive and slow. A proper concept test can cost $10,000–$50,000 and take weeks of recruiting, fielding, and analysis. Most early-stage founders skip it entirely and find out the hard way that nobody wanted what they built.

The obvious shortcut — just ask AI — doesn't work either. Ask an LLM to rate your product idea on a 1–5 scale and it will say 3. Every time. It's not being lazy; it genuinely can't assign numbers well. The result is a flat, useless distribution that tells you nothing about whether real people would buy your thing.

---

## How It Works

This skill uses a research-validated technique called **Semantic Similarity Rating (SSR)**. Instead of asking the AI to pick a number, it does three things:

**1. Creates detailed consumer personas.** Real-feeling people with names, ages, incomes, lifestyles, and opinions — not "Persona A." People who feel like your actual customers, plus a couple who definitely aren't.

**2. Asks each persona to describe their reaction in plain words.** Like a real survey respondent would answer. *"Honestly, $149 is steep for coffee, but I do love my morning ritual..."* No numbers requested, no numbers invented.

**3. Scores those descriptions by comparing them to reference phrases.** Things like *"I'd definitely buy this"* or *"It's very unlikely I'd buy it."* Whichever phrase the response sounds most like determines the score. The text becomes the rating — and the rating reflects something real.

The result: a realistic distribution of responses across your panel, not a meaningless flat "3," plus the verbatim reasons behind every score.

---

## What the Research Says

This method was developed and validated by researchers at PyMC Labs and Colgate-Palmolive:

> Maier et al. (2025). *LLMs Reproduce Human Purchase Intent via Semantic Similarity Elicitation of Likert Ratings.* [arXiv:2510.08338](https://arxiv.org/abs/2510.08338)

The paper tested the method against **9,300 real human responses** across **57 consumer surveys** and found it achieved roughly **90% of human test–retest reliability** — meaning the synthetic panel was almost as consistent with itself as real humans were. Response distributions closely matched actual human panels.

One finding drives everything: detailed, specific personas are not optional. Without rich demographic detail, accuracy drops from ~90% to ~50%. The skill enforces this — it won't let you skip the customer picture.

**To be straight with you:** the method was only validated on personal care products (oral care, skin care). How well it works in other categories is unverified. It does not reliably replicate demographic subgroup effects. It is not a replacement for real research — it's a cheap first pass that helps you figure out which ideas *deserve* real research.

---

## How to Use the Skill

**Option 1 — Claude Cowork (easiest)**
If you use Claude's Cowork mode, paste the contents of `SKILL.md` into your skills folder. It will trigger automatically when you say things like *"test this product idea,"* *"run a consumer survey,"* or *"would people buy this."*

**Option 2 — Claude.ai (any plan)**
1. Open [claude.ai](https://claude.ai) and start a new conversation
2. Copy the full contents of `SKILL.md` from this repo
3. Paste it into your message, followed by your product description
4. Claude walks you through the rest as a conversation — no forms, no setup required

**What to have ready before you start:**
- What your product is and what it does
- The price (the single biggest driver of purchase intent — don't skip it)
- A rough picture of your target customer: age range, income, lifestyle, where they live

---

## What You Get

Claude runs the session as a conversation, not a form. At the end you receive:

- **A panel of 6 synthetic consumers** — each with a name, background, and a distinct perspective on your product (enthusiasts, skeptics, pragmatists, and edge cases)
- **A verbatim reaction from each persona** — written in their voice, the way a real survey respondent talks
- **A purchase intent score for each** (1–5), mapped from their words to a rating using the SSR anchor phrases
- **A distribution summary** — how many said yes, maybe, or no, and what the shape of the response means (bimodal? skewed positive? flat?)
- **A plain-English debrief** — the headline insight, the 2–3 most revealing quotes, what's driving interest, what's killing it, and 2–3 concrete next steps
- **A clear disclaimer** reminding you this is a directional signal, not market truth

---

## Honest Limitations

- **Simulated responses, not real humans.** These are AI personas. Treat results as a screen, not a verdict.
- **Only validated on personal care products.** The research tested oral care and skin care. Your category may behave differently.
- **No demographic subgroup conclusions.** Gender, regional, and ethnic differences were not reliably replicated. Don't draw those conclusions from this output.
- **No real purchasing pressure.** Simulated consumers have no actual budget, no spouse to check with, no shelf of competing products in front of them.
- **Not investment-grade research.** Before a launch decision, a pricing commitment, or anything you'll show investors, validate with real humans.

**The right use:** screen 5–10 concepts cheaply, then spend your real research budget on the 1–2 survivors.

---

## Credits

Original research: Maier et al. (2025), PyMC Labs & Colgate-Palmolive — [arXiv:2510.08338](https://arxiv.org/abs/2510.08338)

Skill built by [AI Daddy](https://aidaddy.com).
