# 3-Tier FAQ-Struktur — Konventionen + Lookup-Logik
<!--
  PURPOSE: Standardisiert wo FAQ-Inhalte liegen, wie sie gehedert sind, und in welcher Reihenfolge der Bot sie sucht.
  QUELLE: Mobile-Sparring-Briefing 2026-06-03 Teil 1.5.
  STATUS: Architektur-Spec für künftige FAQ-Files. Bestehende FAQ-Files werden schrittweise migriert.
-->

---

## Die drei Tiers

### Tier 1 — Produkt-FAQ

**Ort:** Bei der Produkt-Datei oder im Produkt-Ordner.
**Naming-Konvention:** `FAQ - [PRODUCT_TOKEN].md` (z.B. `FAQ - NUTRITION_SENSOR.md`).
**Inhalt:** Fragen die SPEZIFISCH zu einem Produkt gehören.

Beispiele:
- „Wie oft muss ich den NovoDaily Shape Test wiederholen?" → FAQ - WEIGHT_SENSOR
- „Was kostet eine Nachbestellung von NovoDailies?" → FAQ - SUPPLEMENT_DAILY
- „Wie genau ist der Beauty Sensor?" → FAQ - BEAUTY_SENSOR

**Header-Pflicht:**
```yaml
REQUIRES_VARIABLE: {{PRODUCT_TOKEN}}
TIER: product
PRODUCT: PRODUCT_TOKEN
```

### Tier 2 — Generelle FAQ

**Ort:** `01_END_CUSTOMER_UNIVERSAL/` (immer geladen, produkt-übergreifend).
**Naming-Konvention:** `FAQ - [TOPIC].md` (z.B. `FAQ - General Technology & Science.md`, `FAQ - Subscription & Delivery.md`).
**Inhalt:** Themen die produkt-übergreifend gelten und für alle Reseller gleich sind.

Beispiele:
- „Wie funktioniert ein DNA-Test grundsätzlich?" → FAQ - General Technology & Science
- „Wie lange dauert es vom Probenversand bis zum Ergebnis?" → FAQ - Sample Collection & Process
- „Was passiert mit meiner DNA-Probe nach der Analyse?" → FAQ - General Technology & Science

**Header-Pflicht:**
```yaml
REQUIRES_VARIABLE: (none — always loaded)
TIER: general
TOPIC: [topic-name]
```

### Tier 3 — Reseller-spezifische FAQ

**Ort:** `10_RESELLER_BRANDED__NOVODAILY/` (oder analog im jeweiligen Reseller-Ordner).
**Naming-Konvention:** `FAQ - [Reseller] [Topic].md` (z.B. `FAQ - NovoDaily Subscription.md`, `FAQ - NovoDaily Customer Portal.md`).
**Inhalt:** Reseller-spezifische Antworten — Preise, Versand-Partner, Kündigungs-Regeln, Plattform-Bedienung etc.

Beispiele:
- „Wie kündige ich mein NovoDaily Lifestyle+ Abo?" → FAQ - NovoDaily Subscription
- „Mit welchem Versandpartner liefert NovoDaily?" → FAQ - NovoDaily Versand
- „Wo finde ich meine NovoDaily-Berichte?" → FAQ - NovoDaily Customer Portal

**Header-Pflicht:**
```yaml
REQUIRES_VARIABLE: (none — reseller-specific, always loaded for this tenant)
TIER: reseller
RESELLER: NovoDaily
```

---

## Lookup-Reihenfolge (Bot-Such-Logik)

Wenn ein Nutzer eine Frage stellt, sucht der Bot in dieser Reihenfolge:

1. **Tier 1 — Produkt-FAQ** zuerst (wenn ein Produkt im Kontext identifiziert ist)
2. **Tier 2 — Generelle FAQ** zweitens (allgemeine Themen)
3. **Tier 3 — Reseller-FAQ** drittens (reseller-spezifische Details)

**Warum diese Reihenfolge:** Reseller-spezifische Antworten sind oft kürzer und spezifischer (Kündigungsregeln, Preise), aber sie überschreiben nicht die zugrunde liegende Wissenschaft. Produkt-FAQ ist immer das spezifischste fachlich, Tier 2 erklärt das Grundsätzliche, Tier 3 macht's reseller-konkret.

**Konflikt-Auflösung:** Bei Widerspruch zwischen Tiers gilt **immer Tier 3 (Reseller) > Tier 1 (Produkt) > Tier 2 (Generell)**. Reseller-Konfig überschreibt Default, sonst macht die Tier-Trennung keinen Sinn.

**Beispiel-Konflikt:**
- Tier 2 (Generell) sagt: „Mindestlaufzeit für Subscriptions ist 12 Monate."
- Tier 3 (NovoDaily) sagt: „NovoDaily Lifestyle+ Mindestlaufzeit ist 12 Monate, NovoDaily Performance+ ist 15 Monate."
→ Bot nutzt Tier-3-Werte (spezifischer), zitiert Reseller als Quelle.

