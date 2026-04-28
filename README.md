# Mining Purchasing Patterns in Online Retail Transactions

**Association Rules, Support Threshold Sensitivity, and Sequential Pattern Mining**

This project analyzes ~542,000 transaction records from a UK-based online gift retailer to uncover hidden purchasing patterns. Using association rule mining (Apriori, FP-Growth) and sequential pattern mining (PrefixSpan), we investigate how customers buy products together within single transactions and how their purchasing behavior evolves across multiple visits over time. The key finding: **82% of sequential patterns have no counterpart in traditional basket analysis** — meaning most temporal purchasing behavior is invisible without sequence-aware techniques.

> **Start here:** [`main_notebook.ipynb`](main_notebook.ipynb)

> **Project Video:** https://youtu.be/HtcPevO34g0

---

## Research Questions

1. **RQ1 — Threshold Sensitivity:** How do different support thresholds affect the number and quality of frequent itemsets discovered?
2. **RQ2 — Rule Quality Metrics:** How do confidence and lift compare when evaluating association rules, and which metric surfaces more actionable insights?
3. **RQ3 — Temporal Structure:** Do sequential purchasing patterns reveal customer behavior that unordered basket analysis cannot capture?

---

## Dataset

**Online Retail Dataset** — [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/online+retail)

| Property | Value |
|----------|-------|
| Rows | ~541,900 |
| Columns | 8 (InvoiceNo, StockCode, Description, Quantity, InvoiceDate, UnitPrice, CustomerID, Country) |
| Retailer | UK-based online gift shop |
| Time period | December 2010 – December 2011 |

**Preprocessing steps:**
- Removed ~135,000 rows with missing `CustomerID` (~25% of data)
- Filtered out cancelled orders (invoices starting with "C")
- Dropped rows with non-positive quantities or prices
- Final working dataset: **~354,000 rows**, 4,338 customers, 3,665 unique products
- Built a binary transaction matrix (top 500 products) for association rule mining
- Built ordered customer purchase sequences (top 200 products) for sequential mining

The dataset downloads automatically on the first notebook run — no manual download needed.

---

## Results Summary

- **Support threshold is a gatekeeper.** Going from 5% to 1% support increases discovered itemsets from 20 to 914 (a 45x jump). Multi-item co-purchase patterns only emerge below 3% support.
- **Lift beats confidence** for surfacing genuinely interesting rules. The Regency Teacup product family showed lift values exceeding 22x — strong affinity invisible to confidence-only ranking.
- **Sequential mining reveals a hidden dimension.** PrefixSpan discovered 1,382 patterns, and 82% of length-2 sequential patterns had no counterpart in association rules. Repeat purchases, cross-visit product exploration, and multi-step purchasing journeys are all invisible to traditional basket analysis.

---

## How to Reproduce

This project was built and tested in **Google Colab**. To run it locally:

1. Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/676-Project.git
cd 676-Project
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Open and run the main notebook:

```
main_notebook.ipynb
```

Run all cells top to bottom. The dataset downloads automatically on first run.

---

## Key Dependencies and Versions

| Package | Version |
|---------|---------|
| Python | 3.9.6 |
| pandas | 2.3.3 |
| numpy | 2.0.2 |
| matplotlib | 3.9+ |
| seaborn | 0.13+ |
| mlxtend | 0.23+ |
| prefixspan | 0.5+ |
| openpyxl | 3.1+ |

Full list in [`requirements.txt`](requirements.txt).

---

## Repository Structure

```
676-Project/
├── main_notebook.ipynb          # Main deliverable — start here
├── checkpoints/
│   ├── checkpoint_1.ipynb       # Project Checkpoint 1 (dataset selection & EDA)
│   └── checkpoint_2.ipynb       # Project Checkpoint 2 (initial mining experiments)
├── data/                        # Dataset folder (auto-downloaded on first run)
├── requirements.txt             # Python dependencies
├── .gitignore
└── README.md
```

---

## Author

Amaan Chaudhry
Texas A&M University
