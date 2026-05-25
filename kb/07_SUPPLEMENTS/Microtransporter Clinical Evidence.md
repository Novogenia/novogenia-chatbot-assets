# Microtransporter Clinical Evidence — {{COMPANY_NAME}}
<!--
  REQUIRES_VARIABLE: {{SUPPLEMENT_DAILY}}
  PURPOSE: Customer-facing summary of the in-house pharmacokinetic / pharmacodynamic evidence behind
           the {{PELLET_NAME}} micro-transporter technology — the basis for the "up-to-12-hour delivery
           window" and "70% release in 10 minutes" claims used to describe the supplement.
  SOURCE: Reither D, Gruber A, Huttegger M, Wallerstorfer D — "Intestinal Delivery Profiles of 2-mm
          Nutrient Microbeads ('Microtransporters'): In-Vitro Release Integrated with Physiological
          Gastric Transport", Novogenia GmbH Laboratory, Salzburg, Austria.
-->

---

## Headline finding

### What the study shows in one sentence

Two formats of 2 mm {{PELLET_NAME}} — a fast-release bead and a slow-release bead — produce sharply different intestinal nutrient-delivery timelines when their in-vitro release behaviour is combined with how the human stomach actually empties: fast-release peaks within ~1.5 hours, slow-release stretches across roughly 7 hours, and a 50:50 blend gives continuous nutrient availability across the full window.

### Why a customer should care

Nutrient timing is as important as nutrient dose. A single conventional capsule typically empties as a bolus and delivers everything to one small section of intestine. A {{PELLET_NAME}}-based daily {{SACHET_NAME}} can deliver some nutrients early (where the upper small intestine absorbs them best) and others slowly over many hours (where the body benefits from steady availability — for example Vitamin C, which the body cannot store).

---

## Why physical form matters

### How the stomach handles different physical forms

The stomach meters what passes into the duodenum based on physical form and energy density. Low-energy liquids and water empty quickly (half-time ~10–20 minutes; gastric T₅₀ ≈ 13 ± 1 min). Digestible solids empty more slowly over roughly 2–4 hours after an initial lag while particles are mechanically reduced. Large indigestible particles are retained until interdigestive clearance.

### The 3 mm size threshold

Solids smaller than about 3 mm can pass post-prandially alongside food, while larger particles are held back until the migrating motor complex clears the stomach during fasting. {{PELLET_NAME}} are deliberately produced at 1.6–2 mm — small enough to behave as "small solids" that pass with the meal, but large enough to act as discrete release units rather than dissolving in the stomach.

---

## Study design

### What was measured

Two physical formats of vitamin-C-loaded 2 mm microbeads were characterised — a fast-release bead and a slow-release bead. A third "mixed" format combined the two in equal 50:50 proportion. Release was tracked continuously in isothermal intestinal buffer via pH sensing converted to percent release through a calibration curve.

### The three-stage method

Stage 1 — parameterise gastric-emptying functions for liquids vs small solids from published physiological data (scintigraphy, manometry, MRI studies). Stage 2 — measure in-vitro release of vitamin C from each bead format. Stage 3 — mathematically combine the gastric-transport functions with the in-vitro release curves to produce realistic post-ingestion delivery timelines.

---

## Results

### Fast-release format

Fast-release beads released about 70% of their vitamin-C payload in the first 10 minutes in intestinal buffer and reached near-complete release by 60 minutes. After ingestion, solutes from these beads behave like the liquid fraction of stomach contents — they reach the small intestine within roughly 1.5 hours of taking the sachet.

### Slow-release format

Slow-release beads release gradually with a near-linear mid-phase, reaching full release only after about 3 hours in vitro. Because the intact beads behave as small solids (< 3 mm), they empty from the stomach more slowly and only begin releasing once they reach the duodenum. The resulting intestinal delivery window stretches to approximately 7 hours.

### 50:50 mixed format

A 50:50 mix of fast and slow beads bridges the two extremes — continuous nutrient release throughout the full ~7-hour delivery window, with neither the abrupt peak of pure fast-release nor the lag of pure slow-release. This is the configuration that underpins the daily {{SACHET_NAME}} for most nutrients in {{SUPPLEMENT_DAILY}}.

### What this means for absorption

Different nutrients have different optimal release profiles. Fat-soluble vitamins (A, D, E, K) need fat for absorption — they go in fast-release beads to release while meal-derived fat is still in the small intestine. Vitamin C cannot be stored — it goes in slow-release beads for sustained availability across the day. Competing minerals (zinc vs calcium) go in beads timed to release in different zones to prevent absorption interference.

---

## How to discuss this with a customer

### What the bot can confidently say

"The micro-transporter beads come in two release formats, characterised in our in-house in-vitro study. Fast-release beads deliver ~70% of their payload in the first 10 minutes after they reach the small intestine; slow-release beads spread the same dose across about 7 hours. By combining both formats in the right ratio per nutrient, your daily sachet maintains steady nutrient availability across roughly a 12-hour window — much more like absorbing nutrients from food than like a single capsule peak."

### What the study does NOT claim

It does not measure absorption or blood levels — it measures release into intestinal buffer combined with modelled gastric transit. It does not claim {{COMPANY_NAME}}'s pellets are unique in physical principle — controlled-release multiparticulates are a well-established pharmaceutical technique. The novelty is the per-nutrient application to a personalised daily {{SACHET_NAME}}.

### Limitations to acknowledge

In-vitro plus modelled gastric transit, not in-vivo blood-level measurement. Internal study, not yet peer-reviewed. Real human transit times vary with meal composition, body posture, time of day, and individual physiology — the 7-hour and 12-hour windows are best understood as central estimates rather than precise values for every individual.

---

## How this links to the products

### The 12-hour delivery window claim

The "up-to-12-hour delivery" wording in the customer FAQ comes from combining the slow-release window (~7 hours of intestinal release) with the small-intestine residence time in real customers. The 7-hour figure comes directly from this study; the broader 12-hour figure reflects the customer-observed steady release in stool/blood signal observations.

### The "do not chew" instruction

The bot's standard "do not chew the pellets" guidance flows directly from this study. Mechanical disruption defeats the slow-release matrix — chewed beads behave like fast-release ones regardless of which format they were designed as. Accidental chewing is harmless but reduces the slow-release benefit.

### Connection to {{SUPPLEMENT_DAILY}} personalisation

The release-format design is decided per-nutrient in the formulation algorithm — Vitamin C goes slow-release, fat-soluble vitamins go fast-release with a meal-fat trigger, zinc/calcium go in separately timed beads to prevent absorption interference. The same algorithm that picks doses also picks release format, then the production line builds the sachet from the right mix of bead types.

---

## Citation

### How to cite

Reither D, Gruber A, Huttegger M, Wallerstorfer D. *Intestinal Delivery Profiles of 2-mm Nutrient Microbeads ("Microtransporters"): In-Vitro Release Integrated with Physiological Gastric Transport.* Novogenia GmbH Laboratory, Salzburg, Austria. Available to clinicians and resellers on request via the {{COMPANY_NAME}} laboratory.

---

## Downloadable Resources

- [Advantages of Microtransporters (PDF, DE)](https://raw.githubusercontent.com/Novogenia/novogenia-chatbot-assets/main/supplements/B1_Microtransporter_advantages_DE.pdf)
