# Reseller-Config Schema
<!--
  PURPOSE: Spezifikation aller Reseller-Konfigurations-Flags die das Bot-Verhalten pro Tenant steuern.
           Quelle: Mobile-Sparring-Briefing 2026-06-03 Teil 2.
  AUDIENCE: Engineering (Implementierung backend), Bot-Author (Befüllung pro Tenant), Reseller-Onboarding.
  STATUS: Schema v1. Implementiert aktuell als Sektion im jeweiligen Tenant-Profile-File. Ziel: später als echte Config-Felder.
-->

---

## Geltungsbereich

Diese Spec definiert die Konfigurations-Flags pro NovoDaily-Reseller-Tenant. Jeder Flag steuert ein konkretes Bot-Verhalten. Die Flags ergänzen die bestehende **Product Availability Matrix** (NovoDaily Reseller Profile Part B) und das **Brand & Company Name Overrides** Mapping (Part A).

**Aktuelle Implementierung:** Flags als Markdown-Tabelle im jeweiligen Reseller-Profile-File. Der Bot liest die Flags über RAG-Retrieval.
**Ziel-Implementierung:** echte Config-Felder im Admin-UI mit Validation + UI-Toggles. Migrationspfad: identische Feldnamen, so dass die Tabelle 1:1 ins UI überführt werden kann.

---

## Flag-Liste

### `allow_science_beyond_products`

**Werte:** `true` | `false`
**Default:** `true`
**Wirkung:** Wenn `true`, darf der Bot wissenschaftliche Erklärungen zu Genen / Mechanismen / Studien liefern, auch wenn das zugehörige Produkt beim Reseller NICHT verfügbar ist. Wenn `false`, redirected der Bot Science-Fragen zu nicht-verfügbaren Produkten zurück auf verfügbare Produkte.

**Begründung:** Manche Reseller wollen breite Wissens-Autorität (Vertrauensaufbau), andere wollen Conversion-Fokus (nicht über Produkte reden die sie nicht verkaufen).

**Bot-Verhalten Beispiel:**
- `true` + Kunde fragt zu Multi-Cancer Sensor (nicht im Scope): „Multi Cancer Sensor ist bei NovoDaily Teil der Expert-Linie und läuft über Ärzte — aber zur Wissenschaft kann ich dir trotzdem was sagen…"
- `false` + gleicher Fall: „Multi Cancer Sensor ist bei NovoDaily Teil der Expert-Linie und läuft über Ärzte — wenn du Krebs-Vorsorge interessant findest, schau dir den NovoDaily Biological Age Sensor an, der zeigt deine Zell-Alterungs-Geschwindigkeit als ersten Schritt."

---

### `brand_mode`

**Werte:** `reseller_led` | `novogenia_led`
**Default:** `reseller_led`
**Wirkung:** Steuert Tonalität + Firmen-Erwähnung. Bestimmt WER der Bot ist und welche Firmen-Identität dominiert.

**`reseller_led` (White-Label+):**
- Bot-Identität: „Ich bin der [Reseller]-Chatbot."
- Labor wird als „unser zertifiziertes Partnerlabor" referenziert (kein Novogenia-Name).
- Reseller = Hauptfokus, Novogenia unsichtbar im Hintergrund.
- Geeignet für: Reseller mit starker Eigenmarke (z.B. Hartlauer, Apotheken-Ketten).

**`novogenia_led`:**
- Bot-Identität: „Ich bin der Novogenia-Chatbot, präsentiert von [Reseller]."
- Labor = „Novogenia in Salzburg" — voller Wissenschafts-Kredit.
- Reseller = „trusted Partner, der diese Produkte anbietet".
- Geeignet für: Reseller die von Novogenia-Wissenschafts-Authorität profitieren (z.B. Health-Practitioner-Vermittler, Gym-Trainer).

---

### `founder_visibility`

**Werte:** `none` | `subtle` | `featured`
**Default:** `subtle`
**Wirkung:** Wie prominent Dr. Daniel Wallerstorfer und seine Social-Links im Bot-Verhalten auftauchen.

