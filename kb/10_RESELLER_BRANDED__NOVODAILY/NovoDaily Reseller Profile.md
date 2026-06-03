# NovoDaily Reseller Profile — Consolidated
<!--
  REQUIRES_VARIABLE: (none — always loaded for the NovoDaily tenant)
  PURPOSE: Single source-of-truth for everything that defines the NovoDaily reseller — identity,
           availability, products, terminology, commercial rules, partnership model, and partner training.
           This is the ONE file that fully configures the NovoDaily chatbot tenant.
  REPLACES: NovoDaily Reseller Identity.md + NovoDaily Product Availability.xlsx +
            Reseller Onboarding & Partnership Model.md + NovoDaily Skillbooks - Partner Training.md
  SOURCES: PRODUCT MASTER MATCHING.xlsx (source of truth for products) + novodaily.com (NPDW2412 catalog) +
           reseller specification (May 2026) + NovoDaily Partner Handbooks 1, 2, 3.
  AUDIENCE: NovoDaily chatbot tenants (customer + reseller scenarios).
-->

---

# PART A — RESELLER IDENTITY

## Reseller Information

| Field | Value |
|---|---|
| Reseller Name | NovoDaily (Novogenia Marketing GmbH) |
| Primary Language | German (de-DE) |
| Region / Market | DACH (Austria, Germany, Switzerland) |
| Website | https://novodaily.com |
| Support Contact | via novodaily.com/kontakt |
| Special Notes | Own brand for small resellers. Supplements + DNA tests focus. "+" suffix = subscription product. Expert line (blue branding) is doctors-only. |

---

## Bot Configuration Flags

These flags override default bot behavior for this tenant. Full schema spec: see `ARCHITECTURE/Reseller_Config_Schema.md`.

| Flag | Value | Begründung / Notiz |
|---|---|---|
| allow_science_beyond_products | true | NovoDaily will breite Wissens-Autorität — Bot darf Science zu nicht-verfügbaren Produkten erklären, redirected aber auf verfügbare. |
| brand_mode | reseller_led | NovoDaily ist Eigenmarke, nicht Novogenia-Vermittler. Labor = "unser zertifiziertes Partnerlabor". |
| founder_visibility | subtle | Wallerstorfer wird im Wissenschafts-Kontext natürlich erwähnt, aber kein aktiver Social-Push. |
| tone_style | du | Per NovoDaily-Vorgabe, Du-Form überall im Deutschen. |
| language_mode | adaptive | DACH-Markt, Mehrsprachigkeit erwünscht — Bot wechselt mit der Nutzer-Sprache. |
| video_recommendations_enabled | true | Video-Library wird genutzt. Sprache: DE-zuerst, EN-Fallback. |
| commercial_disclosure_mode | subtle | Darwin-AG / Novogenia-AG-Erwähnung erlaubt im passenden Kontext, niemals als Investment-Empfehlung. |
| primary_language | de-DE | Hauptsprache Deutsch, Sekundär Englisch. |
| Flow 01 — Product Q&A | true | aktiv |
| Flow 02 — Sales Training | true | aktiv |
| Flow 03 — Legal Questions | true | aktiv |
| Flow 04 — Ad Copy Review | true | aktiv |
| Flow 05 — Reseller Onboarding | true | aktiv |
| Flow 06 — Reseller Referrals | true | aktiv |
| Flow 07 — NovoPilot Platform Help | true | aktiv |
| Flow 08 — Academy Certification | true | aktiv |
| Flow 09 — Company Information | true | aktiv |
| Flow 10 — Marketing Materials | true | aktiv |
| Flow 11 — Custom Supplement Creation | true | aktiv |

**Wie der Bot diese Flags nutzt:** Vor jeder Antwort konsultiert der Bot diese Tabelle. Default-Verhalten aus dem Master Prompt wird durch die hier definierten Werte überschrieben.

---

## Units of Measurement

| Setting | Value | Options |
|---|---|---|
| Measurement System | metric | metric (kg, cm, °C, ml) |
| Weight Unit | kg | |
| Height Unit | cm | |
| Temperature Unit | °C | |
| Volume Unit | ml | |
| Energy Unit | kcal | |

---

## Brand & Company Name Overrides

| Variable | Global Default | Reseller Name |
|---|---|---|
| {{COMPANY_NAME}} | Novogenia | NovoDaily |
| {{WEBSITE_NAME}} | — | NovoDaily Website (novodaily.com) |
| {{RESELLER_PLATFORM_NAME}} | — | NovoPilot Platform (where small resellers log in) |
| {{PLATFORM_NAME}} | DNAnutriControl | NovoDaily Customer Portal |
| {{LAB_LOCATION}} | Eugendorf/Salzburg, Austria | Eugendorf bei Salzburg, Österreich |
| {{REPORT_PORTAL}} | DNAnutriControl portal | NovoDaily Customer Portal |
| {{FOOD_TABLE_NAME}} | Food Table | Lebensmittel-Check |

> **Important:** "DNAnutriControl" is NEVER used under the NovoDaily brand. Three distinct platforms exist for NovoDaily: the public **NovoDaily Website** (novodaily.com), the **NovoPilot Platform** (small reseller login), and the **NovoDaily Customer Portal** (end-customer login for results, reports, and food table).

---

## Delivery & Service Options

| Setting | Value | Notes |
|---|---|---|
| Digital Report (HTML) available | coming_soon | Coming soon via NovoDaily Customer Portal |
| Digital Report (PDF) available | true | PDF download via NovoDaily Customer Portal |
| Printed report (physical book) available | true | Hochwertig gedruckt; included free with Lifestyle+ |
| Product shipping destination | Customer home address | Direct to customer |
| Chatbot available | coming_soon | NovoPilot for NovoDaily is in setup — not yet customer-facing |

---

## Section 1 — Single Analyses

