# NOVO ACADEMY — Training Catalog
<!--
  REQUIRES_VARIABLE: (none — always loaded)
  PURPOSE: Catalog of the training courses available to {{COMPANY_NAME}} partners and resellers via the
           NOVO ACADEMY platform. The bot can refer resellers to specific courses and modules when they
           ask about education, certifications, or where to deepen their knowledge.
  PLATFORM: React/Vite single-page app with admin backend, certifiable courses, FAQ collections,
            and PowerPoint training decks. Hosted as a separate property; ask reseller for current URL.
-->

---

## Overview

### What NOVO ACADEMY is

NOVO ACADEMY is the dedicated training platform {{COMPANY_NAME}} provides to partners and resellers. Each course is structured as a sequence of modules with course content (videos, PowerPoint decks, PDFs, transcripts) followed by a test. Successful completion of all modules in a category produces a downloadable certificate.

### Who it is for

The academy is primarily reseller-facing — nutritionists, fitness trainers, health practitioners, pharmacies, gyms, and other professionals who advise their own customers using {{COMPANY_NAME}} products. End customers do not generally access the academy.

### How the platform is organised

Each top-level "category" maps to a {{COMPANY_NAME}} product area. Inside the category, modules are numbered (01, 02, 03 …) and proceed from scientific foundation through consultation training, product presentation, objection handling, and frequently asked questions.

---

## Course catalog

### Category 1 — Die Gen-Diät (The Gene Diet)

Maps to {{WEIGHT_SENSOR}} and {{SUPPLEMENT_WEIGHT}}. Five modules:

- **01 — Wissenschaftliche Basis (Scientific Basis):** How genes control body weight — the foundational science of weight-relevant genes (FTO, PPARG, ADRB2/3, FABP2, APOA2, APOA5), nutritional type, hunger / satiety, fat distribution.
- **02 — Beratungsschulung (Consultation Training):** How to structure a weight-management consultation around the customer's genetic profile.
- **03 — Produktpräsentation (Product Presentation):** How to present {{WEIGHT_SENSOR}}, the {{NUTRITION_SENSOR}} Nutrition Plan, and {{SUPPLEMENT_WEIGHT}} to a customer.
- **04 — Einwandsbehandlung (Objection Handling):** Common customer objections in weight conversations and how to answer them.
- **05 — Häufige Fragen (Frequent Questions):** A curated FAQ block for this category (no test).

### Category 2 — Genetik der gesunden Ernährung (Healthy Nutrition Genetics)

Maps to {{NUTRITION_SENSOR}}. Five modules:

- **01 — Das wissenschaftliche Prinzip (Scientific Principle):** The foundational science of nutrigenetics — MTHFR, CYP1A2, APOA1, NQO1, VDR, GPX1, AGT, LCT, HFE.
- **02 — Beratungsschulung (Consultation Training):** Consultation flow around a nutrition genetic profile.
- **03 — Produktpräsentation (Product Presentation):** How to present {{NUTRITION_SENSOR}} and the Precision Nutrition Plan.
- **04 — Einwandsbehandlung (Objection Handling):** Common customer objections about nutrition genetics.
- **05 — Häufige Fragen (Frequent Questions):** Curated FAQ block (no test).

### Category 3 — Leistungs-Genetik (Performance Genetics)

Maps to {{PERFORMANCE_SENSOR}} and {{JUST_PERFORMANCE}}. Five modules:

- **01 — Das wissenschaftliche Prinzip (Scientific Principle):** The science of performance genetics — ACTN3, ACE, recovery genes, injury-risk variants, performance-relevant nutrient handling.
- **02 — Beratungsschulung (Consultation Training):** Consultation flow with athletes and active customers.
- **03 — Produktpräsentation (Product Presentation):** How to present the performance line.
- **04 — Einwandsbehandlung (Objection Handling):** Common objections from athletes and trainers.
- **05 — Häufige Fragen (Frequent Questions):** Curated FAQ block (no test).

### Category 4 — Personalisierte Nahrungsergänzung (Personalized Supplements)

Maps to {{SUPPLEMENT_DAILY}} (and by extension {{SUPPLEMENT_WEIGHT}}, {{COSMETICS_DAY_NIGHT_95ML}}, {{COSMETICS_BODY_LOTION_235ML}}). Seven modules — the deepest curriculum:

- **01 — Das genetische Prinzip (Genetic Principle):** Why a single standard supplement cannot fit everyone — the genetic case for personalisation.
- **02 — Personalisierung & Nährstofftechnologie (Personalisation & Nutrient Technology):** The {{PELLET_NAME}} micro-transporter technology, fast / slow release, nutrient separation and pairing.
- **03 — Qualitätskontrolle (Quality Control):** ISO 9001 / 22000 / 22716, CLIA, Austrian medical-genetics authorisation, the 100+ per-batch tests, retention samples, doping-free testing.
- **04 — Produktberatung (Product Consultation):** How to walk a customer through choosing the right combination of analyses and supplements.
- **05 — Produktpräsentation (Product Presentation):** How to present the supplement line in detail.
- **06 — Einwandsbehandlung (Objection Handling):** Common objections about cost, complexity, science, and ingredient sourcing.
- **07 — Häufige Fragen (Frequent Questions):** Curated FAQ block (no test).

---

## Materials per module

### What each course module contains

Course modules typically include: a transcript file (markdown), a PowerPoint deck (PPTX) used in the live or recorded training, downloadable PDFs (demo reports, supporting reference), and any video links keyed to that module's topic. Materials live under `public/course-materials/` in the academy app and total roughly 1.2 GB across all courses.

### What each test module contains

Each numbered module (except 05/07 FAQs) closes with a 5-question multiple-choice test. The current prototype uses a generic 5-question set; subject-specific tests are being added per module. A passing score on every test in a category unlocks the category certificate.

### Course materials available for download

Resellers can download the PowerPoint decks and PDFs from inside the academy for use in their own consultations — for example the "Die Gen-Diät" deck or the demo Nutrition Plan PDF.

---

## Certification

### Certificates and how they work

Each of the four categories produces its own certificate when all of its tests are passed. Certificates are generated as PDFs inside the academy app using a {{COMPANY_NAME}} template and carry the reseller's name, the category title, and the completion date.

### What a certificate proves

A certificate states that the reseller has completed the {{COMPANY_NAME}} training for that category — it confirms product knowledge and consultation training, not medical qualification.

---

## How the bot should use this catalog

### Referring resellers to a course

When a reseller asks "where do I learn more about X" or "is there training on Y", the bot can name the specific category and module (e.g. "Die Gen-Diät · Modul 02 — Beratungsschulung" or "Personalisierte Nahrungsergänzung · Modul 03 — Qualitätskontrolle") and explain what that module covers, then suggest they log into the academy.

### Linking to product conversations

When a reseller asks how to handle a specific objection or sales situation, the bot can refer to the relevant "04 — Einwandsbehandlung" module in the appropriate category.

### Reseller scope only

The academy is a reseller-facing resource. The bot should not direct end customers to it. End customers are pointed to the public materials referenced in `Video References.md` and `Book Reference - Unlock Your Genes.md`.
