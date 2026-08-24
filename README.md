# Amazon Ecommerce Purchase Analysis

A pandas-based exploratory analysis of 10,000 simulated Amazon purchase records, answering a set of business questions about customer behaviour, payment methods, and contact data.

This is **Mini Project 1 of 3** completed during a Data Science internship at Great Learning Pvt. Ltd., 15 June to 16 August 2020.

## Overview

The dataset is a synthetic snapshot of ecommerce transactions, with one row per purchase and a wide mix of attribute types: monetary values, timestamps split into AM and PM, free-text job titles, email addresses, credit card metadata, browser strings, and IP addresses.

The exercise is deliberately query-shaped rather than model-shaped. Each question is answered with a single pandas expression, which makes it a focused drill in indexing, boolean masking, value counts, and string operations on Series rather than an open-ended investigation.

## Dataset

`Ecommerce Purchases.csv`, **10,000 rows across 14 columns**.

Columns cover Address, Lot, AM or PM, Browser Info, Company, Credit Card, CC Exp Date, CC Security Code, CC Provider, Email, Job, IP Address, Language, and Purchase Price.

## Questions Answered

Every result below is reproduced from the notebook output.

**Purchase behaviour**

| Metric | Value |
| --- | --- |
| Average purchase price | $50.35 |
| Highest purchase price | $99.99 |
| Lowest purchase price | $0.00 |
| Purchases made in the afternoon (PM) | 5,068 |
| Purchases made in the morning (AM) | 4,932 |

The AM and PM split is almost exactly even, which is a useful reminder that this is generated data rather than real traffic, where you would expect pronounced daily peaks.

**Customer attributes**

- 1,098 customers set their site language to English (`en`)
- 30 customers list "Lawyer" as their job title
- The five most common job titles are Interior and spatial designer (31), Lawyer (30), Social researcher (28), Designer, jewellery (27), and Research officer, political party (27)

**Payment and contact data**

- 39 customers paid with American Express on a purchase above $95
- 1,033 credit cards expire in 2025
- The top five email hosts are hotmail.com (1,638), yahoo.com (1,616), gmail.com (1,605), smith.com (42), and williams.com (37)

The steep drop from the three major providers to the fourth place domain is another artefact of synthetic generation: real-world long tails decay far more gradually.

**Record lookups**

- The purchase from Lot "90 WT" was $75.10
- The account holding card number 4926535242672853 is `bondellen@williams-garza.com`

## Techniques Used

- Boolean masking and compound conditions with `&` for multi-criteria filters
- `value_counts()` for frequency distributions and top-N ranking
- `apply()` with lambda expressions for row-wise string work, including slicing expiry dates and splitting email addresses on `@` to isolate the host
- `sum()` over a boolean Series to count matches without an intermediate filter

## Tech Stack

- Python 3
- Jupyter Notebook
- pandas
- NumPy

## Running It

```bash
pip install pandas numpy jupyter
jupyter notebook "Mini Project 1 - Amazon_Ecommerce_Purchases_Submission_Raunak_Choudhary.ipynb"
```

One thing to be aware of before running: the notebook loads the dataset as `Ecommerce Purchases` without a file extension, while the committed file is `Ecommerce Purchases.csv`. Either copy the file or adjust the read:

```bash
cp "Ecommerce Purchases.csv" "Ecommerce Purchases"
```

The repository also includes HTML and PDF exports of the completed notebook if you would rather read the results than run them.

## Internship Series

This is one of three projects from the same internship, in increasing order of statistical depth:

1. **Amazon Ecommerce Purchase Analysis** (this repository): pandas querying and filtering
2. [Insurance Cost Statistical Analysis](https://github.com/raunak-choudhary/Insurance-Cost-Statistical-Analysis-Data-Science-Internship-2020): EDA plus hypothesis testing with t-tests, chi-square, and ANOVA
3. [LaLiga Statistics Analysis](https://github.com/raunak-choudhary/LaLiga-Statistics-Analysis-Data-Science-Internship-2020): data cleaning, derived metrics, and grouped aggregation

## Author

**Raunak Choudhary**

Data Science Intern, Great Learning Pvt. Ltd.

[Email](mailto:raunakchoudhary17@gmail.com) · [LinkedIn](https://www.linkedin.com/in/raunak-choudhary)
