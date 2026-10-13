# Task 10: Duplicate Record Check — Sample Superstore

## Overview

This project identifies duplicate records in the Sample Superstore dataset using Python and Pandas. It demonstrates how to detect duplicate rows, document findings, and prepare a cleaned dataset while maintaining an audit trail.

## Objective

- Identify exact duplicate records.
- Understand the difference between full-row duplicates and duplicates based on selected columns.
- Remove confirmed duplicate rows.
- Document the results in a duplicate report and audit note.
- Export a cleaned copy of the dataset.

## Tools Used

- Python
- Pandas
- Google Colab
- CSV / Excel

## Dataset

**Dataset:** Sample Superstore

The dataset contains sales transaction information, commonly including fields such as Order ID, Order Date, Customer ID, Product Name, Sales, Quantity, Discount, and Profit. Actual columns depend on the dataset version used.

## Project Workflow

1. Load the Sample Superstore dataset.
2. Inspect the dataset structure, column names, data types, and missing values.
3. Identify exact duplicate rows using Pandas.
4. Review potential duplicates based on relevant business keys.
5. Remove confirmed exact duplicate rows.
6. Compare the original and cleaned dataset.
7. Export the duplicate report, cleaned dataset, and audit note.

## Duplicate Detection

Exact duplicate rows are identified using:

```python
df.duplicated(keep=False)
```

This marks every row belonging to a group of identical records, making it easier to review duplicates before cleaning.

For business-key checks, columns such as Order ID and Order Date may help identify repeated combinations, depending on the dataset structure. Repeated Order IDs alone do not automatically mean a record is a duplicate because one order can contain multiple products.

## Data Cleaning

Confirmed exact duplicate rows are removed using:

```python
df.drop_duplicates(keep="first")
```

The cleaned dataset is then compared with the original to verify the number of rows removed and check whether exact duplicates remain.

## Deliverables

- **Duplicate Report:** Records identified as exact duplicates.
- **Cleaned Dataset:** Dataset after removing exact duplicate rows.
- **Audit Note:** Summary of the source file, row counts, duplicates detected, records removed, and final row count.

## Key Learnings

- How to detect duplicate rows using Pandas.
- Why duplicate records can distort sales totals and other business metrics.
- Why repeated order identifiers should be reviewed rather than automatically deleted.
- How to document data-cleaning decisions.
- How to export reproducible data-cleaning outputs.

## Conclusion

This project demonstrates a practical data-quality workflow for the Sample Superstore dataset. It emphasizes careful duplicate detection, responsible cleaning, validation, and documentation to support more reliable analysis.

**Internship:** Data Analytics Internship — Veda Technologies
