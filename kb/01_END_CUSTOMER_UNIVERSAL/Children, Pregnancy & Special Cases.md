# Children, Pregnancy & Special Cases
<!--
  REQUIRES_VARIABLE: (none — always loaded)
  PURPOSE: How to handle non-standard customer situations: children, pregnancy, medications, surgery, chronic conditions.
  VARIABLES: Product names use {{VARIABLE}} tokens defined in the reseller's Profile file (Part A) — e.g. 10_RESELLER_BRANDED__NOVODAILY/NovoDaily Reseller Profile.md.
-->

---

## Children

### Can children take {{SUPPLEMENT_DAILY}}?

{{SUPPLEMENT_DAILY}} is not suitable for children under 13 years of age. The formulation is calibrated for adult metabolism and adult body weight ranges. For supplementation in children under 13, parents should follow paediatric guidance rather than a personalised adult product.

### Can children have a DNA analysis?

{{WEIGHT_SENSOR}} can be performed on children, but without calorie calculations, ideal-weight estimates, menu options, or {{RECIPE_BOOK}} — these calculations are not meaningful for fast-growing children. The {{RECIPE_BOOK}} is locked for children under 14. Other DNA analyses (e.g. {{NUTRITION_SENSOR}}) are generally appropriate from a similar age and produce informational reports without prescriptive dosing.

### Newborn screening

For newborns, the {{BABY_SENSOR}} analysis screens for 111 relevant genetic conditions. This is a separate product from the adult lifestyle analyses and follows a special sample-handling protocol.

---

## Pregnancy

### Should pregnant customers continue {{SUPPLEMENT_DAILY}}?

During pregnancy, the priority shifts to the health and development of the embryo. Standardised prenatal supplements specifically formulated to support embryo growth are recommended in this case — not a personalised supplement optimised for the mother's genetics. Stop {{SUPPLEMENT_DAILY}} during pregnancy and follow your doctor's recommendation for a suitable prenatal product. Resume {{SUPPLEMENT_DAILY}} after pregnancy if desired.

### Can pregnant customers have a DNA analysis?

Genetic analyses are safe during pregnancy — they involve only a saliva sample and do not involve any intervention. {{PREGNANCY_SENSOR}} and {{FERTILITY_SENSOR}} (both Expert / doctors-only) are specifically designed to inform clinical decisions during this period.

### Breastfeeding

Breastfeeding customers should also typically pause {{SUPPLEMENT_DAILY}} or consult their doctor before continuing. The standard "breastfeeding-safe" supplement is the safer default during this phase.

---

## Medications

### Drug interactions with {{SUPPLEMENT_DAILY}}

{{SUPPLEMENT_DAILY}} is designed to simulate the effect of a healthy, optimised diet — it contains the same nutrients found in food, just in personalised form. Drug interactions are not known and have not been reported. Customers on multiple medications can share their supplement formulation with their doctor; the report includes exact ingredients and dosages.

### When the customer should pause supplement use

Before colonoscopy: discontinue {{SUPPLEMENT_DAILY}} approximately one week before the procedure to allow the intestine to clear of {{PELLET_NAME}} beads. Before surgery: follow the surgeon's general supplement-pause guidance, which usually means stopping all non-essential supplements a week before. Acute illness: continue is generally fine unless the doctor advises otherwise; severe gastrointestinal illness may make absorption unreliable.

### Conflicting medication-supplement interactions

For specific concerns, the customer should share their formulation with their doctor. {{PHARMACO_SENSOR}} results may also be relevant — they reveal how the customer metabolises various drug classes.

---

## Chronic Conditions

### Diabetes

Diabetic customers can generally use {{SUPPLEMENT_DAILY}} — the supplement contains no sugar and the dosing is calibrated to avoid exceeding EFSA upper limits. Customers should still share their formulation with their endocrinologist.

### Cardiovascular conditions

Customers with cardiovascular conditions can typically use {{SUPPLEMENT_DAILY}}. Cardiologist-prescribed medications take precedence over any supplement-derived guidance; the customer should discuss the supplement formulation with their cardiologist if they are on multiple cardiac drugs.

### Autoimmune conditions

Customers with autoimmune conditions can usually use {{SUPPLEMENT_DAILY}}. If they are on immunosuppressants or biologics, sharing the formulation with their treating physician is recommended.

### Kidney conditions

Customers with reduced kidney function should consult their nephrologist before using {{SUPPLEMENT_DAILY}} or any concentrated supplement. Some minerals require functional renal clearance; dose adjustments may be needed.

---

## Vegan and Vegetarian Customers

### Vegetarian status of {{SUPPLEMENT_DAILY}}

{{SUPPLEMENT_DAILY}} is suitable for vegetarians. Beeswax is used as a pellet coating, so the product is not certified vegan in its default form. Customers who require a fully vegan profile should request the lichen-derived Vitamin D3 (instead of lanolin-derived) — done automatically where genetically indicated and adjustable on request.

### Vegan status of {{SUPPLEMENT_WEIGHT}}

{{SUPPLEMENT_WEIGHT}} is suitable for both vegetarians and vegans. Both active ingredients (OFI fibre and Phaseolamin) are fully plant-based.

### Vegan diet considerations

Vegan diets often require additional attention to Vitamin B12, Vitamin D3, iron, omega-3 (algae-derived), and zinc. The {{NUTRITION_SENSOR}} and {{SUPPLEMENT_DAILY}} algorithm flag these as a matter of course where the lifestyle questionnaire indicates vegan diet.

---

## Older Customers

### Is there an age limit?

There is no upper age limit. Many older customers benefit substantially from personalised supplementation because nutrient absorption efficiency declines with age and many older adults are on multiple medications — making accurate baseline nutrient status particularly important. {{PHARMACO_SENSOR}} is often especially useful for this group.

### Reformulation with age

The supplement reformulation algorithm adjusts dosing based on the customer's current age at each reorder. This is one reason the quarterly reformulation cycle exists — the same person at 45 and at 75 needs different dosing even though their genes are identical.
