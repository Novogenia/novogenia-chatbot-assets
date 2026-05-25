# Glossary — Plain Language Genetics
<!--
  REQUIRES_VARIABLE: (none — always loaded)
  PURPOSE: Lay-language definitions of genetic and biotech terms customers commonly ask about.
  VARIABLES: Product names use {{VARIABLE}} tokens defined in the reseller's Profile file (Part A) — e.g. 10_RESELLER_BRANDED__NOVODAILY/NovoDaily Reseller Profile.md.
-->

---

## Basic Concepts

### DNA

DNA is the chemical molecule that stores genetic instructions inside every cell of the body. Think of it as a very long recipe book — every cell carries the same copy of this book.

### Gene

A gene is a section of DNA that codes for a specific function — for example, building an enzyme that processes vitamins, or controlling how fat is stored. Humans have around 20,000–25,000 genes.

### SNP (Single Nucleotide Polymorphism)

An SNP is a single-letter difference in the DNA code at one position. SNPs are the most common type of genetic variation between people and account for most differences in how individuals respond to nutrients, medications, and lifestyle.

### Gene mutation

A gene mutation is a rare, spontaneous change in the DNA code that typically appears in only one person or one family. Mutations are different from SNPs — SNPs are common variants found across the population; mutations are uncommon individual errors.

### Variant

A general term covering SNPs, gene mutations, and other DNA-level differences. When the chatbot says "variant", it usually refers to an SNP — a common genetic difference relevant to the customer's analysis.

---

## How Genes Affect the Body

### Genotype vs phenotype

Genotype = the actual DNA sequence the person carries. Phenotype = the visible or measurable effect of that genotype (eye colour, ability to process lactose, how well a vitamin works). The same genotype can produce slightly different phenotypes depending on diet, environment, and other genes.

### Allele

Each gene exists in two copies — one from each parent. Each copy is called an allele. Some traits need both alleles to be variant for an effect to show (recessive); others show with just one variant allele (dominant).

### Carrier

Someone with one variant allele and one normal allele is sometimes called a "carrier" — they typically don't show the trait themselves but can pass the variant to children.

### Penetrance

How likely a genetic variant is to actually produce its effect. Some variants produce the trait every time; others only sometimes. Most lifestyle-relevant variants have moderate penetrance — the trait is influenced but not guaranteed.

---

## Epigenetics

### What epigenetics means

Epigenetics covers the chemical "switches" that turn genes on or off without changing the DNA sequence itself. Lifestyle, diet, environment, and stress can adjust these switches. The DNA itself does not change; what changes is which genes are active.

### Why it matters

Epigenetic changes can persist for many years and can even be partially passed on to children. The {{NUTRITION_SENSOR}} report touches on epigenetic considerations where relevant.

---

## Specific Genes Customers Ask About

### MTHFR

A gene controlling folic acid activation. Variants prevent the body from converting standard folic acid into its active form (methylfolate). About 5–8% of people have variants where standard folic acid is largely useless and methylfolate must be taken directly.

### CYP1A2

The main gene controlling caffeine metabolism. Fast metabolizers clear caffeine quickly; slow metabolizers retain it. Genetic status changes whether 3+ coffees per day are protective or harmful to the heart.

### APOA1

A gene affecting how Omega-3 interacts with cholesterol. In some variants, Omega-3 worsens cholesterol rather than improving it.

### VDR

A gene controlling how cells take up Vitamin D from the blood. Variants mean blood D3 can be normal while cells are still deficient — requiring higher doses.

### HFE

A gene controlling iron absorption. The "Celtic" variant doubles iron uptake; carriers should generally avoid iron supplementation to prevent overload.

### NQO1

A gene required to activate CoQ10. Variants make CoQ10 supplementation ineffective; carriers benefit more from Vitamins C and E as antioxidants.

### COMT

A gene controlling clearance of stress neurotransmitters. Variants influence baseline stress tolerance and recovery. The central gene in {{BURNOUT_SENSOR}}.

### GST family (GSTM1, GSTP1, GSTT1)

Genes in the Phase II detoxification system. Variants reduce the body's ability to neutralise burned substances, chemicals, and free radicals. The core gene set in {{TOXO_SENSOR}}.

---

## Technology Terms

### Microarray

A laboratory chip that simultaneously measures the genetic code at hundreds of thousands of specific positions in a sample. {{COMPANY_NAME}} uses a custom microarray measuring 750,000 positions per sample.

### AI imputation

A statistical method that uses known patterns of inheritance to infer the value of variants not directly measured. {{COMPANY_NAME}} expands the directly measured 750,000 variants to approximately 72 million using imputation.

### Sanger sequencing

A classical, very accurate method for reading short DNA segments (~100 letters). Used for known specific variants in medical genetics; not practical at scale for broad lifestyle analyses.

### Whole genome sequencing (WGS)

Reading the entire human genome (~3 billion letters). Highest data volume; expensive (~€1,500 per sample); roughly 15× worse cost-benefit than microarray for nutrition and lifestyle purposes.

### IgE vs IgG

IgE antibodies cause classic immediate allergic reactions (tested in {{ALLERGY_SENSOR}}). IgG antibodies cause delayed-onset intolerances (tested in {{FOOD_INTOLERANCE_SENSOR}}). Same biological category (antibodies), different biological mechanisms.

### Telomeres

Protective caps at the ends of chromosomes that shorten with each cell division. Telomere length is one measurable indicator of cellular ageing. {{BIOLOGICAL_AGE_SENSOR}} estimates the body's genetic capacity to maintain telomere length.

### PubMed

The US National Library of Medicine's database of medical and biological research publications. PubMed IDs cited in {{COMPANY_NAME}} reports point to the specific peer-reviewed studies supporting each gene-trait claim.
