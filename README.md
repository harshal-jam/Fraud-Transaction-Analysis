# Fraud Transaction Analysis & Risk Monitoring

**A Data Analyst Portfolio Project | Python · Pandas · NumPy · Microsoft Excel · Power BI · DAX**

## 1. Project Overview

Fraudulent transactions can create financial exposure and increase the effort required to monitor payment activity. This project analyzes transaction data from the **IEEE-CIS Fraud Detection dataset** to understand observed fraud patterns, compare fraud rates across transaction segments, and present findings through an interactive Power BI dashboard.

The project follows an end-to-end data analytics workflow, including data inspection, ETL, data cleaning, exploratory data analysis (EDA), statistical outlier identification, KPI development, dashboarding, and business recommendations.

**Project Goal:** Transform raw transaction data into clear, evidence-based insights that help stakeholders identify potentially higher-risk segments and prioritize further investigation.

## 2. Business Questions

This project addresses the following business questions:

- What proportion of transactions are labelled as fraudulent?
- How do fraud rates and fraud volumes differ across product categories?
- How do observed fraud rates vary by card type and card network?
- Do device types or purchaser email domains exhibit different observed fraud patterns?
- How does fraudulent transaction value vary across segments?
- Which segments should be prioritized for further review based on fraud rate, transaction volume, and transaction value?

## 3. Tools and Technologies

| Tool / Technology | Application |
|---|---|
| Python | Data processing and analytical workflow |
| Pandas | Data loading, inspection, cleaning, transformation, and aggregation |
| NumPy | Numerical operations and statistical calculations |
| Microsoft Excel | Initial data inspection and validation |
| IQR Method | Identification of potential numerical outliers for investigation |
| Power BI | Interactive dashboard, KPI cards, slicers, and visual analysis |
| DAX | KPI calculations and analytical measures in Power BI |

*Only describe specific Excel, Python, or DAX tasks as completed if you actually performed them in the project.*

## 4. Dataset

