# Mining Purchasing Patterns in Online Retail Transactions

Association Rules, Support Threshold Sensitivity, and Sequential Pattern Mining

---

## Overview

This project analyzes transaction data from a UK-based online gift retailer to uncover hidden purchasing patterns. Using association rule mining (Apriori, FP-Growth) and sequential pattern mining (PrefixSpan), we investigate how customers buy products together within single transactions and how their purchasing behavior evolves across multiple visits over time.

---

## Dataset

**Online Retail Dataset**
- **Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/online+retail)
- **Size:** ~541,900 transaction rows, 8 columns
- **Retailer:** UK-based online gift shop
- **Time period:** December 2010 – December 2011
- **Contents:** Invoice numbers, product codes/descriptions, quantities, prices, customer IDs, and timestamps

After cleaning (removing missing customer IDs, cancelled orders, and invalid rows), the working dataset contains ~354,000 rows covering 4,338 customers and 3,665 unique products.

---

## Research Questions

1. **RQ1 — Threshold Sensitivity:** How do different support thresholds affect the number and quality of frequent itemsets discovered?
2. **RQ2 — Rule Quality Metrics:** How do confidence and lift compare when evaluating association rules, and which metric surfaces more actionable insights?
3. **RQ3 — Temporal Structure:** Do sequential purchasing patterns reveal customer behavior that unordered basket analysis cannot capture?

---

## Techniques & Algorithms

| Technique | Algorithm | Library |
|-----------|-----------|---------|
| Frequent itemset mining | Apriori, FP-Growth | `mlxtend` |
| Association rule generation | Confidence & lift evaluation | `mlxtend` |
| Sequential pattern mining | PrefixSpan | `prefixspan` |

---

## Key Results

- **Support threshold matters dramatically.** Going from 5% to 1% support increases discovered itemsets from 20 to 914 (45x). Multi-item co-purchase patterns only appear below 3% support.
- **Lift outperforms confidence** for identifying genuinely interesting associations. The Regency Teacup product family showed lift values exceeding 22x, indicating very strong affinity.
- **82% of sequential patterns have no counterpart in association rules.** Sequential mining reveals repeat purchases, cross-visit product exploration, and multi-step purchasing journeys that basket analysis cannot detect.
- **1,382 sequential patterns** discovered via PrefixSpan, including 907 length-2 and 475 length-3 patterns.

---

## Repository Structure

```
├── final_deliverable.ipynb   # Main notebook (all analysis, visualizations, and discussion)
├── data/                     # Dataset folder (downloaded automatically on first run)
└── README.md
```

---

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/YOUR_USERNAME/676-Project.git
   ```
2. Install dependencies:
   ```bash
   pip install mlxtend prefixspan openpyxl seaborn pandas numpy matplotlib
   ```
3. Open and run the notebook:
   ```
   final_deliverable.ipynb
   ```
   The dataset downloads automatically on first run.

---

## Author

Amaan Chaudhry
Texas A&M University
