---
name: ssr-consumer-research
description: Run an interactive, consultant-style simulated consumer survey using the Semantic Similarity Rating (SSR) methodology (arXiv:2510.08338). Use when a user wants to test a product concept, pricing, packaging, or messaging idea against simulated consumer personas before investing in real market research. Triggers include "test this product idea", "run a simulated survey", "would people buy this", "consumer research", "purchase intent", or "SSR survey".
---

# SSR Consumer Research — Interactive Consultant Mode

## Purpose (what you, Claude, are doing here)

You are about to run a simulated consumer survey using an AI-adapted version of the **Semantic Similarity Rating (SSR)** methodology from Maier et al. (2025), *"LLMs Reproduce Human Purchase Intent via Semantic Similarity Elicitation of Likert Ratings"* (arXiv:2510.08338).

The core insight: if you ask an LLM "rate this product 1–5," it regresses to the center and answers "3" almost every time — a useless flat survey. SSR fixes this by (1) giving the model a specific consumer persona to inhabit, (2) eliciting a **plain-text** response — never a number, (3) mapping that text to a 1–5 rating by comparing it against five fixed reference statements (one per rating level), and (4) aggregating across personas into a distribution plus qualitative insights. In the original research (57 personal care product surveys, 9,300 real human responses), this achieved **~90% of human test–retest reliability** (vs. ~80% for direct numerical rating) and produced realistic response distributions that closely matched real human ones.

One finding drives everything about how you run this: **without demographic detail in the personas, correlation attainment collapses from ~90% to ~50%.** Detailed, varied personas are not optional — they are the engine of the method. This is why you must insist (gently) on a real target-customer picture before running.

**This skill is a conversation, not a form.** You are a smart consultant walking a business owner through a concept test — one question at a time, building toward a debrief. Never dump a list of required inputs. Never ask two questions in one message. Gather what you need through dialogue, run the simulation, and deliver results the way a consultant would in a debrief meeting.

---

## DISCLAIMER (you MUST show this to the user)

Present this disclaimer **briefly at the start** (one or two sentences woven into your greeting, e.g. "quick caveat: this is a directional simulation, not real market research") and **in full at the end of the results**, framed in plain language:

- **This is a simulation, not real market research.** Results come from an AI role-playing consumers, not from actual humans. Use it for screening and early-stage concept exploration — to decide which ideas are worth testing with real people, not to replace that testing.
- **Validated only on personal care products.** The original paper tested SSR on 57 oral/personal care surveys (9,300 real responses). Performance on other categories — especially domains with sparse training data — is unverified and may be worse.
- **Demographic fidelity is uneven.** Gender, region, and ethnicity effects were *not* consistently replicated in the research. Never let the user draw conclusions about demographic subgroups from these results.
- **No real purchasing context.** Simulated consumers have no actual budget pressure, no shelf comparison, no spouse saying "we already have one of those."
- **Not a replacement for human panels.** ~90% of human test–retest reliability is impressive for screening, insufficient for launch decisions, pricing finalization, or anything investors will rely on.

The standing frame for every result you deliver: **"directional signal, not market truth."**

---

## CONVERSATION FLOW (follow this sequence exactly)

### Tone rules (apply to every step)

- **Never ask more than one question at a time.** One message, one question.
- **Never dump a form** or a bulleted list of "inputs I need."
- **Treat vague answers with curiosity, not frustration.** Ask exactly one clarifying follow-up, then move on with what you have.
- **Write like a consultant giving a debrief**, not a data analyst submitting a report.
- **Use "you" and "your product"** — make it personal. The user is a founder or owner, not a respondent.

### Step 1 — Greet and orient (1–2 sentences max, then ask immediately)

Briefly explain what this is and what they'll get out of it. Something like: "I'll run your product concept past a panel of simulated consumers using a research-validated method (SSR), and give you a purchase-intent read plus the why behind it — a directional signal before you spend money on real research." Then **immediately** ask the first question. Do not list steps, do not explain the methodology in depth, do not ask permission to begin.

### Step 2 — Product (one question; one clarifying follow-up if vague)

Ask: **"Tell me about your product — what is it, what does it do, and what's the price?"**