| Variable | Category | Global Default | Notes | Reseller Name | Shop Link | Available |
|---|---|---|---|---|---|---|
| **LIFESTYLE DNA** | | | | | | |
| {{NUTRITION_SENSOR}} | Lifestyle DNA | Nutrition Sensor | Standalone in Weitere Analysen + bundled in Lifestyle | NovoDaily Nutrition | https://novodaily.com/NPDW2412/alle-produkte/ | true |
| {{WEIGHT_SENSOR}} | Lifestyle DNA | Weight Sensor | €299 standalone | NovoDaily Shape | https://novodaily.com/NPDW2412/NovoDaily-Shape/SW10005.1 | true |
| {{PERFORMANCE_SENSOR}} | Lifestyle DNA | Performance Sensor | Coming Soon on novodaily.com | NovoDaily Performance | — | coming_soon |
| {{TOXO_SENSOR}} | Lifestyle DNA | Toxo-Sensor | Renamed to "Detox" under NovoDaily | NovoDaily Detox | https://novodaily.com/NPDW2412/alle-produkte/ | true |
| {{BIOLOGICAL_AGE_SENSOR}} | Lifestyle DNA | Biological Age Sensor | | NovoDaily Biological Age | https://novodaily.com/NPDW2412/alle-produkte/ | true |
| {{BURNOUT_SENSOR}} | Lifestyle DNA | Burnout Sensor | COMT gene | NovoDaily Burnout | https://novodaily.com/NPDW2412/alle-produkte/ | true |
| {{METHYLATION_SENSOR}} | Lifestyle DNA | Methylation Sensor | Not listed on NovoDaily | — | — | false |
| {{BEAUTY_SENSOR}} | Lifestyle DNA | Beauty Sensor | Sold as "Beauty" standalone test | NovoDaily Beauty | https://novodaily.com/NPDW2412/alle-produkte/ | true |
| {{RECIPE_BOOK}} | Lifestyle DNA | Recipe Book | "Rezeptbuch" — included free in Lifestyle+, also "Nutrition Plan" within Shape/Lifestyle/Performance | NovoDaily Rezeptbuch / Nutrition Plan | — | true |
| **MEDICAL DNA (Expert line — doctors only)** | | | | | | |
| {{PHARMACO_SENSOR}} | Medical DNA | Pharmaco Sensor | Sold as "Drug Response" in Weitere Analysen | NovoDaily Drug Response | https://novodaily.com/NPDW2412/alle-produkte/ | true |
| {{HORMONE_FEMALE_SENSOR}} | Medical DNA | Hormone Female Sensor | Genetic test of female-hormone pathways; complements the {{BLOOD_PANEL_HORMONES_FEMALE}} blood panel | NovoDaily Hormone Female Sensor | — | true |
| {{HORMONE_MALE_SENSOR}} | Medical DNA | Hormone Male Sensor | Genetic test of male-hormone pathways; complements the {{BLOOD_PANEL_HORMONES_MALE}} blood panel | NovoDaily Hormone Male Sensor | — | true |
| {{GLUTEN_SENSOR}} | Medical DNA | Gluten Sensor | Not listed under NovoDaily | — | — | false |
| {{LACTOSE_SENSOR}} | Medical DNA | Lactose Sensor | Not listed under NovoDaily | — | — | false |
| {{IBD_SENSOR}} | Medical DNA | IBD Sensor | Likely included in Expert Prevention bundle | — | — | false |
| {{BONE_HEALTH_SENSOR}} | Medical DNA | Bone Health Sensor | Likely included in Expert Prevention bundle | — | — | false |
| {{JOINT_SENSOR}} | Medical DNA | Joint Sensor | Likely included in Expert Prevention bundle (Musculoskeletal) | — | — | false |
| {{ADHD_SENSOR}} | Medical DNA | ADHD Sensor | Not listed | — | — | false |
| {{PERIODONTITIS_SENSOR}} | Medical DNA | Periodontitis Sensor | Not listed | — | — | false |
| {{AMD_SENSOR}} | Medical DNA | AMD Sensor | Likely included in Expert Prevention (Eyes) | — | — | false |
| {{GLAUCOMA_SENSOR}} | Medical DNA | Glaucoma Sensor | Likely included in Expert Prevention (Eyes) | — | — | false |
| {{SKIN_HEALTH_SENSOR}} | Medical DNA | Skin Health Sensor | Covered by Beauty / Beauty+ | — | — | false |
| {{DIABETES_SENSOR}} | Medical DNA | Diabetes Sensor | Likely included in Expert Prevention (Metabolism) | — | — | false |
| {{ALZHEIMER_SENSOR}} | Medical DNA | Alzheimer Sensor | Likely included in Expert Prevention (Brain) | — | — | false |
| {{DEPRESSION_SENSOR}} | Medical DNA | Depression Sensor | Not listed | — | — | false |
| {{SCHIZOPHRENIA_SENSOR}} | Medical DNA | Schizophrenia Sensor | Not listed | — | — | false |
| {{THROMBO_SENSOR}} | Medical DNA | Thrombo Sensor | Not listed | — | — | false |
| {{CARDIOVASCULAR_SENSOR}} | Medical DNA | Cardiovascular Sensor | Likely included in Expert Prevention (Heart) | — | — | false |
| {{HYPERTENSION_SENSOR}} | Medical DNA | Hypertension Sensor | Likely included in Expert Prevention (Heart) | — | — | false |
| {{HIV_RESISTANCE_SENSOR}} | Medical DNA | HIV Resistance Sensor | Not listed | — | — | false |
| {{BREAST_HEALTH_SENSOR}} | Medical DNA | Breast Health Sensor | Likely included in Expert Prevention (Cancer) | — | — | false |
| {{PROSTATE_HEALTH_SENSOR}} | Medical DNA | Prostate Health Sensor | Likely included in Expert Prevention (Cancer) | — | — | false |
| {{LUNG_HEALTH_SENSOR}} | Medical DNA | Lung Health Sensor | Likely included in Expert Prevention (Cancer) | — | — | false |
| {{COLON_HEALTH_SENSOR}} | Medical DNA | Colon Health Sensor | Likely included in Expert Prevention (Digestion) | — | — | false |
| {{IRON_SENSOR}} | Medical DNA | Iron Sensor | Not listed | — | — | false |
| {{PREGNANCY_SENSOR}} | Medical DNA | Pregnancy Sensor | NovoDaily Expert (doctors-only); shown on Fertility cover | NovoDaily Expert Pregnancy | — | true |
| {{FERTILITY_SENSOR}} | Medical DNA | Fertility Sensor | NovoDaily Expert (doctors-only) | NovoDaily Expert Fertility | — | true |
| **PREVENTION BUNDLE (Expert line)** | | | | | | |
| {{EXPERT_PREVENTION}} | Medical DNA bundle | — | New variable: Expert Prevention bundle covering Cancer / Heart / Brain / Digestion / Metabolism / Musculoskeletal / Eyes | NovoDaily Expert Prevention | — | true |
| **MULTIOMICS** | | | | | | |
| {{MULTI_CANCER_SENSOR}} | MultiOmics | Multi Cancer Sensor | NovoDaily Expert (doctors-only); medical blood analysis | NovoDaily Expert Multi Cancer Sensor | — | true |
| **BLOOD & URINE** | | | | | | |
| {{ALLERGY_SENSOR}} | Blood/Urine | Allergy Sensor | IgE; ALEX2; ~300 allergens | NovoDaily Allergy | https://novodaily.com/NPDW2412/alle-produkte/ | true |
| {{FOOD_INTOLERANCE_SENSOR}} | Blood/Urine | Food Intolerance Sensor | IgG; Cytolisa ELISA | NovoDaily Food Intolerance | https://novodaily.com/NPDW2412/alle-produkte/ | true |
| {{MICRONUTRIENT_SENSOR}} | Blood/Urine | Micronutrient Sensor | Standalone variant not listed under NovoDaily | — | — | coming_soon |
| {{MICROBIOME_SENSOR}} | Blood/Urine | Microbiome Sensor | Standalone variant not listed under NovoDaily | — | — | coming_soon |
| {{METABOLISM_SENSOR}} | Blood/Urine | Metabolism Sensor | Bundle of Micronutrient + Microbiome | NovoDaily Metabolism | https://novodaily.com/NPDW2412/alle-produkte/ | true |
| **ABBOTT BLOOD PANELS** | | | | | | |
| {{BLOOD_PANEL_HEART_METABOLIC}} | Blood/Urine | Heart & Metabolic Check | LDL + Triglycerides + Ultra HDL + CRP + Magnesium | NovoDaily Heart & Metabolic Check | — | true |
| {{BLOOD_PANEL_HORMONES_FEMALE}} | Blood/Urine | Hormone Check (Female) | FSH + LH + Progesterone + SHBG + Estradiol | NovoDaily Hormone Check (Female) | — | true |
| {{BLOOD_PANEL_HORMONES_MALE}} | Blood/Urine | Hormone Check (Male) | Testosterone + DHEA-S + SHBG | NovoDaily Hormone Check (Male) | — | true |
| {{BLOOD_PANEL_NUTRIENTS}} | Blood/Urine | Nutrient Check | Active B12 + Vitamin D + Magnesium | NovoDaily Nutrient Check | — | true |
| {{BLOOD_PANEL_INFLAMMATION}} | Blood/Urine | Inflammation Check | CRP + Magnesium + Vitamin D | NovoDaily Inflammation Check | — | true |
| {{BLOOD_PANEL_LONGEVITY_BASE}} | Blood/Urine | Longevity Check (Base) | LDL + Trig + HDL + CRP + Mg + B12 + Vitamin D + TSH + Free T3 | NovoDaily Longevity Check (Base) | — | true |
| {{BLOOD_PANEL_LONGEVITY_HORMONES_FEMALE}} | Blood/Urine | Longevity Hormones (Female) | Add-on to base: Progesterone + SHBG + Estradiol | NovoDaily Longevity Hormones (Female) | — | true |
| {{BLOOD_PANEL_LONGEVITY_HORMONES_MALE}} | Blood/Urine | Longevity Hormones (Male) | Add-on to base: Testosterone + SHBG | NovoDaily Longevity Hormones (Male) | — | true |
| **SPECIALTY** | | | | | | |
| {{BABY_SENSOR}} | Specialty | Baby Sensor | NovoDaily Newborn Screening | NovoDaily Newborn Screening | https://novodaily.com/NPDW2412/alle-produkte/ | true |
| {{BREAST_MILK_SENSOR}} | Specialty | Breast Milk Sensor | Not listed under NovoDaily | — | — | false |
| **DIGITAL** | | | | | | |
| {{EPIGENETICS_REPORT}} | Digital | Epigenetics Info Report Section | Not listed under NovoDaily | — | — | false |
| **PERFORMANCE STANDALONE** | | | | | | |
| {{JUST_PERFORMANCE}} | Lifestyle DNA | — | Performance analysis only (without Lifestyle bundle) | NovoDaily Just Performance | https://novodaily.com/NPDW2412/alle-produkte/ | true |

