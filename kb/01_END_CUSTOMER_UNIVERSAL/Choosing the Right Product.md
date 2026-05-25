# Choosing the Right Product — Goal-to-Product Guide
<!--
  REQUIRES_VARIABLE: (none — always loaded)
  PURPOSE: The bot's primary decision-support file. When a customer asks "what should I order?" or
           describes a goal/symptom, the bot uses this guide to recommend the right combination of
           sensor + supplement + blood panel. Recommendations always check {{COMPANY_NAME}} Product
           Availability matrix before being offered — items marked NOT OFFERED for this reseller
           are silently skipped.
-->

---

## How to use this guide

### When a customer is unsure what to order

Open with one or two clarifying questions: what is the customer's primary goal, and how invested do they want to be (one-time test vs subscription, lifestyle-only vs adding blood layer). The customer's answer points to one of the goal scenarios below.

### Why combinations, not single products

Most goals are best served by combining a DNA sensor (the lifetime baseline), a blood panel (the current snapshot), and {{SUPPLEMENT_DAILY}} (the daily action driven by both). The DNA tells you *why*, the blood tells you *what right now*, and the supplement closes the loop.

### Reseller availability

Every recommendation below is silently filtered against the reseller's Product Availability matrix. If a recommended product is not offered, the bot suggests the closest available alternative and notes that the original is "not available with this reseller".

---

## By customer goal

### "I want to lose weight"

The core product is {{WEIGHT_SENSOR}} — six genetic axes (nutritional type, exercise vs. calorie response, muscle preservation, hunger/satiety, fat distribution, target weight). For sustained results pair with {{PACKAGE_SHAPE_PLUS}} (DNA test + {{SUPPLEMENT_WEIGHT}} subscription) or {{PACKAGE_LIFESTYLE_PLUS}} (which adds {{NUTRITION_SENSOR}}, {{TOXO_SENSOR}}, {{BURNOUT_SENSOR}}, {{BIOLOGICAL_AGE_SENSOR}}, and {{SUPPLEMENT_DAILY}}). The {{PACKAGE_LIFESTYLE_PLUS}} subscription is the primary pitch product for most weight customers because it addresses the broader metabolic context, not just weight.

### "I'm tired all the time / brain fog"

The right combination is {{BLOOD_PANEL_NUTRIENTS}} (active B12 + Vitamin D + magnesium — the three most commonly deficient nutrients linked to fatigue) plus {{NUTRITION_SENSOR}} to identify why the body may not be making good use of those nutrients (MTHFR for folate activation, VDR for Vitamin D, CYP1A2 for caffeine handling, NQO1 for CoQ10). Close the loop with {{SUPPLEMENT_DAILY}} dosed to the genetic + blood readout.

### "I want to age well / longevity"

The longevity bundle is {{BIOLOGICAL_AGE_SENSOR}} (the genetic baseline), {{BLOOD_PANEL_LONGEVITY_BASE}} (the current measurement — LDL + Trig + HDL + CRP + Mg + B12 + D + TSH + Free T3), and {{SUPPLEMENT_DAILY}} to act on both. Customers interested in hormone-longevity add {{BLOOD_PANEL_LONGEVITY_HORMONES_FEMALE}} or {{BLOOD_PANEL_LONGEVITY_HORMONES_MALE}}. Customers wanting maximum prevention depth can add {{NUTRITION_SENSOR}} and {{TOXO_SENSOR}}.

### "I want to optimise my nutrition"

The entry product is {{NUTRITION_SENSOR}}, which produces the ~260-page report plus the Precision Nutrition Plan with the personalised food list and daily nutrient targets. For customers ready to act on those targets, add {{SUPPLEMENT_DAILY}} — the supplement is built directly from the same algorithm that drives the Plan, so the daily sachet executes the nutrition recommendations automatically.

### "I'm always stressed / burned out"

Start with {{BURNOUT_SENSOR}} (genetic stress vulnerability — COMT for catecholamine clearance, 5-HTT for serotonin, FKBP5 for HPA-axis, CLOCK/PER for sleep). Pair with {{NUTRITION_SENSOR}} for the magnesium and B-vitamin overlap and {{SUPPLEMENT_DAILY}} for personalised dosing of the stress-relevant nutrients. {{BLOOD_PANEL_NUTRIENTS}} or {{BLOOD_PANEL_INFLAMMATION}} adds the current snapshot of how the body is coping right now.

