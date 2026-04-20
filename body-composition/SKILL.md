---
name: body-composition
version: "0.2.0"
description: "Body composition measurement — DEXA (reference) vs BIA (InBody) vs skinfold vs photos·mirror. Body fat %, muscle mass, waist circumference, FFMI. Error structure and correct interpretation of each method. Limits of the scale number."
---

# Body Composition

> **Background and theory**: Read [references/foundation.md](references/foundation.md)


## One-Line Summary

**Weight is a summary statistic of body composition.** The same 70 kg looks and functions entirely differently depending on the mix of body fat, muscle, and water. Measurement = **combine multiple methods + consistent conditions + track the trend**.


## Comparison of Main Measurement Methods

### DEXA (Dual-energy X-ray Absorptiometry)
- Reference-grade. Three-compartment: fat, lean mass, bone density
- Error ±1~3% body fat
- Cost (Korea: 30,000~80,000 KRW), radiation low but present
- Hydration, meals, exercise sway the same-day result (slightly)
- **Recommended**: once every 6~12 months, same conditions (morning, fasted, post-void)

### BIA (Bioelectrical Impedance) — InBody, etc.
- Estimates from electrical resistance of the body (differential conductivity of water·fat·muscle)
- Body fat % error ±3~8% (depends on model and conditions)
- Sensitive to hydration, meals, exercise, menstrual cycle
- **Trend under identical conditions is useful**; absolute value needs calibration
- Multi-frequency models beat single-frequency but don't replace DEXA

### Skinfold Calipers
- Error ±3~4% in skilled hands
- Low-cost, portable
- Highly operator-dependent; difficult to measure in the high-body-fat population

### Waist Circumference·WHtR
- **Waist-to-height ratio (WHtR)**: target <0.5 (simple, powerful)
- Navel-based vs midpoint between lowest rib and iliac crest — protocol consistency
- Strong predictor of cardiovascular and diabetes risk

### Waist-to-Hip Ratio (WHR)
- Men <0.9, women <0.85 (WHO)

### Photos·Mirror·Fit
- **Consistent conditions** (morning, same spot, same lighting, same pose) once per month
- Clothing fit (belt holes, a specific pair of pants) = honest long-term tracking
- Practical indicators that should not be ignored

### Scale
- **3~7 mornings/week fasted**, use the weekly average
- Daily fluctuation of ±1~2 kg is common (water·glycogen·gut)
- Smart scales (BIA-equipped) share the limits of BIA

### BodPod (air displacement plethysmography)
- Accuracy approaches DEXA, low accessibility (in Korea)

### 3D Scan
- Useful for tracking circumference·volume changes; body fat % calculation is dubious


## Practical Application

### Tracking Protocol
```
Weekly: weight (morning, fasted) weekly average, waist circumference (navel, once/week)
Monthly: photos (front/side/rear, same conditions), BIA or skinfold
Semi-annually: DEXA (if resources allow)
```

### During Fat Loss
- Target body weight -0.5~1%/week
- Waist circumference -1~2 cm over 4 weeks
- DEXA: LBM preserved + FM decreased = success
- A BIA "muscle gain" during fat loss is mostly water·glycogen shifts

### Special Tracking for GLP-1 Agonist Users
- **Watch the proportion of LBM loss** — higher LBM-loss ratio than typical fat loss (Wilding STEP 1 post-hoc, Blundell studies). Target >70% muscle preservation during loss
- **DEXA or the same BIA every 4~8 weeks**, protein 1.2~1.6 g/kg LBM + resistance training 2~3×/week
- Rapid waist shrinkage is a win, but check grip strength and stair-climb RPE — reassess protein·training if function drops
- Rebound is common upon discontinuation — body composition rebounds more slowly than weight (muscle reacquisition is hard)

### Korean InBody Realities
- Common in gyms, offices, oriental medicine clinics, etc. Model variance (professional 770·470 vs home models)
- **Don't compare across machines.** Same machine, same time of day (morning, fasted, post-void), same attire, same hydration
- Recommendation: at most once/month on the same machine. Don't agonize over a "0.3 kg muscle change" — within measurement error
- **InBody segmental muscle asymmetry of ±5%** is normal variability. Strong asymmetry can reflect real development, measurement error, or both

### During Bulking
- Body weight +0.25~0.5%/week
- Waist <1 cm/month (minimize fat accumulation)
- Long-term FFMI tracking to confirm muscle gains

### Recomposition (Beginners·Returnees)
- Possible window of simultaneous FM↓·LBM↑
- Weight change is small → **photos, waist, FFMI, mirror** are better indicators


## Antipatterns

- **Judging success/failure from the scale alone**
- **Overtrusting the absolute value of InBody numbers** — machine·conditions·hydration sensitive
- **Redesigning your diet from an abnormal reading right after measurement** — a single outlier is possible
- **Ignoring waist circumference** — one of the cheapest and strongest indicators
- **Ignoring the menstrual cycle in women** — weekly water fluctuation of ±1~2 kg is common
- **DEXA every week** — radiation·cost, and not enough time for distinguishable change
- **Obsession with a "single-digit" body fat % goal** — risks of amenorrhea, hormonal suppression, mental health
- **Overlooking normal weight obesity** — weight/BMI normal but high body fat and low muscle
- **The myth of spot reduction** — fat distribution is genetic


## Limitations

1. **Inconsistency between methods** — a 5% body fat % gap between DEXA and BIA is common
2. **Day-to-day variability** — hydration, meals, exercise, gut contents especially sway BIA
3. **Without protocol consistency, trends cannot be interpreted**
4. **Uneven muscle distribution** is hard to measure
5. **Accuracy drops in severe obesity**
6. **Body composition isn't everything** — must be viewed alongside function (strength, VO2) and biomarkers
7. **Subjectivity in defining "ideal body fat %"** — psychological, health, and performance goals differ


## Companions·When This Framework Is *Wrong*

- Set calories·protein → `macro-tracking`
- Increase LBM through training → `hypertrophy-volume` · `strength-basics`
- Comprehensive cardiovascular·metabolic risk → `blood-biomarkers`
- Adjust fat-loss rate → `macro-tracking` + regular photos
- Excess fat accumulation during bulk → reset deficit with `macro-tracking`
- Signs of disordered-eating tendencies → consult a specialist (discontinue this framework)
