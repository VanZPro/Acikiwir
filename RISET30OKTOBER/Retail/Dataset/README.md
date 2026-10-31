# Global Retail & E-Commerce Product Price Intelligence Dataset

## Dataset Overview

This dataset provides a snapshot of product metadata, pricing structures, category classifications, and consumer feedback across international retail categories. Extracted directly from Open Food Facts' Open Prices global initiative API, the dataset captures real crowdsourced and verified retail pricing data from store receipts and public shelf tags worldwide.

Every record reflects actual real-world prices collected across major supermarket and retail chains, making it ideal for price elasticity analysis, inflation tracking, currency comparison, and product recommendation engine development.

---

## Technical Specifications

- **Source System:** Open Food Facts - Open Prices Global Crowdsourced Engine API
- **Geographic Coverage:** International (United States, Europe, Latin America, Asia-Pacific)
- **File Format:** Comma-Separated Values (`.csv`) with UTF-8 Encoding
- **Primary Key:** `price_record_id`
- **Primary Use Cases:** Retail Inflation Indexing, Cross-Border Price Disparity Modeling, Supermarket Pricing Strategy, Brand Market Share Analysis

---

## Dataset Structure and Column Descriptions

| Column Name | Data Type | Nullable | Example Value | Description |
| :--- | :--- | :--- | :--- | :--- |
| `price_record_id` | Integer | No | `104829` | Unique numerical identifier for the individual price observation record. |
| `product_code` | String | Yes | `3017620422003` | Global Trade Item Number (GTIN) or UPC/EAN barcode identifier. |
| `product_name` | String | Yes | `Nutella Hazelnut Spread 400g` | Standardized product title or item name. |
| `brand` | String | Yes | `Ferrero` | Manufacturer or brand owner associated with the item. |
| `category` | String | Yes | `Snacks, Sweet snacks, Cocoa and hazelnut spreads` | Primary product category classification hierarchy. |
| `price` | Float | No | `4.29` | Observed price value in the local transaction currency. |
| `currency` | String | No | `EUR` | ISO 4217 three-letter currency code (e.g., USD, EUR, GBP). |
| `price_is_discounted` | Boolean | No | `False` | Flag indicating whether the price was a promotional or clearance rate. |
| `store_name` | String | Yes | `Carrefour` | Retail store chain or merchant where the item was observed. |
| `city` | String | Yes | `Paris` | City or municipality where the retail location is situated. |
| `country_code` | String | No | `FR` | Two-letter ISO country code for the store location. |
| `date_recorded` | Date | No | `2024-11-12` | ISO-8601 formatted date (`YYYY-MM-DD`) when the price was recorded. |

---

## Data Collection and Extraction Procedure

1. **API Ingestion:** Data is fetched directly from the Open Prices public endpoint (`https://prices.openfoodfacts.org/api/v1/prices`).
2. **Field Extraction:** Dynamic nested JSON objects containing geographic coordinates, store tags, and currency details are unwrapped into tabular format.
3. **Cleaning & Standardization:** Unverified records without explicit pricing or location codes are filtered out. Empty categorical fields are assigned standard `None` or `Unknown` markers.

---

## License and Attribution

- **Original Data Source:** Open Food Facts Open Prices Database.
- **Data License:** Open Database License (ODbL) / Open Data Commons.
- **Attribution Requirement:** Any derivative works or public models using this dataset must cite Open Food Facts and the Open Prices contributors.