### "I want better skin"

The genetic side is {{BEAUTY_SENSOR}} (20+ skin-relevant genes covering collagen turnover, UV defence, hydration, oxidative stress, inflammation, skin age). Pair with {{COSMETICS_DAY_NIGHT_95ML}} and/or {{COSMETICS_BODY_LOTION_235ML}} — both are personalised from the same genetic results. For long-term subscriptions {{PACKAGE_BEAUTY_PLUS}} bundles the DNA test free with the serum subscription. Add {{SUPPLEMENT_DAILY}} for the systemic nutrients that support skin (vitamin C, D, omega-3, antioxidants).

### "I'm an athlete / I want better performance"

{{PERFORMANCE_SENSOR}} gives the full performance profile (fibre type, VO₂max, recovery, injury risk) and is the core product. {{JUST_PERFORMANCE}} is the standalone version for customers who already own the lifestyle products. {{PACKAGE_PERFORMANCE_PLUS}} bundles the DNA test free with {{SUPPLEMENT_DAILY}}. {{BLOOD_PANEL_INFLAMMATION}} (CRP + Magnesium + Vitamin D) is the best current-state companion for training-load monitoring.

### "I'm worried about my heart / cholesterol / blood pressure"

The current-state read is {{BLOOD_PANEL_HEART_METABOLIC}} (LDL + Triglycerides + Ultra HDL + CRP + Magnesium). The genetic context comes from {{NUTRITION_SENSOR}} (APOA1 for Omega-3/HDL response, AGT for salt sensitivity, MTHFR for homocysteine, NQO1 for CoQ10). For deeper medical-grade prevention, {{EXPERT_PREVENTION}} consolidates cardiovascular risk variants into the clinician report (doctors-only). {{SUPPLEMENT_DAILY}} closes the loop on the nutrient side.

### "I want to know how medications affect me"

{{PHARMACO_SENSOR}} is the standalone pharmacogenetic test (CYP family, DPYD, HLA-B*5701, NAT2, TPMT, SLCO1B1, VKORC1, UGT1A1) covering 2,000+ active substances. This is a doctors-supported product but available to customers — the report is designed to be shared with the prescribing physician. Particularly relevant for customers on long-term medication, preparing for surgery, or with a history of adverse drug reactions.

### "I have allergies"

{{ALLERGY_SENSOR}} (ALEX2 IgE panel covering ~300 allergens) is the right product for immediate-type allergies (rhinitis, asthma, food allergy with rapid reaction). For delayed reactions and gut symptoms add {{FOOD_INTOLERANCE_SENSOR}} (Cytolisa IgG panel). The two are complementary — one tests immediate IgE, the other tests delayed IgG.

### "I have food intolerances or gut symptoms"

{{FOOD_INTOLERANCE_SENSOR}} is the IgG panel for delayed-type food reactions and supports an elimination-and-reintroduction protocol. For broader gut context add {{METABOLISM_SENSOR}} (Micronutrient + Microbiome GC-MS layers — including butyrate-producing-bacteria activity). For the genetic side of lactose and gluten handling, {{NUTRITION_SENSOR}} covers LCT and gluten-sensitivity context.

### "We want to start a family"

{{FERTILITY_SENSOR}} is the doctors-only genetic panel covering folate (MTHFR), hormone-metabolism, thrombosis risk relevant to IVF, Omega-3 / FADS for gamete quality, and selected carrier-status markers. Both partners can be tested separately. The companion blood panels are {{BLOOD_PANEL_HORMONES_FEMALE}} / {{BLOOD_PANEL_HORMONES_MALE}} for current hormonal status.

### "I'm planning pregnancy or am already pregnant"

{{PREGNANCY_SENSOR}} is the doctors-only genetic panel covering MTHFR (methylfolate vs folic acid choice), thrombosis risk, iron handling (HFE), Vitamin D activation, Omega-3 / DHA conversion — all directly relevant to prenatal supplementation choice and monitoring. Customers in active pregnancy should switch from {{SUPPLEMENT_DAILY}} to a standardised prenatal product; the {{PREGNANCY_SENSOR}} report informs which prenatal formulation best suits them.

