Fraud Transaction Analysis & Risk Monitoring
A Data Analyst Portfolio Project | Python • Pandas • NumPy •
Microsoft Excel • Power BI
Project Overview
Fraudulent transactions can create financial exposure and increase the
effort required to monitor payment activity. This project analyzes
transaction data to understand observed fraud patterns, compare risk
across transaction segments, and present findings in a business-focused
Power BI dashboard.
The project follows an end-to-end analytics workflow: data extraction,
transformation and loading (ETL), data cleaning, exploratory data
analysis (EDA), outlier identification, KPI development, dashboarding,
and business recommendations.
Project goal: Turn raw transaction data into clear, evidence-based
insights that help stakeholders decide which segments may deserve
further investigation.
Business Questions
What proportion of transactions are flagged as fraudulent?
How do fraud rates and fraud volumes differ across product
categories?
How do observed fraud rates vary by card type and card network?
Do device types or purchaser email domains show different observed
fraud patterns?
How does fraudulent transaction value vary across segments?
Which segments should be prioritized for further review, considering
both fraud rate and transaction volume?
Tools & Technologies
---
Tool                                How it was used
---
Python                              Data processing and analytical
workflow
Pandas                              Loading, selecting, cleaning,
transforming, and aggregating data
NumPy                               Numerical operations and
statistical calculations
Microsoft Excel                     Data inspection, validation, and
supporting analysis
IQR Method                          Identifying potential numerical
outliers for investigation
Power BI                            Interactive dashboard, KPI cards,
slicers, and visual analysis
DAX                                 KPI and business-measure
calculations in Power BI
Only describe specific Excel or DAX tasks that you actually performed
in your project.
End-to-End Workflow
1. ETL --- Extract, Transform & Load
Loaded transaction data into the analysis workflow.
Selected fields relevant to the defined business questions.
Prepared data for analysis and reporting.
Structured the output for use in Power BI.
2. Data Cleaning
Inspected data types and missing values.
Checked for duplicate records and inconsistent categorical values.
Reviewed numeric fields and prepared them for analysis.
Kept cleaning decisions aligned with the business purpose and
documented material changes.
3. Exploratory Data Analysis (EDA)
Examined the distribution of fraud and non-fraud transactions.
Compared fraud counts and fraud rates across available categories.
Analyzed transaction amounts and fraudulent transaction amounts.
Explored patterns by card attributes, device type, purchaser email
domain, and relative transaction time where available.
4. Outlier Identification Using IQR
The Interquartile Range (IQR) method was used to flag potential outliers
in numerical data.
IQR = Q3 − Q1
Lower bound = Q1 − 1.5 × IQR
Upper bound = Q3 + 1.5 × IQR
Values outside these bounds are potential outliers, not automatically
data errors or fraud. High-value transactions may be legitimate, so
outliers should be investigated before deciding whether to retain,
correct, cap, or exclude them. Do not remove records solely because they
fall outside the IQR bounds.
5. KPI Development
The dashboard reports the following metrics:
Total Transactions
Fraud Transactions
Fraud Rate
Total Transaction Amount
Fraud Transaction Amount
Fraud Rate = Fraud Transactions ÷ Total Transactions × 100
Fraud transaction amount represents the transaction value associated
with records labelled as fraud. It should not be interpreted as
confirmed financial loss unless loss or recovery data supports that
conclusion.
6. Power BI Dashboard
The dashboard provides an overview of key metrics and allows users to
explore patterns using available slicers and visuals. Detailed analysis
can be presented on a separate report page to keep the main overview
focused.
Key Results From the Current Report
The accompanying report displays the following figures:
Metric                       Reported value
---
Total Transactions                  590,540
Fraud Transactions                   20,663
Fraud Rate                            3.50%
Total Transaction Amount             79.74M
Fraud Transaction Amount              3.08M
Observations reported in the analysis
Product categories W (11.69%) and C (5.90%) show the highest
displayed overall fraud rates in the report.
Discover (7.73%) has the highest displayed overall fraud rate
among the listed card networks.
In the mobile + credit segment, the report shows a 13.91%
fraud rate, with 3,312 fraud transactions out of 23,802
transactions.
Within that mobile + credit segment, categories C (20.70%) and
S (19.32%) show elevated displayed fraud rates.
The report shows a 40.79% observed fraud rate for the Proton
email domain; transaction volume and sample size should be validated
before drawing conclusions.
These are descriptive findings from the current report, not proof that a
category, device, card network, or email domain causes fraud.
Segment-specific rates must not be confused with overall rates.
Business Recommendations
Review segments with elevated fraud rates alongside their
transaction counts and transaction values.
Investigate the mobile + credit segment and the product categories
highlighted in the report.
Compare fraud rate, fraud count, and fraudulent transaction amount
before prioritizing a segment.
Treat email domain and device type as contextual indicators, not
standalone reasons to block transactions.
Validate sample sizes, KPI calculations, filter behaviour, and
potential false positives before using findings operationally.
Repository Structure
``` text
Fraud-Analysis-Dashboard/
├── README.md
├── notebooks/
│   └── cleaning.ipynb
├── powerbi/
│   └── Fraud Detection.pbix
├── Analysis Report/
│   └── Analysis Report.pdf
├── Dashboard/
│   └── Fraud Analysis.png
        Report of analysis.png
Skills Demonstrated
ETL and data preparation
Data cleaning and validation
Exploratory data analysis (EDA)
Python data analysis with Pandas and NumPy
Microsoft Excel for supporting analysis
IQR-based potential outlier identification
KPI calculation and fraud-rate analysis
Power BI dashboard development and data storytelling
Translating analytical findings into business recommendations
Limitations
The dashboard is a descriptive analytics project, not a real-time
fraud detection or machine-learning prediction system.
An observed fraud rate is not proof of causation.
Transaction amount is not necessarily the same as confirmed
financial loss.
Relative time fields should not be labelled as calendar dates or
weekdays unless a valid conversion has been established.
Findings should be validated against sample sizes, filters, data
definitions, and the source dataset before operational use.
Conclusion
This project demonstrates an end-to-end Data Analyst workflow, combining
ETL, data cleaning, EDA, statistical outlier identification, Excel-based
supporting analysis, and Power BI reporting. It converts transaction
data into understandable KPIs and segment-level observations to support
evidence-based fraud review.