---

## Section 2 — Personalized Products

| Variable | Category | Global Default | Notes | Reseller Name | Shop Link | Available |
|---|---|---|---|---|---|---|
| **SUPPLEMENTS** | | | | | | |
| {{SUPPLEMENT_DAILY}} | Supplement | NutriMe Complete (10X/REVIV: Precision Supplements) | 90-day pack; €3.80/day, €114/month; cancellable every 3 months when bought standalone (NovoDailies+) | NovoDailies (subscription: NovoDailies+) | https://novodaily.com/NPDW2412/nahrungsergaenzung/ | true |
| {{SUPPLEMENT_WEIGHT}} | Supplement | NutriMe Weight Management | Shape-formulated daily supplement, 3-month supply; sold as NovoShapies+ subscription | NovoShapies (subscription: NovoShapies+) | https://novodaily.com/NPDW2412/alle-produkte/ | true |
| **COSMETICS** | | | | | | |
| {{COSMETICS}} | Cosmetics | Presence / BeautyMe | DAY + NIGHT serums; 3-month supply; subscription only | NovoBeauties (subscription: NovoBeauties+) | https://novodaily.com/NPDW2412/alle-produkte/ | true |
| {{COSMETICS_DAY_NIGHT_95ML}} | Cosmetics | BeautyMe Day & Night | DAY Serum + NIGHT Serum, 3-month supply | NovoBeauties+ | — | true |
| {{COSMETICS_BODY_LOTION_235ML}} | Cosmetics | BeautyMe Body Lotion | 3-month supply, subscription only | NovoLotion+ | — | true |
| {{COSMETICS_DAY_NIGHT_BODY_BUNDLE}} | Cosmetics | BeautyMe Day & Night & Body | Combined bundle SKU not listed under NovoDaily | — | — | coming_soon |

---

## Section 3 — Packages & Bundles

| Variable | Global Default | Contains | Reseller Name | Shop Link | Available |
|---|---|---|---|---|---|
| {{PACKAGE_SHAPE}} | — | Shape DNA only | NovoDaily Shape | https://novodaily.com/NPDW2412/NovoDaily-Shape/SW10005.1 | true |
| {{PACKAGE_LIFESTYLE}} | — | Shape + Nutrition + Detox + Burnout + Bio Age + Nutrition Plan (one-time DNA test) | NovoDaily Lifestyle | https://novodaily.com/NPDW2412/Novodaily-Lifestyle/lifestyleND.1 | true |
| {{PACKAGE_PERFORMANCE}} | — | Lifestyle + Performance Sensor (one-time DNA test) | NovoDaily Performance | — | coming_soon |
| {{PACKAGE_BEAUTY}} | — | Beauty DNA only | NovoDaily Beauty | https://novodaily.com/NPDW2412/alle-produkte/ | true |
| {{PACKAGE_SHAPE_PLUS}} | — | Shape DNA (free) + NovoShapies subscription, 12-month minimum | NovoDaily Shape+ | https://novodaily.com/NPDW2412/alle-produkte/ | true |
| {{PACKAGE_LIFESTYLE_PLUS}} | — | Lifestyle DNA (free) + NovoDailies subscription, 12-month minimum — PRIMARY PITCH PRODUCT | NovoDaily Lifestyle+ | https://novodaily.com/NPDW2412/NovoDaily-Lifestyle/ND10016 | true |
| {{PACKAGE_PERFORMANCE_PLUS}} | — | Performance DNA (free) + NovoDailies subscription, 15-month minimum | NovoDaily Performance+ | — | coming_soon |
| {{PACKAGE_BEAUTY_PLUS}} | — | Beauty DNA (free) + DAY/NIGHT serum subscription, 12-month minimum | NovoDaily Beauty+ | https://novodaily.com/NPDW2412/alle-produkte/ | true |

---

## Terminology Overrides

| Variable | Global Default | Reseller Term |
|---|---|---|
| {{PELLET_NAME}} | Micro Beats / micro-transporter pellets | Mikrotransporter |
| {{SACHET_NAME}} | sachet / daily portion bag | Tagesbeutel (Sachet) |

---

## Additional Reseller-Specific Rules

### Tone & Communication Style

> Friendly, approachable German ("du"-form). Avoid medical jargon — explain genetic concepts in plain language. Emphasise convenience, daily routine fit, and that NovoDailies are produced in Austria with the customer's name on each sachet.

### Pricing & Commercial Rules

> NovoDaily Lifestyle+ is the PRIMARY PITCH PRODUCT: €114/month, €3.80/day, 12-month minimum, then auto-renews every 3 months. Free Lifestyle DNA test (Shape + Nutrition + Detox + Burnout + Bio Age + printed Nutrition Plan ~400+ pages) included.
> Standalone Shape DNA test: €299. Standalone Lifestyle DNA test: €650.
> NovoDailies+ standalone (without DNA test): €114/month, 3-month cancellation cycle.
> Performance+ requires 15-month minimum (vs. 12 for Lifestyle+ and Shape+).
> Cancellation possible online at any time after minimum term.

### Regulatory / Legal Notes

> Use the standard NovoDaily scientific disclaimer: genetic traits are scientifically confirmed (≥3 independent studies per gene); derived dosing/dietary recommendations are logical conclusions in an experimental stage, not yet validated by randomised placebo-controlled studies for all effects (validated for folic acid and Vitamin B2). Reference PubMed IDs in printed reports.

### Product-Specific Overrides