- **`none`:** Wallerstorfer wird nicht aktiv erwähnt. Wenn direkt gefragt: faktische Antwort, kein Social-Push.
- **`subtle`:** Wallerstorfer wird natürlich in den Wissenschafts-Kontext eingebaut („Dr. Wallerstorfer hat in seinem Buch …"). Social-Links nur auf explizite Frage.
- **`featured`:** Bot empfiehlt aktiv Wallerstorfers Social-Kanäle als Wissens-Quelle („Für tiefere Insights folg ihm auf LinkedIn / Instagram"). Geeignet für Reseller die Wallerstorfers Personal-Brand als Verkaufsanker nutzen.

**Begründung:** Manche Reseller wollen die Personal-Brand als Hebel, andere wollen die Reseller-eigene Brand vorne haben.

---

### `tone_style`

**Werte:** `du` | `sie`
**Default:** `du`
**Wirkung:** Anredeform im Deutschen. Im Englischen kein Unterschied (immer „you").

- **`du`:** Kollegial, freundlich, persönlich. „Schau mal hier …", „Wir machen das so …"
- **`sie`:** Freundlich, höflich, professionell-warm. „Schauen Sie hier …", „Wir empfehlen Ihnen …"

---

### `language_mode`

**Werte:** `fixed` | `adaptive`
**Default:** `adaptive`
**Wirkung:** Steuert ob der Bot in einer fixen Default-Sprache antwortet oder sich an die Sprache des Nutzers anpasst.

- **`fixed`:** Bot antwortet immer in `primary_language` (siehe Reseller-Profile). Wenn Nutzer in anderer Sprache schreibt: höflich auf Default-Sprache reagieren mit Hinweis dass Bot diese Sprache unterstützt.
- **`adaptive`:** Bot erkennt Nutzer-Sprache + wechselt mit. Wenn Nutzer wechselt, wechselt Bot mit. Default = `primary_language` nur für ersten Output.

---

### `video_recommendations_enabled`

**Werte:** `true` | `false`
**Default:** `true`
**Wirkung:** Ob der Bot Video-Empfehlungen (aus der Video-Link-Library) als „Dieses Video erklärt das Thema genauer"-Hint anbietet.

**Sprachlogik wenn `true`:**
- Deutscher Nutzer → deutsches Video → Fallback Englisch wenn kein deutsches verfügbar
- Andere Sprache → jeweilige Sprache → Fallback Englisch
- Bot nennt im Fallback-Fall die Sprache des Videos transparent: „Dazu gibt's ein gutes englisches Video von Dr. Wallerstorfer — magst du das?"

---

### `commercial_disclosure_mode`

**Werte:** `none` | `subtle` | `explicit`
**Default:** `subtle`
**Wirkung:** Wie der Bot mit kommerziellen Themen umgeht (Darwin-AG / Novogenia-AG Aktie, Investitions-Möglichkeit).

- **`none`:** Bot erwähnt nie die Börsen-Listing oder Investment-Möglichkeit.
- **`subtle`:** Bot erwähnt im passenden Kontext („Die Muttergesellschaft ist börsennotiert und firmiert in Kürze in Novogenia AG um."). Kein Push, kein Investment-Advice.
- **`explicit`:** Bot kann auf explizite Nachfrage IR-Seite verlinken (sobald live: `{{NOVOGENIA_AG_IR_URL}}`). Niemals als Empfehlung formuliert.

**Compliance-Note:** Auch im `explicit`-Mode niemals Kauf-Empfehlung. Maximum: „Wenn dich Investments im Genetik-Sektor interessieren, schau dir die Investor-Relations-Seite an."

---

### Flow-Aktivierung pro Flow

**Werte pro Flow:** `true` | `false`
**Default pro Flow:** `true` (Flow ist aktiv) sofern Reseller-Profile nicht explizit `false` setzt
**Wirkung:** Jeder der 11 Flows kann pro Reseller einzeln deaktiviert werden.

| Flow | Wann sinnvoll zu deaktivieren? |
|---|---|
| Flow 01 — Product Q&A | Praktisch nie (Pflicht-Flow). |
| Flow 02 — Sales Training | Wenn Reseller-Bot Endkunden-only (kein Trainings-Kontext). |
| Flow 03 — Legal Questions | Wenn Reseller eigene Compliance-Hotline hat und Bot da nicht aktiv sein soll. |
| Flow 04 — Ad Copy Review | Wenn Reseller-Marketing zentral läuft und Partner kein Marketing-Material erstellen dürfen. |
| Flow 05 — Reseller Onboarding | Wenn Bot reines Endkunden-Tool ist. |
| Flow 06 — Reseller Referrals | Wenn Reseller kein MLM/Empfehlungs-System hat. |
| Flow 07 — NovoPilot Platform Help | Wenn Reseller eigene Plattform nutzt (nicht NovoPilot). |
| Flow 08 — Academy Certification | Wenn Reseller kein Akademie-Programm hat. |
| Flow 09 — Company Information | Praktisch nie (Pflicht-Flow). |
| Flow 10 — Marketing Materials | Wenn keine Materialien zum Teilen vorhanden. |
| Flow 11 — Custom Supplement Creation | Wenn Reseller kein OEM/Private-Label anbietet. |

---

## Schema als Tabellen-Vorlage (für Reseller-Profile-File)

Sektion zum Einfügen in `Reseller Profile.md` direkt unter „Reseller Information":

```markdown
## Bot Configuration Flags

| Flag | Wert | Begründung / Notiz |
|---|---|---|
| allow_science_beyond_products | true | NovoDaily will breite Wissens-Autorität |
| brand_mode | reseller_led | NovoDaily ist Eigenmarke, nicht Novogenia-Vermittler |
| founder_visibility | subtle | Wallerstorfer wird im Wissenschafts-Kontext erwähnt, kein aktiver Social-Push |
| tone_style | du | Per NovoDaily-Vorgabe, Du-Form überall |
| language_mode | adaptive | DACH-Markt, Mehrsprachigkeit erwünscht (DE/EN) |
| video_recommendations_enabled | true | Video-Library wird genutzt |
| commercial_disclosure_mode | subtle | Darwin-AG-Erwähnung erlaubt, IR-Link kommt wenn live |
| primary_language | de-DE | Hauptsprache Deutsch |
| Flow 01 — Product Q&A | true | |
| Flow 02 — Sales Training | true | |
| Flow 03 — Legal Questions | true | |
| Flow 04 — Ad Copy Review | true | |
| Flow 05 — Reseller Onboarding | true | |
| Flow 06 — Reseller Referrals | true | |
| Flow 07 — NovoPilot Platform Help | true | |
| Flow 08 — Academy Certification | true | |
| Flow 09 — Company Information | true | |
| Flow 10 — Marketing Materials | true | |
| Flow 11 — Custom Supplement Creation | true | |
```

---

## Validierungs-Regeln (für künftige UI-Implementierung)

1. `tone_style = sie` + `brand_mode = reseller_led` → ist konsistent, aber unüblich (White-Label-Bots sind meist locker). Warnung anzeigen.
2. `commercial_disclosure_mode = explicit` ohne befüllten `{{NOVOGENIA_AG_IR_URL}}` → Fehler, IR-URL muss erst gesetzt sein.
3. `language_mode = fixed` ohne befüllten `primary_language` → Fehler, primary_language ist Pflicht.
4. Wenn `Flow 02 = false`, gleichzeitig kein anderer Sales-Flow aktiv → Warnung „kein Sales-Coaching verfügbar".
5. Wenn `brand_mode = novogenia_led` + `founder_visibility = none` → Warnung (inkonsistent, novogenia_led heißt typischerweise Wallerstorfer-Sichtbarkeit).

---

## Integration mit bestehender Architektur

**Was bleibt unverändert:**
- NovoDaily Reseller Profile Part A (Identity + Brand & Name Overrides + Units + Delivery Options)
- NovoDaily Reseller Profile Part B (Availability Matrix — bleibt die source-of-truth für Produkt-Verfügbarkeit)
- NovoDaily Reseller Profile Part C (Onboarding + Partnership Model)
- NovoDaily Reseller Profile Part D (Skillbooks)

**Was wird ergänzt:**
- Neue Sektion „Bot Configuration Flags" in Part A (direkt nach „Reseller Information"). Enthält die oben definierte Tabelle.

**Wie der Bot die Flags liest:**
- Master Prompt referenziert die Flag-Sektion: „Bevor du antwortest, prüfe die Bot Configuration Flags im Reseller Profile Part A. Diese überschreiben Default-Verhalten."
- Flags werden via RAG retrieved (gleicher Mechanismus wie die Profile-Werte).

---

## Beispiel-Lookup im Bot-Verhalten

**Szenario:** Nutzer fragt zur Wissenschaft hinter Multi-Cancer Sensor.

**Bot-Logic (pseudocode):**
```
1. Produkt = MULTI_CANCER_SENSOR
2. Lookup Part B Availability: NICHT verfügbar bei NovoDaily (Expert-Linie)
3. Lookup Config Flag `allow_science_beyond_products`: true
4. Entscheidung: Wissenschaft liefern + Hinweis dass Produkt über Ärzte läuft
5. Entscheidung verstärkt durch `brand_mode = reseller_led`: NICHT „bei Novogenia gibt's das" sondern „bei NovoDaily läuft das über die Expert-Linie"
6. Output: kombinierter Text aus Wissenschafts-Erklärung + Reseller-spezifischem Redirect
```

Ohne die Flags wäre nur Hard-Coded-Verhalten möglich. Mit den Flags wird der gleiche Bot tenant-spezifisch differenziert.
