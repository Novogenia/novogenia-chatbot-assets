# Report Example — {{WEIGHT_SENSOR}}
<!--
  REQUIRES_VARIABLE: {{WEIGHT_SENSOR}}
  PURPOSE: Anonymized representative example of the {{WEIGHT_SENSOR}} customer report. Shows section structure, the six genetic axes the report covers, and how recommendations are framed — so the bot can describe what a customer receives without referring to any real person's data.
-->

---

## Overview

### What the customer receives

The {{WEIGHT_SENSOR}} report is a roughly 120-page personalised document covering six genetic dimensions of weight management. It opens with the standard foreword, "what genes are", and disclaimer separating science from recommendation, then presents a results overview followed by a dedicated chapter for each of the six axes, plus closing pages on the laboratory and the technical methodology.

### Tone and framing

Recommendations are written in the second person and always tied back to the customer's genotype. The report consistently separates the genetic trait (study-backed) from the recommendation (a logical conclusion drawn from that trait).

## Report sections

### Front matter

Foreword, "What are genes", "When genes do not work correctly", and the disclaimer. Also covered: who the report is for, how to read it, and how the six axes combine into a weight strategy.

### Results overview

A "Your results at a glance" summary lists every axis with the headline finding for that customer in one line, plus the page where the full chapter begins.

### The six analysis axes

The report has one chapter per axis, in this order: nutritional type (fat vs. carb vs. mixed metaboliser), exercise vs. calorie reduction (which is more effective for this person), preservation of muscle mass during weight loss, control of hunger and satiety, fat distribution (where the body deposits fat), and "hit your desired weight" (how to translate the findings into a target-weight plan).

### Closing pages

About-the-laboratory page and technical details (methodology, accreditations, sample handling).

## The six axes — what each chapter covers

### Nutritional type

Identifies whether the customer's body responds best to a fat-restricted, carb-restricted, or balanced diet. Combines results from genes governing fat metabolism, carbohydrate handling, and insulin sensitivity into one of seven nutrition types ranging from full fat-burner to full carb-burner, with five mixed types in between.

### Exercise or calorie reduction

Estimates the relative payoff of physical activity versus dietary restriction for this individual. Some genotypes respond strongly to exercise (PPARG-functional, ADRB2-responsive); others lose weight almost exclusively through calorie reduction.

### Preservation of muscle mass

Covers genetic propensity to lose muscle during a calorie deficit. Customers with at-risk variants are guided toward resistance training and adequate protein during weight-loss phases to preserve lean mass.

### Control of hunger and satiety

Looks at leptin, ghrelin, and related signalling variants. Identifies whether the customer is genetically prone to constant hunger, weak satiety signalling, or strong appetite control — and what that implies for meal frequency, snack timing, and protein-fat ratio at meals.

### Fat distribution

Analyses where the body preferentially deposits fat — predominantly visceral (around organs, metabolically risky) versus subcutaneous (hips, thighs, metabolically safer). The chapter explains why the same BMI carries different health risk depending on this genotype.

### Hit your desired weight

The integrating chapter. It combines all five preceding axes into a starting weight, calculated optimal weight (based on optimal BMI for the customer's height), and a target weight the customer chooses. Outputs a recommendation on calorie level, exercise emphasis, and which {{COMPANY_NAME}} products best support the plan.

## Chapter structure

### How every chapter is built

Each chapter follows the same template: a short scientific introduction, a "most important details at a glance" box, an explanation of what the genes do when functional vs. defective, the customer's personal result with genotype and a colour-coded verdict (green / yellow / red), a recommendation paragraph, and a small panel of personalised tags (e.g. "Exercise: high impact" or "Snacking risk: elevated"). Each chapter closes with PubMed source IDs.

### Verdict categories

Results are framed in one of three ways: "favourable / typical" (no special intervention needed), "moderate variant" (some adjustment recommended), or "high-impact variant" (significant strategy change advised).

## Example findings

### Example 1 — favourable result, no action

Axis: Muscle preservation. Verdict: "Muscle loss risk: low." Narrative: the customer's relevant variants are protective, so a moderate calorie deficit with standard activity preserves lean mass without specific resistance-training emphasis.

### Example 2 — moderate variant, dietary nudge

Axis: Nutritional type. Verdict: "Mixed type with carb sensitivity." Narrative: the customer metabolises both fats and carbohydrates reasonably well but should keep refined carbohydrates lower than average. Recommendation: prefer wholegrain over white, keep added sugar low, balance plates around protein and vegetables.

### Example 3 — high-impact variant, strategy change

Axis: Exercise or calorie reduction. Verdict: "Exercise efficiency low (PPARG defective)." Narrative: in studies, customers with this variant lost roughly 3× less weight from the same exercise intervention compared with functional carriers. Recommendation: focus the weight-loss strategy on calorie reduction rather than exercise volume, while keeping movement for cardiovascular and muscle reasons.

### Example 4 — at-risk variant, lifestyle change

Axis: Fat distribution. Verdict: "Visceral fat tendency: elevated." Narrative: the customer's variants favour fat storage around organs rather than hips. This makes even modest weight gain metabolically riskier than average. Recommendation: prioritise abdominal-fat-reducing strategies (resistance training, limiting added sugar, sleep hygiene) rather than overall scale weight.

### Example 5 — high-impact variant, behavioural support

Axis: Hunger and satiety. Verdict: "Snacking tendency: high." Narrative: leptin and ghrelin signalling variants make the customer's hunger signal stronger and satiety signal weaker than typical. Recommendation: front-load protein at meals, plan structured snacks rather than fighting hunger, and consider {{SUPPLEMENT_WEIGHT}} during reduction phases.

## How recommendations are framed

### Always tied to a genotype

Every recommendation is preceded by the gene name (or gene cluster), the customer's genotype, and the verdict it produced. The recommendation is presented as a logical consequence of that genotype, not as a study finding in itself.

### Population context

Where useful, the chapter shows what percentage of the general population carries the same variant. This helps the customer locate themselves on a normal distribution rather than feeling singled out.

### Integration with other products

Findings feed into {{SUPPLEMENT_DAILY}} dosing (where ordered), can inform whether {{SUPPLEMENT_WEIGHT}} is appropriate, and connect to {{NUTRITION_SENSOR}} where the customer also has nutrient-handling variants. The bot can cross-reference between reports when both are ordered.

## Connection to other reports and products

### How the weight report hands off

Customers who also own {{NUTRITION_SENSOR}} get a combined Precision Nutrition Plan that blends both reports' findings into one daily strategy. Customers who add {{SUPPLEMENT_DAILY}} get a daily-sachet formulation that already accounts for weight-relevant variants (e.g. higher methylfolate if MTHFR is impaired, adjusted Vitamin D dose if VDR is defective). {{SUPPLEMENT_WEIGHT}} is offered as a context-appropriate add-on for active weight-loss phases.
