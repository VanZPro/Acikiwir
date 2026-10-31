# Datasheet for Dataset: Global Retail & E-Commerce Product Price Intelligence
## 1. Motivation

* **For what purpose was the dataset created?**
  This dataset was aggregated to provide economists, data scientists, and retail analysts with real price observations from store shelves globally. It serves as a resource for studying price discrimination, local inflation variations, and product category dynamics across international markets.

* **Who created the dataset and who funded its creation?**
  Primary crowd-sourced data collection is hosted and maintained by Open Food Facts, a non-profit organization operating open data initiatives globally.

---

## 2. Composition

* **What do the instances that comprise the dataset represent?**
  Each row represents a specific pricing instance for a consumer packaged product recorded at a specific retail outlet on a given date.

* **How many instances are there in total?**
  The active dataset contains a snapshot of up to 50,000 recent price submission entries retrieved directly from the live API.

* **Is any information missing or incomplete?**
  Certain product entries may lack explicit GTIN barcodes (`product_code`) or specific store chain names if the user submitting the receipt did not provide them. Pricing, date, and country fields are 100% complete.

* **Are there confidential or sensitive data fields?**
  No. All data consists of public retail product details and publicly posted shelf prices. No personal user data or shopper information is present.

---

## 3. Collection Process

* **How was the data acquired?**
  Data is gathered via the Open Prices public API, which receives verified crowdsourced submissions, receipt scans, and open store data feeds.

* **What was the timeframe for collection?**
  Records span from the launch of the Open Prices project through recent ongoing submissions.

---

## 4. Preprocessing and Cleaning

* **What preprocessing steps were taken?**
  - Standardized all string column headers to lowercase snake_case.
  - Converted dates into explicit ISO-8601 strings (`YYYY-MM-DD`).
  - Extracted store names and location attributes from nested metadata arrays.

---

## 5. Recommended Applications

* **Recommended Use Cases:**
  - Regional purchasing power parity (PPP) and cost-of-living studies.
  - Machine learning classification to predict discount likelihood based on brand or store chain.
  - Natural Language Processing (NLP) on product titles for category extraction.

* **Unideal Applications:**
  This dataset should not be used for real-time high-frequency financial trading or automated dynamic repricing where millisecond-level market accuracy is required.