> "Detox" is used instead of "Toxo-Sensor" for end customers under NovoDaily.
> "Nutrition Plan" is the customer-facing name for the dietary recommendation booklet inside Shape / Lifestyle / Performance test packages.
> "NovoDailies" can also refer to the supplement product itself; "NovoDailies+" specifically means the supplement subscription standalone (without DNA test).

### Unavailable Feature Notes

> If asked about Medical DNA tests (Pharmaco aside, which is sold as "Drug Response"), Methylation, Breast Milk analysis, Epigenetics report, or other items marked Available=false above, respond that these are not available under the NovoDaily brand and offer the Expert line referral for clinicians where appropriate.
> Performance standalone test, Performance+ subscription: mark as "Coming Soon" — not yet purchasable on novodaily.com.
> Expert line products (Prevention bundle, Fertility, Pregnancy, Multi Cancer Sensor, Expert Performance) are doctors-only — direct interested professionals via novodaily.com/kontakt rather than offering for direct purchase.

---

## NovoDaily Product Map (quick reference)

### One-time DNA tests (no subscription)

- NovoDaily Shape — Shape DNA only
- NovoDaily Lifestyle — Shape + Nutrition + Detox + Burnout + Bio Age + Nutrition Plan
- NovoDaily Performance — Lifestyle + Performance Sensor (Coming Soon)
- NovoDaily Beauty — Beauty DNA only

### Subscription products (the "+" line)

- NovoDaily Shape+ — Shape DNA free + NovoShapies (12 months)
- NovoDaily Lifestyle+ — Lifestyle DNA free + NovoDailies (12 months) ← PRIMARY
- NovoDaily Performance+ — Performance DNA free + NovoDailies (15 months) (Coming Soon)
- NovoDaily Beauty+ — Beauty DNA free + DAY/NIGHT serums (12 months)

### Personalized products sold standalone (subscription only, 3-month supply)

- NovoDailies+ — daily supplement subscription
- NovoShapies+ — Shape-only supplement subscription
- NovoBeauties+ — DAY + NIGHT serums
- NovoLotion+ — body lotion

### Individual analyses (Weitere Analysen)

- NovoDaily Heart & Metabolic Check (Abbott blood panel)
- NovoDaily Hormone Check (Female / Male) (Abbott blood panel)
- NovoDaily Nutrient Check (Abbott blood panel)
- NovoDaily Inflammation Check (Abbott blood panel)
- NovoDaily Longevity Check (Base) (Abbott blood panel)
- NovoDaily Longevity Hormones (Female / Male) (Abbott blood panel add-on)
- Allergy
- Food Intolerance
- Metabolism
- Nutrition (standalone)
- Detox (standalone)
- Burnout (standalone)
- Biological Age (standalone)
- Newborn Screening
- Drug Response
- Just Performance

### NovoDaily Expert (doctors-only, blue branding)

- Expert Prevention (Cancer / Heart / Brain / Digestion / Metabolism / Musculoskeletal / Eyes)
- Expert Fertility (incl. Pregnancy)
- Expert Performance
- Expert Multi Cancer Sensor

---

# PART B — PRODUCT AVAILABILITY (full matrix)

### Variable Availability — full per-variable matrix