### "My baby was born / I have a newborn"

{{BABY_SENSOR}} is the 111-marker GC-MS newborn screen for inherited metabolic, endocrine, haematological, and immune conditions. It complements rather than replaces the standard hospital newborn screen and is parent-facing in language but designed to be discussed with the paediatrician.

### "I want a comprehensive health overview"

The deepest single product is {{PACKAGE_LIFESTYLE_PLUS}} (the primary pitch product): free Lifestyle DNA bundle (Weight, Nutrition, Toxo, Burnout, Biological Age, Recipe Book) plus a 12-month {{SUPPLEMENT_DAILY}} subscription. For doctors and clinicians the equivalent is {{EXPERT_PREVENTION}} — a consolidated clinician report covering Cancer, Heart, Brain, Digestion, Metabolism, Musculoskeletal, and Eyes prevention.

### "I want early cancer detection"

{{MULTI_CANCER_SENSOR}} is the doctors-only multi-omics blood-based screening test covering 15+ cancer types. It is intended as a surveillance tool (periodic repeat) for higher-risk groups by age, family history, or environmental exposure. Not a replacement for standard age-appropriate screening (mammography, colonoscopy, etc.).

### "I'm a woman, hormonal symptoms or PCOS"

The combined approach: {{HORMONE_FEMALE_SENSOR}} for the genetic predisposition (oestrogen and progesterone pathways, cycle traits) + {{BLOOD_PANEL_HORMONES_FEMALE}} for the current measured hormones (FSH, LH, Progesterone, SHBG, Estradiol). The two together explain both the "why" and the "what right now". For perimenopause-focused customers add {{BLOOD_PANEL_LONGEVITY_HORMONES_FEMALE}}.

### "I'm a man, fatigue / libido / aging concerns"

The combined approach: {{HORMONE_MALE_SENSOR}} for the genetic side (testosterone / DHT pathways, androgen-receptor sensitivity) + {{BLOOD_PANEL_HORMONES_MALE}} for current measured hormones (Testosterone, DHEA-S, SHBG). For ageing-focused customers add {{BLOOD_PANEL_LONGEVITY_HORMONES_MALE}}. Cross-reference {{BIOLOGICAL_AGE_SENSOR}} if longevity is the framing.

---

## By customer demographic

### Active mother, 30s–40s, "I just want to feel my best"

Best entry: {{PACKAGE_LIFESTYLE_PLUS}}. Adds practical daily-value (the supplement subscription) on top of the genetic baseline. If budget allows, layer in {{BLOOD_PANEL_NUTRIENTS}} to confirm B12 + Vitamin D + magnesium status — these are the most commonly deficient in this group.

### Man, 40s–50s, prevention-focused

Best entry: {{PACKAGE_LIFESTYLE_PLUS}} plus {{BLOOD_PANEL_HEART_METABOLIC}} and {{BLOOD_PANEL_HORMONES_MALE}}. For deeper prevention, {{EXPERT_PREVENTION}} via a doctor consultation.

### Postmenopausal woman

Best entry: {{NUTRITION_SENSOR}} (especially VDR, LCT, HFE, MTHFR), {{BIOLOGICAL_AGE_SENSOR}}, plus {{BLOOD_PANEL_LONGEVITY_BASE}} for the integrated longevity readout. Bone-relevant nutrient handling is the centre of gravity here — magnesium, vitamin D, calcium-pairing variants.

### Serious athlete

Best entry: {{PACKAGE_PERFORMANCE_PLUS}} (Performance DNA bundle + supplement subscription) plus {{BLOOD_PANEL_INFLAMMATION}} for training-load monitoring. Add {{BLOOD_PANEL_HORMONES_MALE}} / {{BLOOD_PANEL_HORMONES_FEMALE}} for endocrine monitoring under heavy training load.

### Couple planning a baby

Both partners do {{FERTILITY_SENSOR}} (doctors-only). The woman adds {{BLOOD_PANEL_HORMONES_FEMALE}}; both can complement with {{NUTRITION_SENSOR}} for the longer-term nutrient context. After conception, the woman transitions to {{PREGNANCY_SENSOR}}-informed prenatal planning.

