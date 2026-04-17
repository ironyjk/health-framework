# Health & Training Framework

[한국어](README.ko.md) | **English**

---

A meta-router + framework collection for health and training decision-making.

Bundles 13 frameworks — nutrition (Mediterranean, low-carb, intermittent fasting, macro tracking), training (progressive overload, strength, hypertrophy, polarized endurance), sleep & recovery, measurement & diagnostics (blood biomarkers, body composition), and occupational health — under a single routing layer.

## Design Principles

1. **Evidence-based only** — Backed by RCTs, meta-analyses, and Cochrane reviews. Pseudoscience, influencer marketing, and supplement industry claims are excluded.
2. **Evidence strength is explicit** — "Strong evidence" (e.g., PREDIMED, progressive overload) / "Moderate" (e.g., 16:8 TRE) / "Weak or contested" (e.g., most supplements) are labeled distinctly.
3. **Goal and personal context first** — The right framework differs by purpose: weight loss vs. muscle gain vs. endurance vs. healthspan.
4. **Anti-pattern warnings included** — Explicit notes on when each framework backfires or becomes unsustainable.

## Structure

```
health-framework/
├── SKILL.md                   # Meta-router — situation → framework selection
├── mediterranean-diet/        # PREDIMED-based; strongest long-term evidence
├── low-carb-keto/             # Ketogenic · metabolic adaptation · target populations
├── intermittent-fasting/      # 16:8 · 5:2 · TRE
├── macro-tracking/            # Calories + protein · carb/fat allocation by goal
├── progressive-overload/      # Foundational principle for all training
├── strength-basics/           # 5x5 · 5/3/1 · Starting Strength
├── hypertrophy-volume/        # MV/MEV/MAV/MRV · PPL · RP
├── polarized-endurance/       # Seiler 80/20 · Z2 + VO2max
├── sleep-foundations/         # 7–9 h · consistency · light exposure
├── recovery-periodization/    # SRA · HRV · deload
├── blood-biomarkers/          # ApoB · HbA1c · hs-CRP · Vitamin D
├── body-composition/          # DEXA · BIA · FFMI · waist circumference
└── occupational-health/       # Repetitive strain · shift work · industrial injury · work-related MSDs (v0.2.0)
```

## Usage

```
/fit <situation description>
```

The meta-router classifies purpose, symptoms, and level, then selects 1–3 frameworks and executes/synthesizes via the Skill tool.

> 💡 **Short name**: after [wrapper setup](https://github.com/ironyjk/claude-frameworks-marketplace#short-command-setup-optional), callable as `/fit`

## Out of Scope

- Disease treatment or prescription (→ physician)
- Mental health / psychological counseling (→ `counsel`)
- Sport-specific technique coaching (→ domain specialist)
- Pregnant women, children, or elderly with special conditions (→ specialist physician)

## Meta

- `last_verified: 2026-04-17`
- `valid_until: 2026-10-17` — Nutrition guidelines, biomarker reference ranges, and supplement evidence require re-verification within 6 months.

## Disclaimer

**This repo is a decision-support tool, not medical or nutritional advice.**

- If you have underlying conditions (diabetes, cardiovascular disease, kidney disease, thyroid, autoimmune, etc.) or take medication, consult a physician or dietitian before making changes.
- Figures presented (protein g/kg, target heart rate, biomarker reference ranges, etc.) are based on general adult populations; individual variation is substantial.
- You bear full responsibility for outcomes from changes to supplements, diet, or training protocols.
- Acute symptoms (chest pain, fainting, severe fatigue, sudden weight change, etc.) require clinical care — not a framework.
