# Telecom Customer Churn Data Dictionary

## Dataset overview

This dataset contains customer-level telecommunications records used to analyze churn, customer characteristics, service adoption, contract arrangements and revenue exposure.

- **Unit of analysis:** One customer per row
- **Records analyzed:** 7,043 customers
- **Geographic coverage:** California locations represented in the source data
- **Purpose:** Independent portfolio analysis of customer churn and retention priorities

## Source and usage

- **Dataset title:** Telecom Customer Churn
- **Publisher:** Maven Analytics Data Playground
- **Original source:** IBM Cognos Analytics
- **Dataset URL:** [Telecom Customer Churn dataset](https://mavenanalytics.io/data-playground/telecom-customer-churn)
- **Date accessed:** 2026-09-30
- **Usage:** Public portfolio analysis; review the source page for the applicable dataset terms.

> This repository contains an independent portfolio analysis. It does not contain confidential client or employer data.

## Source fields

| Field | Type | Definition | Example / values |
|---|---|---|---|
| Customer ID | Text | Unique identifier assigned to each customer. | `0002-ORFBO` |
| Gender | Category | Customer gender recorded in the source data. | Male, Female |
| Age | Whole number | Customer age in years. | `37` |
| Married | Boolean/category | Indicates whether the customer is married. | Yes, No |
| Number of Dependents | Whole number | Number of dependents associated with the customer. | `0`, `1`, `2` |
| City | Text | Customer city recorded in the source data. | Los Angeles |
| Latitude | Decimal | Geographic latitude used for mapping. | Decimal coordinate |
| Longitude | Decimal | Geographic longitude used for mapping. | Decimal coordinate |
| Referred a Friend | Boolean/category | Indicates whether the customer referred another customer. | Yes, No |
| Number of Referrals | Whole number | Number of customer referrals. | `0`, `1`, `3` |
| Tenure in Months | Whole number | Number of months the customer has remained with the company. | `6`, `24`, `49` |
| Offer | Category | Promotional offer associated with the customer, where applicable. | Offer A–E, None |
| Phone Service | Boolean/category | Indicates whether the customer subscribes to phone service. | Yes, No |
| Multiple Lines | Boolean/category | Indicates whether the customer has multiple phone lines. | Yes, No |
| Internet Service | Boolean/category | Indicates whether the customer subscribes to internet service. | Yes, No |
| Internet Type | Category | Type of internet service used by the customer. | Cable, DSL, Fiber Optic, None |
| Online Security | Boolean/category | Indicates whether online security service is included. | Yes, No |
| Online Backup | Boolean/category | Indicates whether online backup service is included. | Yes, No |
| Device Protection Plan | Boolean/category | Indicates whether device protection is included. | Yes, No |
| Premium Tech Support | Boolean/category | Indicates whether premium technical support is included. | Yes, No |
| Streaming TV | Boolean/category | Indicates whether streaming television service is included. | Yes, No |
| Streaming Movies | Boolean/category | Indicates whether streaming movie service is included. | Yes, No |
| Streaming Music | Boolean/category | Indicates whether streaming music service is included. | Yes, No |
| Unlimited Data | Boolean/category | Indicates whether unlimited data is included. | Yes, No |
| Contract | Category | Customer contract arrangement. | Month-to-Month, One Year, Two Year |
| Paperless Billing | Boolean/category | Indicates whether the customer uses paperless billing. | Yes, No |
| Payment Method | Category | Customer payment method. | Bank Withdrawal, Credit Card, Mailed Check |
| Monthly Charge | Currency/decimal | Customer's recurring monthly charge. | `$70.00` |
| Total Charges | Currency/decimal | Cumulative service charges recorded for the customer. | Currency value |
| Total Refunds | Currency/decimal | Total refunds issued to the customer. | Currency value |
| Total Extra Data Charges | Currency/decimal | Charges associated with additional data use. | Currency value |
| Total Long Distance Charges | Currency/decimal | Cumulative long-distance charges. | Currency value |
| Total Revenue | Currency/decimal | Total revenue associated with the customer. | Currency value |
| Customer Status | Category | Customer status at the time represented by the dataset. | Stayed, Joined, Churned |
| Churn Category | Category | Broad category assigned to the customer's reason for leaving. | Competitor, Dissatisfaction, Price |
| Churn Reason | Text/category | Specific reported reason for customer churn. | Competitor had better devices |

## Calculated fields used in the dashboard

| Calculated field | Definition / formula | Purpose |
|---|---|---|
| Churned Customer | `1` when Customer Status is Churned; otherwise `0`. | Counts churned customers. |
| Churn Rate | `Churned Customers / Total Customers` | Measures the percentage of customers who churned. |
| Churned Revenue | Sum of Total Revenue for customers with Churned status. | Quantifies revenue associated with churned customers. |
| Age Group | Groups customers into Under 30, 30–44, 45–59 and 60+. | Compares churn across life-stage segments. |
| Referral Group | Groups customers into No Referrals, 1–2 Referrals and 3+ Referrals. | Tests whether referral engagement is associated with churn. |
| Tenure Group | Groups tenure into 0–6, 7–12, 13–24, 25–48 and 49+ months. | Identifies when churn risk is highest in the customer lifecycle. |
| Stayed Customer | `1` when Customer Status is Stayed; otherwise `0`. | Counts established customers who remained. |

## Dashboard control fields

The interactive dashboard provides filters for:

- City
- Age Group
- Contract
- Internet Type
- Number of Dependents
- Married
- Gender

## Data-quality notes

- Blank or not-applicable service fields should be distinguished from explicit `No` values.
- Churn Category and Churn Reason apply primarily to churned customers.
- Geographic fields should be validated before mapping.
- Currency fields should be stored as numeric values rather than formatted text.
- Customer ID should remain unique and should not be aggregated as a measure.

## Dashboard totals used for validation

| Measure | Reported value |
|---|---:|
| Total Customers | 7,043 |
| Churned Customers | 1,869 |
| Stayed Customers | 4,720 |
| Overall Churn Rate | 26.5% |
| Churned Revenue | $3.7M |

> Customers with a `Joined` status account for the difference between Total Customers and the combined Stayed and Churned counts.
