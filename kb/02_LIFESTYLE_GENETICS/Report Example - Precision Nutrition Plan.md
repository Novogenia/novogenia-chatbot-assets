# Report Example — Precision Nutrition Plan
<!--
  REQUIRES_VARIABLE: {{NUTRITION_SENSOR}}, {{SUPPLEMENT_DAILY}}
  PURPOSE: Anonymized representative example of the Precision Nutrition Plan that accompanies a {{NUTRITION_SENSOR}} report. Shows what the customer-facing daily-requirements and food/exercise plan look like, including the supplement-recipe view, so the bot can describe the deliverable accurately without quoting real personal values.
-->

---

## Overview

### What this document is

The Precision Nutrition Plan is the action-oriented companion to the {{NUTRITION_SENSOR}} report. While the main report explains the genetics chapter by chapter, the Plan converts those findings into a daily micronutrient prescription, a personalised food rating, and a weight-management and exercise section. It is the document the customer uses day to day.

### How it is generated

The Plan is auto-generated from the aggregated nutrient arrows of every chapter in the main report. There is no separate questionnaire — the genotype results are the only input. New blood results, age changes, or new science can re-trigger an updated Plan.

## Plan sections

### Front matter

A short foreword, the standard disclaimer separating science from recommendation, and a table of contents covering the nutrient and lifestyle requirements, the {{SUPPLEMENT_DAILY}} recipe view, the {{SUPPLEMENT_WEIGHT}} recipe view (if applicable), {{COMPANY_NAME}}'s precision IV partner section, the food and exercise plan, and the food item list A–Z.

### Your nutrient and lifestyle requirements

A multi-page master view that maps every nutrient or lifestyle factor (caffeine, Omega-3, methylfolate, magnesium, vitamin D3, alcohol, smoke, heavy metals, sucrose, etc.) to the chapters that contributed to its rating, with the same green-arrow / red-arrow / neutral system used in the main report.

### Supplement recipe view

The exact daily dose for each micronutrient and other nutrient included in {{SUPPLEMENT_DAILY}}, grouped into Minerals, Vitamins, and Other Nutrients, each labelled with a need level (low, normal, high).

### Superfood extracts panel

A list of personalised botanical and superfood extracts included in the daily pack — typically several dozen plant extracts (berries, herbs, mushrooms, roots) tailored to the customer's genetic profile.

### Weight management recipe view

If the genetic nutrition-type analysis is included, a separate section covers the personalised {{SUPPLEMENT_WEIGHT}} sachet — based on plant-derived Opuntia ficus-indica cactus fibre plus Phaseolamin from white kidney bean, dosed against the customer's genetic sensitivity to fats vs. carbohydrates.

### Precision IV section

A partner-network section covering how the same genetic profile can drive a precision IV formulation at a partner clinic, scanned via a unique QR code.

### Food and exercise

A "you and your results in everyday life" section presenting a starting weight, calculated optimal weight, and target weight, followed by four nutrition-style options and a curated exercise selection, each tagged for whether it suits "reduce weight" or "maintain weight" phases.

### Food item list A–Z

A long appendix evaluating roughly 900–1,400 foods against the customer's profile, used as the everyday shopping reference.

## How requirements are expressed

### Need levels

Each nutrient in the supplement recipe view is tagged as low need, normal need, or high need. The accompanying short text explains what that level means in practice — for example "we recommend slightly increasing the intake of this nutrient", "the intake of this nutrient should be significantly increased", or "you either have no need for it, it does not work for you, or you have an excess — it is not recommended to take it".

### Units

Doses are given in milligrams or micrograms per day. The Plan emphasises that the dose accounts for typical dietary intake, so the supplement plus a normal diet should not exceed the upper safe limit.

## Example daily requirement view

### Example structure — Minerals block

Magnesium, manganese, selenium, zinc, copper, iron, calcium — each shown with a need level (low/normal/high) and a gene-derived dose in mg or µg. Specific values differ per customer.

### Example structure — Vitamins block

Vitamin C, vitamin E, vitamin B12, vitamin B6, methylfolate, vitamin B2, vitamin D3 — each with its need level and dose. The methylfolate entry in particular is a direct consequence of an MTHFR finding in the main report.

### Example structure — Other nutrients block

Coenzyme Q10, phytosterols, Omega-3 fatty acids, alpha-lipoic acid, MSM, TMG — with need levels driven by the corresponding chapters. For example, a "low need" verdict on Omega-3 typically traces back to a defective APOA1 finding.

### Note on personalisation

Categories and the way they are framed are stable across customers. The numbers — doses, need levels, included nutrients — differ in every report.

## Recipe-level personalisation

### Micronutrient layer

Each {{SUPPLEMENT_DAILY}} pack is formulated to the doses on the requirements page. The same recipe is rebuilt whenever new biological data (new genes, new blood values, age changes) is available, so subsequent orders may differ.

### Superfood extract layer

Beyond the micronutrients, the pack carries dozens of personalised botanical extracts (for example acai, acerola, ashwagandha, broccoli, milk thistle, pomegranate, lion's mane, turmeric-family roots). The selection is filtered against the customer's genetic profile so that only relevant extracts are included.

### Delivery format

The micronutrients are delivered as {{PELLET_NAME}} micro-transporter beads designed to mimic natural absorption from food and maintain steady blood levels through the day.

## Weight management recipe view

### Composition logic

If the nutrition-type analysis is part of the order, a second sachet is formulated for weight management. {{SUPPLEMENT_WEIGHT}} combines Opuntia ficus-indica cactus fibre (fat binding) and Phaseolamin from white kidney bean (carbohydrate-digestion blocker) in a ratio dictated by the customer's genetic sensitivity to fats versus carbohydrates.

### Usage in the plan

The Plan instructs taking one sachet with a large glass of water just before lunch and dinner, swallowing the tasteless microtransporters whole, with a hard cap of two sachets per day.

## Food and exercise section

### Anchors

The section opens with three numbers: current weight at time of analysis, calculated optimal weight (based on optimal BMI for the customer's height), and the customer's chosen target weight. All examples in this KB use placeholder values only.

### Four nutrition styles

The Plan offers four diet templates to choose from, each tagged for whether it fits a weight-reduction phase, a weight-maintenance phase, or both. The customer picks the style that suits their lifestyle and the Plan formats the food list accordingly.

### Exercise selection

A curated set of exercises with calorie burn estimates is included, again tagged for "reduce weight" vs "maintain weight" suitability.

## Connection back to the report

### Traceability

Every nutrient need on the Plan can be traced back to the chapter or chapters in the main report that contributed to it — the requirements pages list the chapter name beside each nutrient. This means the bot can always explain why a particular need level appears, by pointing the customer back to the relevant chapter of their {{NUTRITION_SENSOR}} report.
