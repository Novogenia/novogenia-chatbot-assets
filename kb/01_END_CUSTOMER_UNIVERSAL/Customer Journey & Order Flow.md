# Customer Journey & Order Flow
<!--
  REQUIRES_VARIABLE: (none — always loaded)
  PURPOSE: Chronological walkthrough of what happens from order placement to ongoing delivery.
           The chatbot uses this to explain "what happens next" to new customers.
  VARIABLES: Product names use {{VARIABLE}} tokens defined in the reseller's Profile file (Part A) — e.g. 10_RESELLER_BRANDED__NOVODAILY/NovoDaily Reseller Profile.md.
-->

---

## Step 1 — Ordering

### How does the order itself work?

The customer chooses a product on the {{WEBSITE_NAME}} (or via the reseller's channel). For a "+" subscription, the first monthly instalment is charged at order time. For a one-time DNA test or product, the full price is charged at order time. A confirmation is sent with order details.

### What does the customer receive first?

A sample collection kit is dispatched to the customer's address. Kits arrive within typical postal delivery times — usually a few days for DACH-region customers, longer for other markets. The kit includes the saliva collection device, a return envelope, and clear collection instructions.

---

## Step 2 — Sample Collection

### How does the customer collect their sample?

The customer swirls a small amount of water around their mouth and spits into the proprietary collection tube. They should avoid eating for 30 minutes before collection. The kit includes detailed step-by-step instructions in the customer's language. No medical professional is needed.

### How does the sample get back?

The customer seals the tube and posts the return envelope. The collection device is designed to stabilise the sample for two weeks across a wide temperature range, so postal delivery worldwide is reliable. No cold-chain logistics needed.

---

## Step 3 — Laboratory Analysis

### What happens at the lab?

The sample arrives at Novogenia's laboratory in Eugendorf, Salzburg, Austria. The barcoded tube is checked in by automated systems — the lab works only with barcodes, not customer identity, during analysis. DNA is extracted, the custom microarray runs the analysis, and AI imputation expands the dataset.

### How long does this take?

Typically a few weeks from sample receipt to results delivery. Exact timing varies by analysis complexity and current volume. The customer is notified once their results are ready.

### What if the sample fails?

The lab can attempt up to three independent analyses from the same saliva sample. If all three fail, a new kit is sent to the customer free of charge.

---

## Step 4 — Report Generation and Delivery

### How are reports delivered?

Delivery format depends on the reseller — see the reseller availability matrix. Options include PDF download, interactive HTML report (app-like experience), and a printed physical book. Reports are typically 200–400+ pages depending on the analyses ordered.

### How is identity linked back?

After analysis is complete, the barcoded result is linked back to the customer's identity. The customer is then notified via email and the {{REPORT_PORTAL}} that the report is ready.

### What language?

Reports are available in German and English upon request. The default is the customer's order language; the alternative can be enabled via the {{REPORT_PORTAL}}.

---

## Step 5 — Personalised Supplement Production (if subscribed)

### When does the supplement begin?

Once analysis is complete, the formulation algorithm calculates the customer's personalised recipe. The first 3-month supply of {{SUPPLEMENT_DAILY}} is then produced and shipped — directly with the report or in a separate shipment depending on the reseller's setup.

### Monthly billing rhythm

The first instalment was charged at order time. From the point of the first supplement delivery, billing continues monthly. The supplement is produced and shipped every three months — so the customer has uninterrupted daily supply while paying in convenient monthly instalments.

---

## Step 6 — Ongoing Subscription

### Quarterly reformulation

Each 3-month reorder is recalculated to reflect the customer's current age, any new analysis data added since the last order, and any new science integrated into the algorithm. The algorithm is improved approximately once per week on average. The customer's genetic results never change, but the way they are translated into a recipe continues to evolve.

### Adding more analyses

Customers can add further analyses to their account at any time — for example adding {{ALLERGY_SENSOR}} or {{METABOLISM_SENSOR}} to a {{PACKAGE_LIFESTYLE_PLUS}} subscription. New results automatically feed into the next supplement reformulation.

### Pausing or cancelling

After the minimum subscription term has ended, the customer can pause or cancel online at any time. Pausing preserves all data and resumes whenever the customer is ready. See the Cancellation, Pause & Returns file for full details.

---

## Step 7 — Long-term Use

### How long can the customer take {{SUPPLEMENT_DAILY}}?

{{SUPPLEMENT_DAILY}} is designed for daily, long-term use. The formulation never exceeds EFSA upper safe limits even combined with a nutrient-rich diet.

### What about new science?

New genetic findings are continuously integrated into the algorithm. The customer's report will improve over time — typically reflected in newer reformulation cycles and, where relevant, communicated via the {{REPORT_PORTAL}}.

### Repeat genetic testing

Genes do not change. The customer does not need to repeat a genetic test they have already completed. Adding new analyses (different gene sets) is meaningful; repeating the same analysis is not.
