# Report Example — {{NUTRITION_SENSOR}}
<!--
  REQUIRES_VARIABLE: {{NUTRITION_SENSOR}}
  PURPOSE: Anonymized representative example of the {{NUTRITION_SENSOR}} customer report. Shows section structure, finding types, recommendation style, and reference framing so the bot can describe what a customer actually receives without quoting real personal data.
-->

---

## Overview

### What the customer receives

The {{NUTRITION_SENSOR}} report is a roughly 260-page personalised document. It opens with a foreword from the Chief Scientific Officer, explains what genes are, sets out a disclaimer about the boundary between science and recommendation, then presents an at-a-glance results overview followed by a chapter for each gene-driven topic. A companion Precision Nutrition Plan covers the customer's daily nutrient requirements and feeds into {{SUPPLEMENT_DAILY}}.

### Tone and framing

Recommendations are written in the second person and are always tied back to the genotype that produced them. The report consistently distinguishes between genetic traits (study-backed) and the derived recommendation (a logical conclusion drawn from the trait).

## Report sections

### Front matter

Foreword, "What are genes", "When genes do not work correctly", and a Disclaimer that separates scientific findings from the recommendations layered on top.

### Results overview

A two-page summary headed "Your results at a glance" listing every chapter and the headline finding for that customer with a one-line plain-language verdict and the page where the full chapter starts.

### Gene reference table

A "Gene overview" page lists every gene tested with its rs-ID(s) and a one-sentence biological role — for example AGT (blood pressure regulation), MTHFR (folate activation), CYP1A2 (caffeine breakdown), VDR (vitamin D response), LCT (lactose digestion).

### Topic chapters

Roughly twenty topic chapters cover: coffee and caffeine, Omega-3 and HDL, folic acid, homocysteine protection, Coenzyme Q10, detoxification of carcinogens, detoxification of chemicals, oxidative stress, selenium, salt and blood pressure, Vitamin D3, lactose and calcium, inflammation, LDL cholesterol, triglycerides, and iron absorption.

### Methylation block

A separate methylation block walks through five sequential steps: breakdown of SAH, activation of folic acid, building the homocysteine breakdown machinery, recharging it, and methionine as fuel for COMT.

### Closing pages

About-the-laboratory page and technical details (methodology, accreditations).

## Chapter structure

### How every chapter is built

Each topic chapter follows the same template: a short scientific introduction, a "most important details at a glance" box, an explanation of what the gene does when effective vs. defective with a simple two-step diagram, the customer's personal result with genotype and a colour-coded verdict, a recommendation paragraph, and a "Need" panel showing nutrient arrows (green = more is better for you, red = less is better, none = neutral). Each chapter closes with PubMed source IDs.

### Verdict categories

Results are framed in one of three ways: "functional / effective" (no action needed), "impaired / partially defective" (moderate adjustment recommended), or "defective" (clear behavioural or supplementation change needed).

## Example findings

### Example 1 — functional gene, no action

Topic: Coenzyme Q10 activation. Gene: NQO1. Verdict: "The conversion of Coenzyme Q10 works." Narrative: the customer's NQO1 gene converts Q10 to its active form ubiquinol normally, so no special supplementation strategy is required. This is the simplest finding type — it confirms a strength rather than triggering a change.

### Example 2 — minor variant, dietary nudge

Topic: Selenium supply. Gene: GPX1. Verdict: "Selenium requirement is normal." Narrative: because the GPX1 gene is functional, the customer needs only the standard daily selenium intake. The recommendation is to maintain normal dietary sources (brazil nuts, fish, eggs) without supplementing aggressively.

### Example 3 — impaired gene, supplement switch

Topic: Folic acid metabolism. Gene: MTHFR (rs1801133, rs1801131). Verdict: "Folic acid conversion impaired." Narrative: because the MTHFR genes are partially impaired, synthetic folic acid is only converted slowly into its active form, methylfolate. The recommendation is to take methylfolate directly rather than folic acid, and to prefer gently steamed leafy vegetables, legumes, eggs, and liver because methylfolate degrades above 60°C.

### Example 4 — defective gene, reduce intake

Topic: Coffee and caffeine. Gene: CYP1A2 (rs762551). Verdict: "Breakdown of caffeine is limited." Narrative: because the CYP1A2 gene is impaired, caffeine is neutralised only slowly. Recommendation: reduce caffeinated coffee and switch to decaffeinated, which still delivers the protective antioxidants and polyphenols without the cardiovascular load.

### Example 5 — defective gene, reverse the usual advice

Topic: Omega-3 and HDL cholesterol. Gene: APOA1 (rs670). Verdict: "Omega-3 worsens HDL cholesterol." Narrative: because the APOA1 gene is defective, additional Omega-3 fails to lift HDL and can actually lower it. The recommendation is to still prefer fish and plant oils over saturated animal fats, but not to take Omega-3 capsules — and to use phytosterols instead as the HDL-supporting alternative.

### Example 6 — defective gene, lifestyle change

Topic: Salt and blood pressure. Gene: AGT. Verdict: "Salt contributes to high blood pressure." Narrative: because the customer carries the salt-sensitive variant, table salt raises blood pressure more steeply than average. Recommendation: reduce added salt, favour potassium-rich foods, and treat processed food as the main intervention target.

## How recommendations are framed

### Always tied to a genotype

Every recommendation is preceded by the gene name, rs-ID, and the customer's genotype. The verdict is then derived from that genotype, and the recommendation is presented as a logical consequence, never as a study finding in itself.

### Population context

Many chapters add a "your genes in comparison" page showing what percentage of the general population carries the same variant and at what activity level (for example 100%, 83%, 66%, 48% functional). This helps the customer locate themselves on a normal distribution rather than feeling singled out.

### Nutrient need arrows

Each chapter closes with a small panel of green and red arrows for the nutrients tied to that topic. Multiple green arrows mean "more is better for you", multiple red arrows mean "less is better for you", and no arrows mean the nutrient is neutral. The arrows in every chapter feed into the consolidated nutrient requirement table in the Precision Nutrition Plan.

## Connection to the nutrition plan

### How the report hands off

The report's final chapters do not end with shopping advice. Instead, each chapter's arrow panel and verdict are aggregated into the companion Precision Nutrition Plan, which translates the genetic findings into concrete daily micronutrient doses and a food-by-food rating. If the customer orders {{SUPPLEMENT_DAILY}}, the recipe is built from those aggregated requirements automatically.