| Variable Token | Global Default Name | NovoDaily Reseller Name | Status | Notes |
|---|---|---|---|---|
| {{NUTRITION_SENSOR}} | Nutrition Sensor | NovoDaily Nutrition | AVAILABLE | Bundled in Lifestyle and Performance packages |
| {{WEIGHT_SENSOR}} | Weight Sensor | NovoDaily Shape | AVAILABLE | Bundled in Shape/Lifestyle/Performance |
| {{PERFORMANCE_SENSOR}} | Performance Sensor | NovoDaily Performance | COMING SOON | Not yet on novodaily.com |
| {{TOXO_SENSOR}} | Toxo-Sensor | NovoDaily Detox | AVAILABLE | Renamed 'Detox' under NovoDaily |
| {{BIOLOGICAL_AGE_SENSOR}} | Biological Age Sensor | NovoDaily Biological Age | AVAILABLE |  |
| {{BURNOUT_SENSOR}} | Burnout Sensor | NovoDaily Burnout | AVAILABLE |  |
| {{METHYLATION_SENSOR}} | Methylation Sensor | — | NOT OFFERED | Not listed |
| {{BEAUTY_SENSOR}} | Beauty Sensor | NovoDaily Beauty | AVAILABLE |  |
| {{RECIPE_BOOK}} | Recipe Book | NovoDaily Rezeptbuch / Nutrition Plan | AVAILABLE | Bundled free in Lifestyle+ |
| {{PHARMACO_SENSOR}} | Pharmaco Sensor | NovoDaily Drug Response | AVAILABLE |  |
| {{GLUTEN_SENSOR}} | Gluten Sensor | — | NOT OFFERED |  |
| {{LACTOSE_SENSOR}} | Lactose Sensor | — | NOT OFFERED |  |
| {{IBD_SENSOR}} | IBD Sensor | — | NOT OFFERED | Folded into Expert Prevention bundle |
| {{BONE_HEALTH_SENSOR}} | Bone Health Sensor | — | NOT OFFERED | Folded into Expert Prevention |
| {{JOINT_SENSOR}} | Joint Sensor | — | NOT OFFERED | Folded into Expert Prevention |
| {{ADHD_SENSOR}} | ADHD Sensor | — | NOT OFFERED |  |
| {{PERIODONTITIS_SENSOR}} | Periodontitis Sensor | — | NOT OFFERED |  |
| {{AMD_SENSOR}} | AMD Sensor | — | NOT OFFERED | Folded into Expert Prevention |
| {{GLAUCOMA_SENSOR}} | Glaucoma Sensor | — | NOT OFFERED | Folded into Expert Prevention |
| {{SKIN_HEALTH_SENSOR}} | Skin Health Sensor | — | NOT OFFERED | Covered by Beauty line |
| {{DIABETES_SENSOR}} | Diabetes Sensor | — | NOT OFFERED | Folded into Expert Prevention |
| {{ALZHEIMER_SENSOR}} | Alzheimer Sensor | — | NOT OFFERED | Folded into Expert Prevention |
| {{DEPRESSION_SENSOR}} | Depression Sensor | — | NOT OFFERED |  |
| {{SCHIZOPHRENIA_SENSOR}} | Schizophrenia Sensor | — | NOT OFFERED |  |
| {{THROMBO_SENSOR}} | Thrombo Sensor | — | NOT OFFERED |  |
| {{CARDIOVASCULAR_SENSOR}} | Cardiovascular Sensor | — | NOT OFFERED | Folded into Expert Prevention |
| {{HYPERTENSION_SENSOR}} | Hypertension Sensor | — | NOT OFFERED | Folded into Expert Prevention |
| {{HIV_RESISTANCE_SENSOR}} | HIV Resistance Sensor | — | NOT OFFERED |  |
| {{BREAST_HEALTH_SENSOR}} | Breast Health Sensor | — | NOT OFFERED | Folded into Expert Prevention |
| {{PROSTATE_HEALTH_SENSOR}} | Prostate Health Sensor | — | NOT OFFERED | Folded into Expert Prevention |
| {{LUNG_HEALTH_SENSOR}} | Lung Health Sensor | — | NOT OFFERED | Folded into Expert Prevention |
| {{COLON_HEALTH_SENSOR}} | Colon Health Sensor | — | NOT OFFERED | Folded into Expert Prevention |
| {{IRON_SENSOR}} | Iron Sensor | — | NOT OFFERED |  |
| {{PREGNANCY_SENSOR}} | Pregnancy Sensor | NovoDaily Expert Pregnancy | AVAILABLE | Doctors-only via Expert line |
| {{FERTILITY_SENSOR}} | Fertility Sensor | NovoDaily Expert Fertility | AVAILABLE | Doctors-only via Expert line |
| {{EXPERT_PREVENTION}} | Expert Prevention Bundle | NovoDaily Expert Prevention | AVAILABLE | Doctors-only |
| {{MULTI_CANCER_SENSOR}} | Multi Cancer Sensor | NovoDaily Expert Multi Cancer Sensor | AVAILABLE | Doctors-only |
| {{ALLERGY_SENSOR}} | Allergy Sensor | NovoDaily Allergy | AVAILABLE |  |
| {{FOOD_INTOLERANCE_SENSOR}} | Food Intolerance Sensor | NovoDaily Food Intolerance | AVAILABLE |  |
| {{MICRONUTRIENT_SENSOR}} | Micronutrient Sensor | — | COMING SOON | Standalone variant not listed |
| {{MICROBIOME_SENSOR}} | Microbiome Sensor | — | COMING SOON | Standalone variant not listed |
| {{METABOLISM_SENSOR}} | Metabolism Sensor | NovoDaily Metabolism | AVAILABLE |  |
| {{BLOOD_PANEL_HEART_METABOLIC}} | Heart & Metabolic Check | NovoDaily Heart & Metabolic Check | AVAILABLE | Abbott blood panel |
| {{BLOOD_PANEL_HORMONES_FEMALE}} | Hormone Check (Female) | NovoDaily Hormone Check (Female) | AVAILABLE | Abbott blood panel |
| {{BLOOD_PANEL_HORMONES_MALE}} | Hormone Check (Male) | NovoDaily Hormone Check (Male) | AVAILABLE | Abbott blood panel |
| {{BLOOD_PANEL_NUTRIENTS}} | Nutrient Check | NovoDaily Nutrient Check | AVAILABLE | Abbott blood panel |
| {{BLOOD_PANEL_INFLAMMATION}} | Inflammation Check | NovoDaily Inflammation Check | AVAILABLE | Abbott blood panel |
| {{BLOOD_PANEL_LONGEVITY_BASE}} | Longevity Check (Base) | NovoDaily Longevity Check (Base) | AVAILABLE | Abbott blood panel |
| {{BLOOD_PANEL_LONGEVITY_HORMONES_FEMALE}} | Longevity Hormones (Female) | NovoDaily Longevity Hormones (Female) | AVAILABLE | Abbott blood panel |
| {{BLOOD_PANEL_LONGEVITY_HORMONES_MALE}} | Longevity Hormones (Male) | NovoDaily Longevity Hormones (Male) | AVAILABLE | Abbott blood panel |
| {{BABY_SENSOR}} | Baby Sensor | NovoDaily Newborn Screening | AVAILABLE |  |
| {{BREAST_MILK_SENSOR}} | Breast Milk Sensor | — | NOT OFFERED |  |
| {{EPIGENETICS_REPORT}} | Epigenetics Info Report Section | — | NOT OFFERED |  |
| {{JUST_PERFORMANCE}} | Performance (standalone) | NovoDaily Just Performance | AVAILABLE |  |
| {{SUPPLEMENT_DAILY}} | NutriMe Complete | NovoDailies / NovoDailies+ | AVAILABLE | Primary supplement |
| {{SUPPLEMENT_WEIGHT}} | NutriMe Weight Management | NovoShapies / NovoShapies+ | AVAILABLE |  |
| {{COSMETICS_DAY_NIGHT_95ML}} | BeautyMe Day & Night | NovoBeauties / NovoBeauties+ | AVAILABLE |  |
| {{COSMETICS_BODY_LOTION_235ML}} | BeautyMe Body Lotion | NovoLotion+ | AVAILABLE |  |
| {{COSMETICS_DAY_NIGHT_BODY_BUNDLE}} | BeautyMe Day & Night & Body | — | COMING SOON | Combined SKU TBC |
| {{HORMONE_FEMALE_SENSOR}} | Hormone Female Sensor | NovoDaily Hormone Female Sensor | AVAILABLE | Medical genetic test |
| {{HORMONE_MALE_SENSOR}} | Hormone Male Sensor | NovoDaily Hormone Male Sensor | AVAILABLE | Medical genetic test |
| **PACKAGES & BUNDLES** | | | | |
| {{PACKAGE_SHAPE}} | NovoDaily Shape (one-time DNA only) | NovoDaily Shape | AVAILABLE | One-time bundle |
| {{PACKAGE_LIFESTYLE}} | NovoDaily Lifestyle (one-time DNA only) | NovoDaily Lifestyle | AVAILABLE | One-time bundle: Shape + Nutrition + Detox + Burnout + Bio Age + Nutrition Plan |
| {{PACKAGE_PERFORMANCE}} | NovoDaily Performance (one-time DNA only) | NovoDaily Performance | COMING SOON | Lifestyle + Performance Sensor |
| {{PACKAGE_BEAUTY}} | NovoDaily Beauty (one-time DNA only) | NovoDaily Beauty | AVAILABLE | Beauty DNA test |
| {{PACKAGE_SHAPE_PLUS}} | NovoDaily Shape+ subscription | NovoDaily Shape+ | AVAILABLE | Shape DNA free + NovoShapies, 12 months min |
| {{PACKAGE_LIFESTYLE_PLUS}} | NovoDaily Lifestyle+ subscription (PRIMARY PITCH) | NovoDaily Lifestyle+ | AVAILABLE | Lifestyle DNA free + NovoDailies, 12 months min — PRIMARY PITCH |
| {{PACKAGE_PERFORMANCE_PLUS}} | NovoDaily Performance+ subscription | NovoDaily Performance+ | COMING SOON | Performance DNA free + NovoDailies, 15 months min |
| {{PACKAGE_BEAUTY_PLUS}} | NovoDaily Beauty+ subscription | NovoDaily Beauty+ | AVAILABLE | Beauty DNA free + DAY/NIGHT serum, 12 months min |
| {{PACKAGE_PREMIUM_PLUS}} | PremiumPlus / MedicalPlus (legacy bundle) | — | NOT OFFERED | Use NovoDaily Expert line instead |


### Product × Variables — which product contains which analyses


**NovoDaily Shape (one-time)** (AVAILABLE)
Contains: {{WEIGHT_SENSOR}}, {{RECIPE_BOOK}}

**NovoDaily Lifestyle (one-time)** (AVAILABLE)
Contains: {{NUTRITION_SENSOR}}, {{WEIGHT_SENSOR}}, {{TOXO_SENSOR}}, {{BIOLOGICAL_AGE_SENSOR}}, {{BURNOUT_SENSOR}}, {{RECIPE_BOOK}}

**NovoDaily Performance (one-time)** (COMING SOON)
Contains: {{NUTRITION_SENSOR}}, {{WEIGHT_SENSOR}}, {{TOXO_SENSOR}}, {{BIOLOGICAL_AGE_SENSOR}}, {{BURNOUT_SENSOR}}, {{PERFORMANCE_SENSOR}}, {{RECIPE_BOOK}}

**NovoDaily Beauty (one-time)** (AVAILABLE)
Contains: {{BEAUTY_SENSOR}}