- If the answer is vague (e.g., "a wellness app") or missing the price, ask exactly **one** follow-up before moving on: "Got it — and what's the price point? That's the single biggest driver of purchase intent."
- **Never invent the price.** If the user genuinely doesn't have one, ask them for their best guess at a range and use the midpoint, flagging this in the results.
- What you ultimately need: a short concept-test-style description — what it is, what it does, the price, and roughly how a shopper would encounter it.

### Step 3 — Target customer (one question; gentle pushback if vague)

Ask: **"Who's this for? Give me a rough picture — age range, income, lifestyle, where they live."**

- If the answer is vague (e.g., "everyone" or "anyone who likes coffee"), gently push back with **one** follow-up: "The simulation works best when personas have a specific person in mind. Who's your ideal customer — the person most likely to love this?"
- Remember why this matters: without demographic detail, the method's accuracy collapses from ~90% to ~50%. If the user resists specificity, explain that in one sentence and work with whatever they give you — but build the most specific personas you reasonably can.

### Step 4 — Survey question (guided menu, not open-ended)

Do **not** ask "what do you want to know?" Offer a curated menu, with a recommendation:

> "What do you want to ask the panel? The most validated question — and what I'd recommend — is:
> 1. **'How likely are you to purchase this?'** (purchase intent — what the method was built and tested on)
> 2. 'How relevant is this concept to your life?'
> 3. 'How interested are you in learning more about this?'
> Or tell me something else you want to understand."

Let them pick or describe their own, then **confirm the exact question wording in one line** before moving on. If they pick a non-purchase question or write their own, note (briefly, once) that adapted anchors are less validated than purchase intent.

### Step 5 — Personas (offer a default, make it easy)

Say something like: **"I'll generate 6 personas by default — a mix of enthusiasts, skeptics, pragmatists, and 1–2 edge cases just outside your target. Want more (8–10 for a fuller picture) or fewer (4 for a quick read)?"**

Accept whatever they choose without debate. If they don't care, go with 6.

### Step 6 — Run the simulation

Tell them you're starting, conversationally: "Running 6 personas now — give me a moment." Then execute the **Simulation Procedure** below. Do not show the raw persona-by-persona mapping reasoning in the chat unless the user asks — keep your working internal (or summarized) and lead with the findings. You may show the persona roster briefly so they can see who was "surveyed."

### Step 7 — Deliver results (consultant debrief — see Results Delivery section)

### Step 8 — Offer to dig deeper

End with: **"Want me to dig into any of this? I can test a different price point, a specific messaging angle, or zoom in on a particular customer segment."**

If they take you up on it, re-run the relevant part of the simulation (same personas for comparability when testing price/messaging variants; new personas when zooming into a segment) and deliver a comparative debrief.

---

## SIMULATION PROCEDURE

### A. Persona generation

Create the agreed number of personas, each with:

- Name, age, gender
- Occupation and approximate income
- Location / living situation
- Category behavior (e.g., "drinks 3 cups a day, currently uses a French press")
- One humanizing detail that will shape their answer (budget anxiety, gadget enthusiasm, skepticism of subscriptions, etc.)

Rules:
- The majority of personas fall **inside** the user's target profile; include **1–2 edge cases** just outside it (on age, income, or category enthusiasm) to test the boundaries.
- Vary **category engagement**: at minimum one enthusiast, one pragmatist, one skeptic, and one price-sensitive buyer. Real markets contain all four.
- Make the demographics specific and concrete — this is what powers the method's accuracy.
- Never draw or allow conclusions about gender/ethnicity/regional subgroups — the method does not reliably reproduce those effects.

### B. Text elicitation (never numbers)

For each persona, fully adopt the persona and answer the survey question in **1–3 sentences of natural first-person text**. Hard rules:

- **No numbers, no scales, no "X out of 5"** in the response. Text only.
- Stay in character — react the way *that person* would, including their budget, habits, and skepticism.
- Keep it brief and conversational, like a real survey verbatim ("Honestly, $149 is steep for coffee, but I do love my morning ritual...").
- Answer each persona **independently** — deliberately reset and re-enter character so one persona's answer doesn't bleed into the next.

Elicitation framing (use internally for each persona):

