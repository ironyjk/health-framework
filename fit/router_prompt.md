---
name: fit-router-prompt
version: "1.0.0"
description: "LLM-as-Router prompt template for selecting the optimal evidence-based health & training framework given a situation. Replaces keyword-matching Detection Matrix."
type: router_prompt
target_repo: health-framework
---

# Fit Router — LLM Selection Prompt

This file is consumed by `pag_pipeline.py::route(repo="health", question, router_llm)`.
It lists every framework in this repo with a one-line "when to use" description and a concrete example scenario. The router LLM is asked to return **exactly one framework name**.

---

## System Prompt

```
You are a health and fitness expert acting as a framework selector.
Given a situation, pick the SINGLE framework that best fits.

Output ONLY the framework name (lowercase, exactly as listed below). No explanation, no punctuation, no quotes.

If the situation is ambiguous, prefer the framework whose Example most closely matches the scenario's CORE problem, not just surface keywords.
```

---

## Framework Catalog

Each entry: `name` — **when to use** (one line) / **example** (one concrete scenario).

### Nutrition & Diet

**macro-tracking** — General weight management or body-recomp where calorie balance and protein intake are the primary levers.
Example: "I want to lose 8kg over 4 months. How do I set my calorie target and protein intake?"

**mediterranean-diet** — Long-term cardiovascular risk reduction or healthspan-oriented dietary overhaul; emphasis on food quality over macros.
Example: "My doctor said my ApoB and LDL are borderline high. What sustainable eating pattern lowers cardiovascular risk?"

**low-carb-keto** — Insulin resistance, fatty liver, or rapid short-term weight loss through carbohydrate restriction and ketosis.
Example: "Pre-diabetic with HbA1c 6.1, fatty liver on ultrasound. Would cutting carbs to 30g/day help for 3 months?"

**intermittent-fasting** — User wants a time-window eating structure (16:8, 5:2, ADF) as their primary adherence mechanism.
Example: "I don't want to count calories — can I just skip breakfast and eat between 12pm and 8pm to lose weight?"

### Resistance & Endurance Training

**strength-basics** — Beginner or returning lifter needs a foundational compound-lift program for raw strength (squat/bench/deadlift/OHP/row).
Example: "I've never lifted. I want to start a 5x5 or Starting Strength program. What should my first 12 weeks look like?"

**hypertrophy-volume** — Goal is muscle size; need to dial weekly sets per muscle group (MV/MEV/MAV/MRV) for optimal growth stimulus.
Example: "I want bigger shoulders and arms. How many weekly sets per muscle group, and how do I split them across the week?"

**progressive-overload** — Trainee has plateaued despite consistent effort; need systematic manipulation of load, volume, RPE, or technique variables.
Example: "My bench has been stuck at 85kg for 3 months. I train 3x/week but nothing moves. How do I break through?"

**polarized-endurance** — Runner, cyclist, or triathlete needs intensity distribution (80% Z2 / 20% VO2/threshold) for aerobic performance.
Example: "My cycling FTP is stuck at 210W. I ride 6h/week mostly at tempo. How do I structure zones to push past the plateau?"

### Recovery, Sleep & Measurement

**sleep-foundations** — Sleep quality or quantity is the bottleneck (insomnia, short duration, irregular schedule) affecting everything else.
Example: "I only sleep 5 hours and wake at 4am every day. Training and mood are suffering. How do I fix the sleep itself?"

**recovery-periodization** — Trainee is overreaching, HRV dropping, chronic fatigue from training load; need deload cycles and SRA-curve management.
Example: "My HRV has trended down for 3 weeks, morning HR is up 8bpm, and lifts feel heavy. Do I need a deload, and how long?"

**blood-biomarkers** — User has blood test results to interpret (lipids, glucose, thyroid, ferritin, vitamin D) or wants to decide what to test.
Example: "Got my annual check-up. ApoB 115, HDL 42, TG 180, HbA1c 5.7, ferritin 28. What do these mean together and what should I do?"

**body-composition** — User wants to measure or track body fat %, muscle mass, FFMI, waist circumference via DEXA / InBody / skinfold / photos.
Example: "InBody says 18% body fat but I don't look lean. How reliable is it and what should I use instead to track changes?"

### Occupational & Work-Related

**occupational-health** — Pain, fatigue, or musculoskeletal problem with a work-related cause (repetitive motion, overhead, shift work, heavy lifting).
Example: "Assembly-line worker, 10 years. Shoulder and wrist hurt during workdays but feel fine on weekends. What's the root cause?"

---

## User Prompt Template

```
## Situation
{scenario}

## Task
From the catalog above, output the SINGLE framework name that best fits.

Answer (one word, lowercase):
```

---

## Routing Notes (for maintainers, not shown to LLM)

- **Ambiguous cases deliberately kept**: e.g., "weight loss with insulin resistance" → `low-carb-keto` (not `macro-tracking`). `macro-tracking` is the default general-loss pick; `low-carb-keto` takes over when metabolic dysfunction dominates.
- **`intermittent-fasting` vs `macro-tracking`**: if the user asks about *when* to eat, route IF; if they ask about *how much*, route macro-tracking.
- **`occupational-health` takes priority** when the pain/fatigue pattern correlates with work shifts — the etiology branch must be decided before prescribing any training framework.
- **`sleep-foundations` vs `recovery-periodization`**: sleep is the pick when the sleep *itself* is broken; recovery-periodization is the pick when training volume is the proximate cause.
- **Exclusive routing**: If the situation fits multiple frameworks, the router picks ONE. Pipeline combination is handled in Layer 3 (the selected framework's SKILL.md may invoke others).
- **Not included here**: `fit` itself (this IS fit).

---

## Maintenance Protocol

Adding a new framework requires:
1. Add an entry to Framework Catalog above (name + when + example).
2. Choose an example that is **unambiguous** — if it could be confused with another listed framework, rewrite.
3. Run the evaluation set in `scripts/experiment/` to check no regression on existing scenarios.