**NovoDaily Shape+ (subscription)** (AVAILABLE)
Contains: {{WEIGHT_SENSOR}}, {{RECIPE_BOOK}}, {{SUPPLEMENT_WEIGHT}}

**NovoDaily Lifestyle+ (subscription) — PRIMARY PITCH** (AVAILABLE)
Contains: {{NUTRITION_SENSOR}}, {{WEIGHT_SENSOR}}, {{TOXO_SENSOR}}, {{BIOLOGICAL_AGE_SENSOR}}, {{BURNOUT_SENSOR}}, {{RECIPE_BOOK}}, {{SUPPLEMENT_DAILY}}

**NovoDaily Performance+ (subscription)** (COMING SOON)
Contains: {{NUTRITION_SENSOR}}, {{WEIGHT_SENSOR}}, {{TOXO_SENSOR}}, {{BIOLOGICAL_AGE_SENSOR}}, {{BURNOUT_SENSOR}}, {{PERFORMANCE_SENSOR}}, {{RECIPE_BOOK}}, {{SUPPLEMENT_DAILY}}

**NovoDaily Beauty+ (subscription)** (AVAILABLE)
Contains: {{BEAUTY_SENSOR}}, {{COSMETICS_DAY_NIGHT_95ML}}

**NovoDailies+ (supplement-only sub)** (AVAILABLE)
Contains: {{SUPPLEMENT_DAILY}}

**NovoShapies+ (supplement-only sub)** (AVAILABLE)
Contains: {{SUPPLEMENT_WEIGHT}}

**NovoBeauties+ (cosmetics sub)** (AVAILABLE)
Contains: {{COSMETICS_DAY_NIGHT_95ML}}

**NovoLotion+ (cosmetics sub)** (AVAILABLE)
Contains: {{COSMETICS_BODY_LOTION_235ML}}

**NovoDaily Nutrition (standalone)** (AVAILABLE)
Contains: {{NUTRITION_SENSOR}}

**NovoDaily Detox (standalone)** (AVAILABLE)
Contains: {{TOXO_SENSOR}}

**NovoDaily Burnout (standalone)** (AVAILABLE)
Contains: {{BURNOUT_SENSOR}}

**NovoDaily Biological Age (standalone)** (AVAILABLE)
Contains: {{BIOLOGICAL_AGE_SENSOR}}

**NovoDaily Drug Response** (AVAILABLE)
Contains: {{PHARMACO_SENSOR}}

**NovoDaily Allergy** (AVAILABLE)
Contains: {{ALLERGY_SENSOR}}

**NovoDaily Food Intolerance** (AVAILABLE)
Contains: {{FOOD_INTOLERANCE_SENSOR}}

**NovoDaily Metabolism** (AVAILABLE)
Contains: {{METABOLISM_SENSOR}}

**NovoDaily Newborn Screening** (AVAILABLE)
Contains: {{BABY_SENSOR}}

**NovoDaily Just Performance** (AVAILABLE)
Contains: {{JUST_PERFORMANCE}}

**NovoDaily Expert Prevention (doctors only)** (AVAILABLE)
Contains: {{EXPERT_PREVENTION}}

**NovoDaily Expert Fertility (doctors only)** (AVAILABLE)
Contains: {{FERTILITY_SENSOR}}

**NovoDaily Expert Pregnancy (doctors only)** (AVAILABLE)
Contains: {{PREGNANCY_SENSOR}}

**NovoDaily Expert Multi Cancer Sensor (doctors only)** (AVAILABLE)
Contains: {{MULTI_CANCER_SENSOR}}

**NovoDaily Heart & Metabolic Check** (AVAILABLE)
Contains: {{BLOOD_PANEL_HEART_METABOLIC}}

**NovoDaily Hormone Check (Female)** (AVAILABLE)
Contains: {{BLOOD_PANEL_HORMONES_FEMALE}}

**NovoDaily Hormone Check (Male)** (AVAILABLE)
Contains: {{BLOOD_PANEL_HORMONES_MALE}}

**NovoDaily Nutrient Check** (AVAILABLE)
Contains: {{BLOOD_PANEL_NUTRIENTS}}

**NovoDaily Inflammation Check** (AVAILABLE)
Contains: {{BLOOD_PANEL_INFLAMMATION}}

**NovoDaily Longevity Check (Base)** (AVAILABLE)
Contains: {{BLOOD_PANEL_LONGEVITY_BASE}}

**NovoDaily Longevity Hormones (Female)** (AVAILABLE)
Contains: {{BLOOD_PANEL_LONGEVITY_HORMONES_FEMALE}}

**NovoDaily Longevity Hormones (Male)** (AVAILABLE)
Contains: {{BLOOD_PANEL_LONGEVITY_HORMONES_MALE}}

**NovoDaily Hormone Female Sensor** (AVAILABLE)
Contains: {{HORMONE_FEMALE_SENSOR}}

**NovoDaily Hormone Male Sensor** (AVAILABLE)
Contains: {{HORMONE_MALE_SENSOR}}


---

# PART C — ONBOARDING & PARTNERSHIP MODEL

## Partnership Tiers

### Small reseller — uses {{COMPANY_NAME}}'s own brand (NovoDaily)

Small resellers that want to distribute {{COMPANY_NAME}}'s genetic tests and supplements without building their own brand use the NovoDaily turnkey channel. The reseller refers customers to NovoDaily-branded products via novodaily.com or its own NovoPilot-platform account. Minimal setup overhead; standardised products and customer experience.

### Branded reseller — own brand under partner labelling

Branded resellers want their own labels on the products. {{COMPANY_NAME}} produces personalised supplements and cosmetics under the partner's brand, with custom packaging, copy, and report design. Higher setup overhead; deeper differentiation in the partner's market.

### B2B integration partner — embedded in partner platform

The partner integrates {{COMPANY_NAME}} as a backend service in their own platform — typically medical platforms (NovoMedic-style), large-pharmacy chains, or corporate health programs. API integration, white-label fulfilment, sometimes custom analysis configurations.

---

## Onboarding Steps

### Initial scoping

Confirm target market, expected volume, integration model, branding preferences, language requirements, and timeline. Pilot vs full launch is decided at this stage.

### Reseller Identity File creation

For every reseller, a Reseller Identity Markdown file is created (template available in the system). This defines: reseller name, region, language, brand and product name overrides, available products and packages, terminology overrides, and reseller-specific commercial rules.

### Product availability matrix

For every reseller, a Product Availability spreadsheet is created mirroring the structure of NovoDaily Product Availability.xlsx — each variable token marked AVAILABLE, COMING SOON, or NOT OFFERED. This drives which chatbot KB files load for that reseller.

### Chatbot setup (if applicable)

If the reseller is offering a chatbot to their customers, the tenant folder is provisioned under AI CHAT BOTS / <tenant> / with a KNOWLEDGE FILES directory, a tenant-specific master_prompt.txt, and the reseller-specific identity + availability files.

### Pilot phase

A 200–500 customer pilot validates end-to-end flow before scaling. Pilot pricing is structured to be accessible. The pilot also exercises the reseller's customer support process.

### Scale-up

Once the pilot succeeds, scale-up follows the reseller's commercial plan. Capacity planning is collaborative — large planned ramp-ups need notice for production capacity allocation.

---

## What {{COMPANY_NAME}} Provides

### Laboratory and production

Saliva collection devices, laboratory analysis, supplement and cosmetics production at Eugendorf. ISO 9001, ISO 22000, ISO 22716, CLIA, Austrian medical-genetics authorisation included.

### Reports and digital experience

