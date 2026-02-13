# Online Retail Data Mining Project

## Overview
This project explores transaction data from a UK-based online retailer to discover patterns in customer purchasing behavior. The goal is to apply core data mining techniques from the course and extend the analysis using an additional technique not covered in class.

This repository currently contains the first project checkpoint, which focuses on dataset selection, comparison, and exploratory data analysis (EDA).

---

## Project Goals
- Select a dataset that supports course data mining techniques
- Identify an additional, beyond-course technique
- Perform exploratory data analysis
- Document data cleaning decisions and observations
- Formulate initial research questions

---

## Selected Dataset
**Online Retail Dataset**  
Source: UCI Machine Learning Repository  
https://archive.ics.uci.edu/ml/datasets/online+retail

### Dataset Description
- ~541,000 transaction rows
- UK-based online retailer
- Time period: December 2010 – December 2011
- Each row represents a product within an invoice
- Includes product info, quantities, timestamps, and customer IDs

---

## Techniques

### Course Techniques
- Frequent itemset mining
- Association rule mining

### Beyond-Course Technique
- Sequential pattern mining using transaction timestamps

---

## Exploratory Data Analysis Highlights
Key findings from the initial analysis:

- A small number of products dominate transaction frequency.
- The average basket size is approximately 21 items.
- The dataset is highly sparse in item co-occurrence.
- Transactions occur in rapid bursts, with an average time gap of about 1.3 minutes.

These observations suggest that sequential or time-aware analysis may reveal patterns not captured by standard association rules.

---

## Repository Structure
- `Project_Checkpoint_1.ipynb` — Main notebook
- `data/` — Dataset folder (downloaded automatically)
- `README.md` — Project description

---

## How to Run
1. Clone the repository:
   `git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git`
2. Open the notebook:
   `Project_Checkpoint_1.ipynb`
3. Run all cells from top to bottom.
   - The dataset will download automatically.

---

## Initial Research Questions
1. How do different support thresholds affect the quality of association rules?
2. Do sequential patterns reveal relationships missed by frequent itemsets?
3. Are there different purchasing patterns between bulk and small-basket customers?

---

## Future Work
- Implement frequent itemset mining (Apriori or FP-Growth)
- Generate and evaluate association rules
- Apply sequential pattern mining
- Compare unordered vs. temporal patterns

---

## Author
Amaan Chaudhry  
Texas A&M University