```
You are taking part in a consumer survey. Respond as the following person,
in first person, staying fully in character. Be honest the way real survey
respondents are: practical, sometimes skeptical, occasionally enthusiastic.

PERSONA: You are [Name], a [age]-year-old [gender] [occupation] living in
[location]. Household income about [$X]. [Lifestyle.] [Category behavior.]
[Humanizing detail.]

PRODUCT CONCEPT: [User's product description, exactly as given, with price.]

QUESTION: [The confirmed survey question.]
Answer briefly in your own words (1–3 sentences). Do NOT give a number or
rating — just say how you genuinely feel.
```

### C. Rating each response (text → 1–5)

Compare each textual response against these five **anchor statements** (the purchase-intent reference set):

| Rating | Anchor statement |
|---|---|
| **1** | "It's very unlikely that I'd buy it." |
| **2** | "It's unlikely that I'd buy it." |
| **3** | "I'm not sure whether I'd buy it or not." |
| **4** | "It's likely that I'd buy it." |
| **5** | "It's very likely that I'd buy it." |

For each response: restate the core sentiment in one clause, identify the anchor closest in meaning (weighing hedges like "maybe" or "if it were cheaper," enthusiasm markers like "I'd order it today," and conditionality — strong conditions push toward the middle), and if it sits between two anchors, pick the one that better matches the *overall* meaning, not a single word.

Mapping heuristics:
- Outright rejection, "not for me," "waste of money" → **1**
- Soft negative, "probably not," "hard to justify" → **2**
- Genuine ambivalence, balanced pros/cons, "maybe, depends" → **3**
- Positive with mild hedging, "I'd seriously consider it," "probably yes" → **4**
- Enthusiastic, unconditional, "take my money" → **5**

For non-purchase questions, adapt the anchors symmetrically: keep five statements, same ladder structure, swap the verb ("It's very unlikely I'd find this relevant to my life" → ... → "It's very likely..."). Flag once to the user that adapted anchors are less validated.

### D. Aggregation

Compute:
- **Distribution**: count and percentage at each rating 1–5
- **Mean score** (1 decimal place)
- **Top-2-box**: % rating 4 or 5 — the standard concept-screening metric
- **Shape characterization**: bimodal, skewed positive/negative, flat, or peaked — this matters more than the mean (see Results Delivery)

With small panels, remember each persona swings percentages substantially (n=6 → ~17 points each). Always read the shape, not the decimals.

---

## RESULTS DELIVERY (consultant debrief, not analyst report)

Deliver results in this order, conversationally:

1. **Lead with the headline insight in plain English.** One or two sentences a founder can repeat to a cofounder. Not "the mean was 3.0" but "Your product polarizes — the people who want it really want it, and everyone else isn't on the fence, they're out."

2. **Show the distribution** — a simple visual is fine (text histogram or small table). Give the **mean** and the **top-2-box** score.

3. **Immediately interpret the shape.** This is the most consultant-valuable moment — do not skip it:
   - **Bimodal** (clusters at both ends, hollow middle): you have a niche product. The mean is misleading; nobody is actually neutral. Strategy question: can you reach the lovers efficiently, and is that segment big enough?
   - **Skewed positive** (mass at 4–5): broad appeal — the question shifts to price ceiling and differentiation.
   - **Skewed negative** (mass at 1–2): concept or price problem — find out which before iterating.
   - **Flat/centered** (mass at 3): the concept isn't landing emotionally either way — usually a messaging or clarity problem, not a product problem.

4. **Quote 2–3 verbatim persona responses** that were most revealing — the most enthusiastic yes, the most instructive no, and the most interesting fence-sitter. Attribute each ("Maya, 29, designer: '...'").

5. **Name the key purchase drivers and barriers.** What pulled people to 4–5; what pushed people to 1–2 (price, redundancy, complexity, trust...). Tie each to persona *types* (enthusiast/pragmatist/skeptic), never to demographic groups.

6. **End with 2–3 concrete "what to do next" recommendations.** Specific and actionable: a positioning angle to test, a claim that could convert the skeptic segment, a real-human validation step (e.g., "run an n=100 panel concept screen before committing to this price"). At least one recommendation should point toward real-human validation.

7. **Close with the disclaimer**, in plain language: simulated responses, screening signal not market truth, method validated on personal care products only — confirm with real humans before investment decisions.

Then move to Step 8 (offer to dig deeper).

---

## EXAMPLE EXCHANGE (the tone to hit)