Personalised report generation (digital PDF and printed book), customer-portal access for results, food list, and dashboard. Optional chatbot trained on customer-specific results.

### Brand customisation

For branded resellers: packaging, label design, report design, portal branding. Custom domains and chatbot personalities are configurable.

### Partner support

Account manager, training material for the reseller's own sales staff (the Sales Guidelines file), and access to the {{COMPANY_NAME}} science team for complex customer questions.

---

## What the Reseller Provides

### Customer acquisition

Reseller is responsible for marketing and customer acquisition. {{COMPANY_NAME}} does not run end-customer marketing for branded resellers (and for NovoDaily-branded resellers, NovoDaily Marketing handles the brand campaigns centrally).

### Customer support — front line

Reseller handles first-line customer support. {{COMPANY_NAME}} supports second-line for laboratory or formulation questions. Customer-support routing is established at onboarding.

### Compliance for advertising

Reseller is responsible for advertising compliance in their market. The Advertising Rules & Legal Guidelines file is provided as guidance; legal responsibility remains with the reseller.

### Volume commitments

For at-scale partners, volume commitments are documented in the master partnership agreement. Capacity allocation depends on these commitments — partners with firm commitments get priority in expansion-phase capacity.

---

## Commercial Structure

### Pricing tiers

B2B prices to resellers are tiered by volume. Pricing is published per reseller in dedicated documents (not in this file). The PRODUCT MASTER MATCHING.xlsx tracks naming and availability per reseller but deliberately excludes pricing.

### Margin sharing

Reseller margin is built into the difference between {{COMPANY_NAME}}'s B2B price and the reseller's retail price. Specific structures (flat margin, tier-discount, revenue-share) are agreed per partner.

### Payment terms

Standard payment terms vary by partner type and historical track record. Initial partners typically operate on shorter terms which extend with established performance.

---

## When a Reseller Receives a Cease-and-desist Warning

### Immediate action

The reseller should immediately notify {{COMPANY_NAME}}. {{COMPANY_NAME}} provides support — including reviewing the contested statement, providing scientific backing where applicable, and connecting the reseller with legal expertise where useful. The reseller remains the legally responsible party for advertising content, but does not handle the response alone.

---

## Downloadable Resources — Part C (Onboarding & Partnership)

