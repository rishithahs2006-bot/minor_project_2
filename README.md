# SpendDNA – Your Wallet's Year-End Story

**SpendDNA** is a personal finance analysis tool built to ingest raw banking or transaction logs, standardise messed-up data formats, categorize expenses, and generate structured spending summaries and visualisations.

---

## 📌 Project Details

* **Project Title:** Minor Project 2 – SpendDNA: Your Wallet's Year-End Story
* **Author:** Rishitha HS
* **USN:** 4RA23CI031
* **Batch:** July
* **Date:** 08 August 2026

---

## 🛠️ Features & Workflow

The notebook processes raw banking records (`DADS MP2 Dataset.csv`) through four key functional stages:

### Feature 1 – Transaction Parser & Data Cleaning
Raw bank statements contain inconsistent date formats, currency symbols, duplicate entries, and mixed transaction types. The parser:
* **Normalises Currency:** Strips currency symbols (`₹`, `Rs.`), cleans commas, and converts transaction amounts into standard numeric values.
* **Standardises Dates:** Uses multi-format date parsing (`%Y-%m-%d`, `%d-%b-%y`, `%d/%m/%y`, etc.) to eliminate missing/unparsed (`NaT`) dates.
* **Standardises Types:** Normalises transaction type markers (`DR` → `Debit`, `CR` → `Credit`).
* **Deduplication:** Identifies and drops duplicate transaction entries.

### Feature 2 – Vendor Extractor
Extracts and standardises merchant or vendor names from unstructured description strings:
* Strips payment mechanism prefixes (e.g., `UPI-`, `POS `, `BHIM-`, `NEFT-`) and handles `@` / `-` delimiters.
* Standardises variations of vendor aliases under unified brands (e.g., `ZOMATO MEDIA P L`, `ZOMATO BENGALURU`, `POS ZOMATO` → **`ZOMATO`**).

### Feature 3 – Category Tagger
Categorises cleaned transactions into high-level spending groups:
* **Food:** Swiggy, Zomato, Blinkit, Zepto, Restaurants, Starbucks, Truffles, CCD, etc.
* **Transport:** Uber, Ola, Rapido, BMTC, Tummoc, etc.
* **Shopping:** Amazon, Flipkart, Myntra, Nykaa, Dmart, BigBasket, etc.
* **Bills:** BESCOM, Electricity, BWSSB, Airtel, Vi, Mobile Recharge, Rent, etc.
* **Entertainment:** BMS, PVR, BookMyShow, Netflix, Spotify, Disney+ Hotstar, etc.
* **Fuel:** Petrol, Indian Oil, Fuel Stations, etc.
* **Investment:** Groww, Zerodha, Coin, Mutual Funds.
* **Transfer:** P2P Transfers (e.g., UPI transfers to personal handles).
* **Income:** Credit/Salary transactions.

### Feature 4 – Spending Overview & Data Visualisation
Calculates top-level metrics across all processed entries and generates visual spending distributions using `matplotlib`.

---

## 📊 Dataset Analytics Summary

Based on the execution run on 1,310 deduplicated transactions:

| Metric | Value |
| :--- | :--- |
| **Total Income** | ₹ 509,774.00 |
| **Total Spending** | ₹ 1,678,901.00 |
| **Average Transaction Amount** | ₹ 1,670.74 |

### Spending Breakdown by Category

| Category | Total Spent (₹) |
| :--- | :--- |
| **Shopping** | ₹ 649,789.00 |
| **Food** | ₹ 353,335.00 |
| **Investment** | ₹ 248,160.00 |
| **Bills** | ₹ 135,264.00 |
| **Other** | ₹ 114,854.00 |
| **Fuel** | ₹ 89,303.00 |
| **Transport** | ₹ 51,860.00 |
| **Entertainment** | ₹ 18,437.00 |
| **Transfer** | ₹ 17,899.00 |

---

## 💻 Tech Stack & Requirements

* **Language:** Python 3
* **Libraries Used:**
  * `pandas` – Data manipulation & clean-up
  * `numpy` – Array operations
  * `matplotlib` – Data visualisation
  * `datetime` – Custom date parsing

---

## 🚀 How to Run

1. Clone the repository:
   ```bash
   git clone [https://github.com/your-username/spenddna.git](https://github.com/your-username/spenddna.git)
   cd spenddna