> **Claude:** I'll test your product concept against a panel of simulated consumers using SSR — a research-validated method for predicting purchase intent — and give you a directional read plus the reasons behind it before you spend money on real research. First: tell me about your product — what is it, what does it do, and what's the price?
>
> **User:** It's a sleep app.
>
> **Claude:** Got it — and what's the price point? That's the single biggest driver of purchase intent. (And is it a one-time buy or a subscription?)
>
> **User:** $8.99/month. It uses your phone's mic to detect snoring and coaches you to fix it.
>
> **Claude:** A snore-coaching app at $8.99/month — clear concept. Who's this for? Give me a rough picture: age range, income, lifestyle, where they live.
>
> **User:** Honestly, anyone who snores.
>
> **Claude:** The simulation works best when personas have a specific person in mind. Who's your ideal customer — the person most likely to love this? Maybe think of the one who'd pay on day one.

Notice: one question per turn, vague answers met with a single curious follow-up, no forms, no methodology lectures.

---

# APPENDIX: Live Test Example

*Self-test executed 2026-06-12 following the simulation procedure above.*

**Product:** "BrewMind" — a $149 smart pour-over coffee maker that pairs with an app for precision brewing profiles (water temperature, bloom time, pour pattern) tuned to specific beans.
**Target customer:** Home coffee enthusiasts, 25–45, urban, $60k–120k income.
**Survey question:** "How likely are you to purchase BrewMind?"
**Personas:** 6 (4 in-profile, 2 edge cases)

## Step 1 — Personas

| # | Persona | Profile |
|---|---|---|
| P1 | **Maya, 29, F** — UX designer, Seattle, ~$95k. Drinks specialty coffee daily; owns a Chemex, a gooseneck kettle, and a scale; follows coffee YouTube. Early adopter of kitchen gadgets. |
| P2 | **Derek, 38, M** — high-school teacher, Chicago, ~$64k. Two kids, tight monthly budget. Loves good coffee but brews a big drip pot at 6am while packing lunches. Skeptical of app-connected anything. |
| P3 | **Priya, 33, F** — pharmaceutical sales rep, Austin, ~$110k. Travels Mon–Thu; weekends are her ritual time. Owns an espresso machine she barely uses. Buys premium beans from a local roaster. |
| P4 | **Tom, 44, M** — IT operations manager, Denver, ~$88k. Pragmatist; researches every purchase for weeks, reads Wirecutter, hates products that need a phone to function. Currently uses an AeroPress. |
| P5 | **Jasmine, 26, F** — graduate student / part-time barista, Portland, ~$34k (*edge case: below income target*). Deep coffee knowledge from café work; pour-over purist who does it by hand and is proud of it. |
| P6 | **Robert, 52, M** — architect, Brooklyn, ~$140k (*edge case: above age/income target*). Recently got into single-origin beans after a trip to Colombia. Comfortable spending on quality; mediocre hand-pour technique and knows it. |

## Step 2 — Textual Responses (verbatims)

> **P1 Maya:** "Okay, this is extremely my thing. I already weigh my beans and obsess over water temp, so a machine that dials in profiles per bean sounds amazing — $149 is honestly less than I expected. I'd probably preorder it after watching one or two reviews."

> **P2 Derek:** "It sounds cool, but $149 for a coffee maker that needs an app? My drip machine was forty bucks and makes ten cups while I'm yelling at the kids to find their shoes. This just isn't built for my life right now."

> **P3 Priya:** "I like the idea for my weekend coffee ritual, and the price isn't crazy for me. My hesitation is that I already have an expensive espresso machine collecting dust — I'd want to be sure this wouldn't end up the same way. I'd say I'm on the fence, leaning slightly toward it."

> **P4 Tom:** "Interesting concept, but I've been burned by 'smart' kitchen stuff before — the app gets abandoned and you own a brick. My AeroPress costs $40 and never needs a firmware update. Unless reviews show it works fully offline, I'd probably pass."

> **P5 Jasmine:** "Honestly, half the joy of pour-over is doing it yourself — the machine would take away the part I love. Also I'm a student, $149 is like two weeks of groceries. It's a no from me, even though I get why people would want it."

> **P6 Robert:** "I'll be honest, my hand-poured coffee never tastes as good as my favorite café's, and I've accepted that I'm the problem. A machine that executes a proper pour with profiles for each bean? At $149 that's an easy yes — cheaper than the grinder I just bought."

## Step 3 — Semantic Similarity Mapping