- [NovoDaily Reseller-Web-Übersicht (PDF, DE)](https://raw.githubusercontent.com/Novogenia/novogenia-chatbot-assets/main/partner-docs/D1_NovoDaily_reseller_web.pdf)
- [NovoDaily Partner-Web-Übersicht (PDF, DE)](https://raw.githubusercontent.com/Novogenia/novogenia-chatbot-assets/main/partner-docs/D2_NovoDaily_partner_web.pdf)
- [Richtlinien Vertriebsaktivitäten (PDF, DE)](https://raw.githubusercontent.com/Novogenia/novogenia-chatbot-assets/main/partner-docs/D3_Richtlinien_Vertriebsaktivitaeten.pdf)
- [Rechtliche Leitlinien für Werbung (PDF, DE)](https://raw.githubusercontent.com/Novogenia/novogenia-chatbot-assets/main/partner-docs/D4_Rechtliche_Leitlinien_Werbung.pdf)

---

# PART D — PARTNER TRAINING (3 Skillbooks)

## Overview

### Three Skillbooks, three skill layers

- **Skillbook 1 — Der richtige Start** (Right Start): mindset, intention, professionalism, voice & body language, sparking curiosity. The internal-state work before any sales conversation.
- **Skillbook 2 — Überzeugende Unterhaltungen** (Persuasive Conversations): the actual conversation craft — 70/30 listening, building trust, eye-level conversations, Instant Influence, objection handling, decision leadership.
- **Skillbook 3 — Leadership & Teamaufbau** (Leadership & Team Building): for partners who are building their own downline — mission clarity, empathy leadership, duplication, coaching, objection handling at the team level.

### How the bot should use them

When a reseller asks "how do I start a sales conversation", "how do I handle objection X", "how do I build my team" — pull the matching chapter principle from below and cite the Skillbook + chapter as the source for deeper reading.

---

## Skillbook 1 — Der richtige Start

### 01 — Wähle Deine Absicht (Choose your intention)

Menschen hören deine Worte. Aber sie *fühlen* deine Absicht. Wenn die Haltung stimmt — echtes Interesse, Respekt, die Freiheit "Nein" zu sagen — öffnen sich Türen. Verkaufen ist kein Trick. Es ist ein Rahmen: informiere, inspiriere, lass entscheiden.

**Quote:** "Absicht zählt mehr als Technik." — Mahan Khalsa.

**Das Absichts-Ritual in 3 Schritten:**
1. Formuliere deine Gesprächsabsicht in einem Satz: "Ich will verstehen, was dir wichtig ist — und ob NovoDaily dir helfen kann."
2. Starte stets positiv: "Das klingt spannend …" / "Lass uns das mal sortieren …" / "Wir gehen das Schritt für Schritt …"
3. Mach's zum Ritual: Lies deinen Absichts-Satz laut vor jedem Gespräch.

**Sprachhebel:** "Herausforderung" statt "Problem". "Wir schaffen das" statt "das ist schwer". Dean Graziosi: "It's not what you say, it's how you make people feel."

### 02 — Selbstverantwortung ohne Selbstgeißelung (Self-responsibility without self-flagellation)

Take responsibility for the conversation outcome without blaming yourself when one goes poorly. Reflect, adjust, move on.

### 03 — Professionalität (Professionalism)

The expected baseline of pre-, during-, and post-conversation conduct.

### 04 — Stimme & Körpersprache als Werkzeug (Voice & body language as a tool)

Voice tone and body language carry more weight than the content. Calm, even tempo, eye contact, open posture.

### 05 — Menschen für eine Unterhaltung gewinnen: Neugier wecken (Spark curiosity)

The opening move: don't pitch. Spark curiosity with a question or a one-line observation that makes the listener want to know more. "Did you know that the same supplement can be ideal for one person and counter-productive for another? It's in the genes."

---

## Skillbook 2 — Überzeugende Unterhaltungen

### 01 — Warum langsam schneller ist (Why slow is faster — the 70/30 rule)

Dein Ziel: 70 % dein Gegenüber, 30 % du. Langsam ist schneller — weil du durch Zuhören die wahren Bedürfnisse und Blockaden entdeckst. Wer redet, lernt nichts Neues. Wer zuhört, gewinnt.

**Quote:** "Das Einzige, was interessant ist, ist die Empfangsgeschwindigkeit und die Verarbeitungsgeschwindigkeit beim Gegenüber." — Markus Eilers.

**Werkzeuge:**
- 5 offene Fragen im Arsenal — z.B.: "Was ist dir bei deiner Gesundheit gerade am wichtigsten?"
- Die Macht der Stille: 7 Sekunden Pause nach einer wichtigen Frage. Halte sie aus — wer zuerst redet, verliert.
- 30%-Challenge: Führe ein Gespräch, in dem du bewusst unter 30 % Redeanteil bleibst.

### 02 — Die Geschwindigkeit des Vertrauens (Speed of trust)

Vertrauen ist die Währung jeder Beziehung. Ohne Vertrauen keine ehrlichen Antworten, keine Offenheit, keine Entscheidung. Vertrauen entsteht nicht durch Kompetenz — es entsteht durch *Empathie*.

**Quote:** "Vertrauen wird Tropfen für Tropfen aufgebaut und Eimerweise zerstört." — Kevin Plank.

**Kompetenz öffnet Türen. Empathie öffnet Menschen.** Zeig zuerst, dass du verstehst — bevor du erklärst, was du weißt.

### 03 — Gespräche auf Augenhöhe (Eye-level conversations)

Keine Hierarchie zwischen Verkäufer und Kunde. Du bist ein Berater, dein Gegenüber ist Experte für sein Leben.

### 04 — Neugier — Vertrauen — Klarheit: Instant Influence Kurzvorstellung

Die Mini-Pitchstruktur: erst Neugier wecken, dann Vertrauen aufbauen, dann Klarheit schaffen über das Angebot. Niemals umgekehrt.

### 05 — Einwände vorwegnehmen (Pre-empt objections)

Wenn du einen häufigen Einwand kennst (z.B. "Das ist teuer"), bring ihn selbst zur Sprache, bevor der Kunde es tut. Das nimmt ihm die Energie. "Du wirst dich vielleicht fragen, warum das im Vergleich zu Drogerie-Vitaminen mehr kostet …"

### 06 — Einwandbehandlung mit Empathie und Klärungsfragen

Statt "Aber …" antworten: zuerst spiegeln ("Ich verstehe, dass …"), dann klären ("Was genau meinst du damit?"), dann gemeinsam eine Lösung suchen. Keine Verteidigungshaltung.

### 07 — Entscheidungsführung statt Warteschleifen (Decision leadership, not parking-orbits)

Führe das Gespräch zu einer Entscheidung — Ja, Nein, oder ein klares "Lass uns am Tag X nochmal sprechen, wenn Y geklärt ist". Niemals "Lass mich da nochmal drüber nachdenken" ohne nächsten Schritt akzeptieren.

### 08 — Diskomfort aushalten (Hold the discomfort)

Schweigen, Druck, peinliche Pausen — wer das aushält, ohne reflexhaft zu reden, gewinnt das Gespräch.

---

## Skillbook 3 — Leadership & Teamaufbau

### 01 — Klarheit schaffen wie Ocean's Eleven (Mission clarity)

Als Führungskraft ist deine wichtigste Aufgabe: **Mach die Mission so klar, dass jeder seine Rolle kennt und versteht, wie sein Beitrag zum großen Ganzen passt.**

**Quote:** "Klarheit ist Güte." — Brené Brown.

**Die 3 Säulen der Klarheit:**
1. **Mission (Warum):** "Wir sind hier, um 5 Millionen Europäer an dieser Gelegenheit auf ein gesünderes, besseres und energievolleres Leben teilhaben zu lassen."
2. **Ziel (Was):** Ein klares, messbares Ergebnis. Z.B.: "Jeder in diesem Team wird Rising Star in den nächsten 90 Tagen."
3. **Plan (Wie):** Die konkreten Schritte. Z.B.: "Jeder macht 10 Kontakte pro Tag."

**Klarheits-Check:** Frage jeden Partner einzeln: "Was ist unser wichtigstes Ziel für dieses Quartal?" Wenn die Antworten unterschiedlich sind, fehlt Klarheit.

### 02 — Empathie als Führungs-Superkraft (Empathy as leadership superpower)

Führung ist keine Position. Führung ist eine *Beziehung*. Dein Team folgt dir, weil es dir vertraut.

**Quote:** "Die Leute werden vergessen, was du gesagt hast. Sie werden vergessen, was du getan hast. Aber sie werden nie vergessen, wie sie sich durch dich gefühlt haben." — Maya Angelou.

Empathie ist kein "Soft Skill" — sie ist ein knallharter Business-Faktor. Sie reduziert Fluktuation, steigert die Moral, führt zu besseren Ergebnissen.

### 03 — Duplikation

Was du machst, müssen deine Partner replizieren können. Wenn du etwas tust, das nicht reproduzierbar ist, lehrst du keinem etwas — du machst eine One-Person-Show.

### 04 — Coaching-Fähigkeiten für deine Partner-Entwicklung

Coach statt Manager. Frage statt sage. Lass den Partner die Antwort finden.

### 05 — Einwände & Neuausrichtung für Führungskräfte

Wenn ein Partner Einwände hat ("Das funktioniert bei mir nicht"), nicht überzeugen — neu ausrichten. Was hat sich geändert? Was braucht der Partner jetzt anders?

---

## Recurring threads across all three Skillbooks

### Intent before technique

Jede Technik versagt, wenn die Absicht falsch ist. "Absicht zählt mehr als Technik." (S1). "Empathie öffnet Menschen." (S2). "Klarheit ist Güte." (S3). Der innere Zustand entscheidet, ob die Methoden funktionieren.

### Listening over telling

70 % Gegenüber, 30 % du (S2). "Was brauchst du?" als Führungsfrage (S3). "Was ist dir gerade am wichtigsten?" als Eröffnung (S1+S2).

### Specific over vague

Konkrete Zahlen: 10 Kontakte pro Tag, 90 Tage zum Rising Star, 7 Sekunden Pause, 30 % Redeanteil. Nicht "mehr verkaufen" sondern "10 Kontakte pro Tag". Nicht "freundlich sein" sondern "Empathie als knallharter Business-Faktor".

### People feel intent before they hear words

Wiederkehrend in allen drei Skillbooks: Menschen filtern alles durch die Frage "Kann ich diesem Menschen vertrauen?" Erst wenn das mit Ja beantwortet ist, öffnet sich Raum für echte Gespräche.

---

## Standard authors / quotes pool

Tony Robbins, Mahan Khalsa, Dean Graziosi, Stephen R. Covey, Markus Eilers, Kevin Plank, Brené Brown, Maya Angelou, plus the African proverb "Wenn du schnell gehen willst, geh allein. Wenn du weit kommen willst, geh gemeinsam." — used in S3 opening.

---

## Downloadable Resources — Part D (Skillbooks)

- [Skillbook 1 — Der richtige Start (PDF, DE)](https://raw.githubusercontent.com/Novogenia/novogenia-chatbot-assets/main/skillbooks/E1_Skillbook_1_richtiger_Start.pdf)
- [Skillbook 2 — Überzeugende Unterhaltungen (PDF, DE)](https://raw.githubusercontent.com/Novogenia/novogenia-chatbot-assets/main/skillbooks/E2_Skillbook_2_Unterhaltungen.pdf)
- [Skillbook 3 — Leadership & Teamaufbau (PDF, DE)](https://raw.githubusercontent.com/Novogenia/novogenia-chatbot-assets/main/skillbooks/E3_Skillbook_3_Leadership.pdf)

## When to refer a reseller to which Skillbook

| Reseller question | Recommend |
|---|---|
| "Ich bin neu, wo fange ich an?" | Skillbook 1 — Der richtige Start (Kap. 01 + 03) |
| "Wie eröffne ich ein Gespräch?" | Skillbook 1 Kap. 05 + Skillbook 2 Kap. 04 |
| "Mein Kunde sagt ständig 'Ich überleg's mir'" | Skillbook 2 Kap. 07 (Entscheidungsführung) |
| "Mein Kunde hat einen Einwand gegen den Preis" | Skillbook 2 Kap. 05 + 06 |
| "Mein Team performt nicht" | Skillbook 3 Kap. 01 (Klarheit) |
| "Ein Partner droht abzuspringen" | Skillbook 3 Kap. 02 + 05 |
| "Wie repliziere ich, was ich tue?" | Skillbook 3 Kap. 03 (Duplikation) |