---

## Themen-Zuordnung — was gehört in welchen Tier?

Diese Tabelle definiert wo häufige FAQ-Themen hingehören. Bei Unsicherheit ist Tier 2 die Default-Wahl (allgemein), Tier 3 nur wenn reseller-spezifisch.

| Thema | Tier | Begründung |
|---|---|---|
| Wissenschaft eines Sensors / Was wird gemessen | 1 (Produkt) | Produkt-spezifisch |
| Wie lese ich mein Ergebnis im Kapitel X | 1 (Produkt) | Produkt + Kapitel |
| DNA-Test grundsätzlich erklärt | 2 (Generell) | Produkt-übergreifend |
| Sample Collection / Speichelprobe | 2 (Generell) | Produkt-übergreifend |
| Privacy / Datenschutz allgemein | 2 (Generell) | Wissenschaftliche Basis |
| Subscription-Mindestlaufzeit konkret | 3 (Reseller) | Pro Reseller anders |
| Kündigung / Pause Workflow | 3 (Reseller) | Pro Reseller anders |
| Versand-Zeiten / Versandkosten | 3 (Reseller) | Pro Reseller anders |
| Login zur Customer-Plattform | 3 (Reseller) | Pro Reseller anders (eigenes Portal) |
| Refund-Regeln | 3 (Reseller) | Pro Reseller anders |
| Preisanfrage | 3 (Reseller) | Pro Reseller anders |
| Kit-Versand / Sample-Return | 3 (Reseller) | Pro Reseller (Versanddienstleister) |
| Was sind Microtransporter | 2 (Generell) | Produkt-übergreifende Technologie |
| Welcher Test passt für Diabetes-Vorsorge | 2 (Generell) | Produkt-Empfehlung (kann tier-1 sein wenn ein konkretes Produkt) |
| Vergleich Lifestyle+ vs Shape+ vs Beauty+ | 3 (Reseller) | Bundle-Namen + Preise reseller-spezifisch |

---

## Klassifikations-Heuristik (für die Pflege)

**Frage:** Würde sich die Antwort ändern wenn ein anderer Reseller den selben Bot fragt?
- Nein → Tier 2 (Generell)
- Ja, weil Reseller A das Produkt anders nennt / anders verkauft → Tier 3 (Reseller)
- Ja, weil's um ein spezifisches Produkt geht → Tier 1 (Produkt)

**Frage:** Bezieht sich die Antwort auf ein konkretes Produkt?
- Ja, ausschließlich → Tier 1
- Ja, aber gilt auch für andere → Tier 2 mit Verweis auf Tier 1
- Nein, produkt-übergreifend → Tier 2 oder Tier 3

---

## Migrations-Strategie für bestehende FAQ-Files

Aktueller Stand: 73 KB-Files sind im Tenant, viele haben „FAQ" im Namen aber sind noch nicht systematisch ge-tiered. Migration in 3 Wellen:

**Welle 1 — Reseller-spezifisch (höchste Priorität):**
Identifiziere Files in `10_RESELLER_BRANDED__NOVODAILY/` die reseller-spezifische Antworten enthalten und gib ihnen TIER: reseller Header.

**Welle 2 — Produkt-FAQ:**
In `02_LIFESTYLE_GENETICS/`, `07_SUPPLEMENTS/`, `03_BLOOD_ANALYSES/` etc. — alle „FAQ - PRODUCT_TOKEN.md" mit TIER: product Header versehen.

**Welle 3 — Generell:**
In `01_END_CUSTOMER_UNIVERSAL/` — alle übrigen FAQs als TIER: general kennzeichnen.

**Wann durchführen:** Nicht jetzt. Sobald die nächste KB-Restruktur ansteht (Phase C im Sequencing-Plan).

---

## Cross-Reference Beispiel

So sollte eine gute FAQ-Antwort referenzieren:

> Nutzer: „Wie lange dauert es bis ich meinen NovoDaily Lifestyle+ Bericht bekomme?"
>
> Bot (intern):
> 1. Tier 1 Lookup: FAQ - WEIGHT_SENSOR (Bericht-Erstellung) → 4–6 Wochen nach Sample-Eingang
> 2. Tier 2 Lookup: FAQ - Sample Collection & Process → bestätigt: Labor-Durchlaufzeit
> 3. Tier 3 Lookup: FAQ - NovoDaily Versand → Sample-Eingang typisch 3–5 Tage nach Versand-Aufgabe
>
> Bot-Antwort: „Vom Versand des Speichel-Kits bis zum fertigen Bericht sind rund 5–7 Wochen — der Versand zum Labor dauert 3–5 Tage, die Analyse selbst 4–6 Wochen, plus die Generierung deines persönlichen Berichts."

Statt einer einzigen Quelle synthetisiert der Bot aus allen drei Tiers.