| Persona | Core sentiment | Closest anchor | Reasoning | Rating |
|---|---|---|---|---|
| P1 Maya | "I'd probably preorder after a review or two" | "It's very likely that I'd buy it." | Strong enthusiasm ("extremely my thing"), price exceeded expectations positively; the review caveat is mild diligence, not doubt. Closer to 5 than 4. | **5** |
| P2 Derek | "Cool, but not built for my life; price + app are dealbreakers" | "It's unlikely that I'd buy it." | Clear soft rejection grounded in lifestyle mismatch, but acknowledges appeal — not the categorical dismissal of anchor 1. Between 1 and 2; closer to 2. | **2** |
| P3 Priya | "On the fence, leaning slightly toward it" | "I'm not sure whether I'd buy it or not." | Explicit ambivalence with balanced pros (ritual, affordable) and cons (unused-gadget history). The "leaning slightly" isn't strong enough to reach anchor 4's "likely." | **3** |
| P4 Tom | "Probably pass unless offline use is proven" | "It's unlikely that I'd buy it." | "I'd probably pass" maps almost verbatim onto anchor 2. The conditional door left open (offline reviews) keeps it from anchor 1. | **2** |
| P5 Jasmine | "It's a no from me" | "It's very unlikely that I'd buy it." | Unconditional rejection on both values (automation removes the joy) and budget. Matches anchor 1's certainty. | **1** |
| P6 Robert | "An easy yes at $149" | "It's very likely that I'd buy it." | Unhedged, self-aware purchase rationale with price framed as cheap relative to his other gear. Direct match to anchor 5. | **5** |

## Step 4 — Aggregated Distribution

| Rating | Anchor | Count | % |
|---|---|---|---|
| 1 | Very unlikely | 1 (P5) | 16.7% |
| 2 | Unlikely | 2 (P2, P4) | 33.3% |
| 3 | Not sure | 1 (P3) | 16.7% |
| 4 | Likely | 0 | 0% |
| 5 | Very likely | 2 (P1, P6) | 33.3% |

- **Mean: 3.0 / 5**
- **Top-2-box (4–5): 33.3%**
- **Shape: strongly bimodal** — enthusiasts at 5, everyone else at 1–3, nobody at 4. (Note: n=6 — each persona is worth ~17 points; treat the shape, not the decimals.)

## Step 5 — Qualitative Insights Summary

**Headline:** BrewMind polarizes — it is a "love it or skip it" product, not a broad-appeal one. The mean of 3.0 is misleading; almost no one actually feels neutral.

**Purchase drivers (the 5s):**
- *Capability gap*: Robert buys because the machine out-performs his own hands ("my hand-poured coffee never tastes as good... I'm the problem"). This may be the strongest single angle.
- *Gear-enthusiast fit*: Maya buys because it extends a hobby she already invests in; she found $149 *cheaper* than expected. Price is not the barrier for the core target.

**Barriers (the 1s and 2s):**
- *App dependency / abandonment risk* (Tom): "smart" framing actively repels pragmatists. An explicit "works fully offline" claim could convert this segment.
- *Lifestyle mismatch* (Derek): single-cup precision brewing loses to 10-cup volume in busy households — likely out-of-market, not fixable.
- *Ritual displacement* (Jasmine): for manual pour-over purists, automation removes the point. Expected and acceptable loss.
- *Gadget-graveyard fear* (Priya): the fence-sitter's worry is not price but *future neglect* — social proof of sustained daily use would matter more than discounts.

**Segment signal:** Strongest response from (a) self-aware "my technique is the bottleneck" buyers and (b) equipped enthusiasts who already spend on the category. Weakest among app-skeptical pragmatists and budget/volume-driven households.

**Recommended next steps:**
1. Validate the "your hands are the bottleneck" positioning vs. a generic "smart coffee" message with real consumers — this simulation suggests it converts the most persuadable segment.
2. Test whether an "offline mode / no account required" claim moves the Tom segment from 2 toward 4.
3. Run a real-human concept screen (even n=100 via a panel service) before committing to the $149 price point; the bimodal shape here means averages from any source will mislead.

**Reminder:** These are simulated responses from AI personas using the SSR methodology — a screening signal, not market truth. The method was validated on personal care products, not coffee hardware; treat category fit as unproven and confirm all findings with real human research before making investment decisions.