### Customer on multiple medications

Lead with {{PHARMACO_SENSOR}} — single test, lifetime relevance, drives a clinician conversation that can change prescribing. Add lifestyle products only if the customer asks for more.

### Customer with a strong cosmetics interest

Best entry: {{PACKAGE_BEAUTY_PLUS}} (Beauty DNA free + DAY/NIGHT serum subscription). Add {{COSMETICS_BODY_LOTION_235ML}} subscription if body skin is also a concern. Pair with {{SUPPLEMENT_DAILY}} for the systemic nutrients that support skin from the inside.

---

## Quick-start entry tiers

### Cheapest meaningful entry

{{NUTRITION_SENSOR}} as a standalone test — lifetime-valid, covers the most-asked questions about food, energy, and supplementation. Customers can add anything later.

### Best value for general health

{{PACKAGE_LIFESTYLE_PLUS}} (primary pitch product) — combines five lifestyle DNA tests free with a 12-month {{SUPPLEMENT_DAILY}} subscription. The subscription is what produces ongoing customer value rather than a one-time test that sits in a drawer.

### Most comprehensive single order

{{PACKAGE_LIFESTYLE_PLUS}} + {{BLOOD_PANEL_LONGEVITY_BASE}} + {{ALLERGY_SENSOR}} + {{FOOD_INTOLERANCE_SENSOR}} + {{METABOLISM_SENSOR}}. Covers genetics, blood-marker snapshot, immune reactivity, and metabolite status in one go.

### Doctor / clinician channel

{{EXPERT_PREVENTION}} as the entry. Add {{PHARMACO_SENSOR}} for any patient on long-term medication. Add {{FERTILITY_SENSOR}} / {{PREGNANCY_SENSOR}} for reproductive medicine. Add {{MULTI_CANCER_SENSOR}} for surveillance in higher-risk patients.

---

## Bundle vs standalone reasoning

### When a bundle wins

Whenever the customer wants ongoing daily benefit — the "+" subscription bundles include the DNA test free during the minimum subscription term, so the bundle price ends up lower than test-plus-supplement bought separately.

### When standalone wins

When the customer is unsure, wants to "try the science" first, or is only interested in the genetic readout without daily supplementation. Standalone DNA tests are lifetime-valid and can be supplemented later.

### When a blood panel wins

Whenever the customer's question is about the current state ("am I deficient right now", "is my inflammation up") rather than the lifetime predisposition. Blood panels are repeatable and reflect intervention — they're the right product for tracking change over months.

---

## Sequencing recommendations over time

### Year 1 — establish the baseline

{{PACKAGE_LIFESTYLE_PLUS}} subscription (or matching reseller bundle). The customer gets the genetic baseline once and starts on personalised supplements immediately.

### Year 1, around month 3 — add the current-state layer

The first blood panel — typically {{BLOOD_PANEL_NUTRIENTS}} or {{BLOOD_PANEL_LONGEVITY_BASE}} depending on the customer's primary concern. This gives a real reading on whether the supplement is delivering.

### Year 2+ — periodic blood retest

Re-run the relevant blood panels every 6–12 months to track progress and re-tune {{SUPPLEMENT_DAILY}} dose against current values.

### Life-stage triggers

A change in life stage (planning pregnancy, athletic event, new diagnosis, new medication) is the natural trigger to add a focused product: {{FERTILITY_SENSOR}}, {{PERFORMANCE_SENSOR}}, {{EXPERT_PREVENTION}}, or {{PHARMACO_SENSOR}}.

---

## Downloadable Resources

- [Different kinds of gene analyses (PDF, DE)](https://raw.githubusercontent.com/Novogenia/novogenia-chatbot-assets/main/company-science/A3_Kinds_of_gene_analyses_DE.pdf)
- [Novogenia Demo Reports (PDF, DE)](https://raw.githubusercontent.com/Novogenia/novogenia-chatbot-assets/main/demo-reports/F1_Demoreports_v15_DE.pdf)
- [Novogenia Demo Reports (PDF, EN)](https://raw.githubusercontent.com/Novogenia/novogenia-chatbot-assets/main/demo-reports/F2_Demoreports_v15_EN.pdf)