**Source:** [IEEE-CIS Fraud Detection — Kaggle](https://www.kaggle.com/competitions/ieee-fraud-detection/data)

The project uses transaction data and associated identity information from the IEEE-CIS Fraud Detection dataset.

The primary tables are:

- **`train_transaction`** — transaction attributes, transaction amounts, product categories, card information, relative transaction time, and the `isFraud` target.
- **`train_identity`** — identity-related attributes, including device information, associated with a subset of transactions through `TransactionID`.

The identity table contains fewer records than the transaction table. Consequently, some transactions do not have corresponding identity information. These records should not automatically be treated as invalid or removed.

## 5. End-to-End Analytics Workflow

### Step 1: ETL — Extract, Transform, and Load

- Loaded the transaction data into the analysis workflow.
- Selected relevant fields based on the business questions.
- Prepared the data for analysis and reporting.
- Structured the required data for Power BI reporting.

### Step 2: Data Cleaning and Validation

- Inspected column names, data types, and missing values.
- Checked for duplicate records and inconsistent categorical values.
- Reviewed numerical fields, including transaction amounts.
- Examined the relationship between transaction and identity tables.
- Documented material data preparation decisions and their impact on the analysis.

### Step 3: Exploratory Data Analysis (EDA)

- Examined the distribution of fraudulent and non-fraudulent transactions.
- Compared fraud counts and fraud rates across available product categories.
- Analyzed total transaction amounts and fraudulent transaction values.
- Explored patterns by card attributes, device type, purchaser email domain, and relative transaction time where available.
- Compared segment-level fraud rates with transaction volumes to avoid relying on percentages alone.

### Step 4: Statistical Outlier Identification Using IQR

The Interquartile Range (IQR) method can be used to identify potential outliers in numerical variables, such as transaction amounts.

**Formula:**

- IQR = Q3 − Q1
- Lower Bound = Q1 − 1.5 × IQR
- Upper Bound = Q3 + 1.5 × IQR

Values outside these bounds are potential outliers, not automatically data errors or fraudulent transactions.

High-value transactions may be legitimate. Therefore, potential outliers should be investigated before deciding whether to retain, correct, cap, or exclude them. Records should not be removed solely because they fall outside the IQR bounds.

### Step 5: KPI Development

The dashboard reports the following key performance indicators:

| KPI | Definition |
|---|---|
| Total Transactions | Number of transaction records |
| Fraud Transactions | Number of records labelled `isFraud = 1` |
| Fraud Rate | Fraud transactions divided by total transactions |
| Total Transaction Amount | Sum of transaction amounts |
| Fraud Transaction Amount | Sum of transaction amounts for records labelled as fraud |

**Fraud Rate Formula:**

`Fraud Rate (%) = (Fraud Transactions / Total Transactions) × 100`

Fraud transaction amount represents the transaction value associated with records labelled as fraudulent. It should not be interpreted as confirmed financial loss unless supported by actual loss, chargeback, or recovery data.

### Step 6: Power BI Dashboard

The interactive Power BI report presents an overview of fraud performance and enables further exploration through available filters and visualizations.

**Dashboard components include:**

- KPI cards for transaction volume, fraud volume, fraud rate, and transaction amounts.
- Fraud rate comparisons by product category and card attributes.
- Fraudulent transaction value comparisons by card network.
- Fraud transaction trends by relative day.
- Fraud rate comparisons by purchaser email domain.
- Device type and card type slicers for segment-level analysis.

The dashboard separates high-level monitoring from detailed analysis to improve readability and usability.

## 6. Key Results and Observations

The current report displays the following aggregate figures:

| Metric | Reported Value |
|---|---:|
| Total Transactions | 590,540 |
| Fraud Transactions | 20,663 |
| Fraud Rate | 3.50% |
| Total Transaction Amount | 79.74M |
| Fraud Transaction Amount | 3.08M |

*These figures are reported from the current dashboard and should be reconciled against the underlying data and measures before publication.*

### Observed Patterns

**1. Product Category**

Product categories W (11.69%) and C (5.90%) show the highest displayed overall fraud rates in the current report.

**2. Card Network**

Discover (7.73%) has the highest displayed overall fraud rate among the listed card networks.

**3. Mobile and Credit Segment**

The report shows a 13.91% fraud rate for the mobile + credit segment, with 3,312 fraud transactions out of 23,802 transactions.

Within this segment, categories C (20.70%) and S (19.32%) show elevated displayed fraud rates.

**4. Purchaser Email Domain**

The Proton email domain shows a 40.79% observed fraud rate in the current report. The associated transaction count and sample size should be validated before drawing conclusions.

These findings are descriptive observations from the current report. They do not establish that a particular product category, card network, device type, or email domain causes fraud.

Segment-specific fraud rates must also be distinguished from overall fraud rates.

## 7. Business Recommendations

Based on the observed patterns, the following actions may support further risk review:

- Review segments with elevated fraud rates alongside their transaction counts and transaction values.
- Investigate the mobile + credit segment and the product categories highlighted in the report.
- Compare fraud rate, fraud count, and fraudulent transaction value before prioritizing a segment.
- Examine high-rate email-domain groups alongside their sample sizes and other available transaction attributes.
- Treat device type and email domain as contextual indicators rather than standalone reasons to block transactions.
- Validate KPI calculations, filter behaviour, data relationships, and potential false positives before using findings operationally.

These recommendations are intended to support investigation prioritization, not automatic transaction blocking.

## 8. Repository Structure

```text
Fraud-Analysis-Dashboard/
│
├── README.md
│
├── notebooks/
│   └── cleaning.ipynb
│
├── powerbi/
│   └── Fraud Detection.pbix
│
├── Analysis Report/
│   └── Analysis Report.pdf
│
└── Dashboard/
    ├── Fraud Analysis.png
    └── Report of analysis.png
```


## 9. Skills Demonstrated

- End-to-end data analytics workflow
- Data inspection, ETL, and data preparation
- Data cleaning and validation
- Exploratory data analysis using Python, Pandas, and NumPy
- Microsoft Excel for supporting data inspection and validation
- IQR-based potential outlier identification
- KPI development and fraud-rate analysis
- Power BI dashboard design and interactive filtering
- DAX measure development
- Data storytelling and business-oriented interpretation
- Translating analytical findings into risk-review recommendations

## 10. Limitations

- This is a descriptive analytics project, not a real-time fraud detection system or a machine-learning prediction model.
- An observed fraud rate does not establish causation.
- Transaction amount is not necessarily equivalent to confirmed financial loss.
- The identity table covers only a subset of transactions; missing identity information should not automatically be treated as a data error.
- Relative transaction time should not be labelled as a calendar date or weekday unless a valid conversion has been established.
- Small segment sizes may produce unstable or misleadingly high fraud rates.
- Findings should be validated against sample sizes, data definitions, model relationships, filters, and the source dataset before operational use.

## 11. Conclusion

The **Fraud Transaction Analysis & Risk Monitoring** project demonstrates how transaction data can be transformed into business-focused insights using Python, Pandas, NumPy, Microsoft Excel, and Power BI.

By combining data preparation, exploratory analysis, statistical outlier identification, KPI development, and interactive reporting, the project examines fraud patterns across transaction segments and highlights areas that may deserve further investigation.

The primary business value is to help stakeholders compare fraud rates, transaction volumes, and fraudulent transaction values to support more informed and evidence-based review priorities.

---
