# Shipping & Delivery Costs
<!--
  REQUIRES_VARIABLE: (none — always loaded; per-reseller free-shipping rules in reseller identity)
  PURPOSE: Per-region shipping costs for reports and for additional products.
  VARIABLES: Product names use {{VARIABLE}} tokens defined in the reseller's Profile file (Part A) — e.g. 10_RESELLER_BRANDED__NOVODAILY/NovoDaily Reseller Profile.md.
-->

---

## Report Print & Shipping Costs

### What this covers

These costs apply when shipping printed reports from one customer order. A single order may include multiple analyses — the cost is per order, not per report, because all reports from one order ship together.

### Cost by region — printed reports

Austria: €27.50. Germany: €28.30. Switzerland: €44.20. Great Britain: €44.20. EU group (Belgium, Denmark, France, Luxembourg, Netherlands, Italy, Sweden, Spain, Finland, Poland, Portugal, Slovakia, Slovenia, Czech Republic, Hungary, Isle of Man): €36.70. Rest of Europe: €44.20. Rest of world: €58.20. All prices exclude VAT.

---

## Additional Products — Packaging & Shipping

### What this covers

Costs for shipping supplements, cosmetics, or other physical products that are not bundled inside the original report shipment. Supplement subscriptions typically ship every three months; these per-shipment costs apply.

### Cost by region — additional products

Austria: €7.50. Germany: €8.30. Switzerland: €24.00. Great Britain: €26.30. EU group: €19.90. Rest of Europe: €36.50. Rest of world: €51.20. All prices exclude VAT.

---

## Free-shipping Rules per Reseller

### How the chatbot should handle this

Many resellers absorb shipping into their listed prices or set their own thresholds for free shipping. The chatbot should consult the reseller's identity file for the active rule before quoting shipping cost to a customer. The numbers above are the underlying Novogenia carrier costs; what a customer pays depends on the reseller's commercial choices.

### NovoDaily default

For NovoDaily, the published rule is "Versandkostenfrei" (shipping included) on {{PACKAGE_LIFESTYLE_PLUS}} subscriptions. For other products, the customer-facing shipping cost is set during checkout.

---

## Delivery Timeline

### Kits to customer

Sample collection kit ships within typical postal delivery times after order. DACH region: usually a few days. EU: typically 5–10 days. Rest of world: depends on destination.

### Sample to lab

After the customer collects their sample and posts the kit back, it usually arrives at the laboratory within a few days. The collection device stabilises the sample for two weeks across a wide temperature range, so normal postal timing is fine.

### Analysis turnaround

From sample receipt at the lab to report ready: typically a few weeks depending on analysis complexity and current volume.

### Supplement / cosmetic shipping

Once formulation is calculated, the first 3-month supply is produced and shipped. Customers in DACH typically receive their first shipment within 2–3 weeks of sample arrival at the lab.
