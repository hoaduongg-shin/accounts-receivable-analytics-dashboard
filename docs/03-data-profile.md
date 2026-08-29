# Data Profile

## 1. Dataset Overview

This project uses a simulated dataset developed to support the analysis of short-term accounts receivable for a company operating in the postal and delivery industry.

The dataset covers the period from **Q1/2024 to Q4/2025** and was constructed based on:

- The business process related to order fulfillment and accounts receivable.
- Operational characteristics of the postal and delivery industry.
- Reference information from financial reports.
- Business logic used to simulate transactions, invoices, payments, and receivables.

The dataset is intended to provide a consistent data foundation for dashboard development and accounts receivable analysis. It does not contain actual operational data from the company.

---

## 2. Business Process Coverage

The dataset reflects the main business flow related to the formation and settlement of accounts receivable:

```text
Order
  ↓
Shipment
  ↓
Reconciliation
  ↓
Invoice
  ↓
Payment
  ↓
Accounts Receivable
```

Data is generated and linked across these stages to support the tracking of receivables from the underlying transaction to invoice issuance and payment.

## 3. Data Scope

The dataset covers information related to:

- Customers and business partners.
- Orders and delivery transactions.
- Shipments and operational events.
- Reconciliation and revenue-related information.
- Invoices and payment due dates.
- Customer payments.
- Outstanding and overdue receivables.

The data is structured to support analysis across different levels, including overall receivables, customer-level performance, and payment behavior.

## 4. Dataset Construction

As direct access to the company's operational data was not available, the dataset was simulated based on the business logic and relationships identified during the research.

The simulation considers:

- The relationships between orders, shipments, invoices, and payments.
- Customer payment terms and due dates.
- The formation and settlement of outstanding receivables.
- Differences in customer payment behavior.
- Changes in receivables and payments over time.
- Operational characteristics relevant to the postal and delivery industry.

The objective was to create a dataset that reflects the main analytical relationships required for accounts receivable management rather than to reproduce actual company transactions.

## 5. Data Structure

The dataset includes both business entities and transactional data.

The main data groups include:

| Data Group           | Description                                                                                                       |
| -------------------- | ----------------------------------------------------------------------------------------------------------------- |
| **Master Data**      | Core entities used to describe the business context, such as customers, services, branches, employees, and dates. |
| **Operational Data** | Data generated during business operations, including orders, shipments, delivery tracking, and shipment events.   |
| **Receivables Data** | Data related to reconciliation, invoices, payments, outstanding balances, and overdue receivables.                |
| **Analytical Data**  | Supporting data used for KPI calculation, trend analysis, aging analysis, and dashboard reporting.                |

These datasets are connected through business identifiers and relationships that reflect the receivables lifecycle.

## 6. Analytical Dimensions

The data supports analysis across several dimensions:

- Time – analysis by date, month, quarter, and year.
- Customer – analysis of receivables and payment behavior by customer.
- Service – analysis by service or business category.
- Branch / Region – analysis across organizational or geographical units.
- Receivables Status – analysis of outstanding, overdue, and settled receivables.
- Payment Status – analysis of on-time and late payments.

## 7. Data Characteristics

The simulated dataset was designed to include characteristics relevant to accounts receivable analysis, including:

- Variations in transaction volume over time.
- Different customer groups and payment behaviors.
- Outstanding invoices and overdue receivables.
- Differences between on-time and late payments.
- Relationships between operational transactions and financial settlement.
- Receivables aging based on payment status and due dates.

These characteristics support the calculation of key performance indicators and the identification of patterns related to receivables and collection performance.

8. Data Usage

The dataset is used throughout the project for:

```
Data Simulation
      ↓
Data Preparation
      ↓
Data Modeling
      ↓
KPI Calculation
      ↓
Dashboard Development
      ↓
Business Analysis
```

The detailed data preparation and quality considerations are documented in `04-data-preparation-and-quality.md`, while the structure and relationships between tables are described in `06-data-model.md`.

## 9. Data Limitation

The dataset is simulated and was developed for academic and analytical purposes.

Therefore:

- It does not represent actual operational data from the company.
- The values and transaction patterns are based on predefined business rules and assumptions.
- The analysis results should be interpreted within the context of the simulated dataset.
- The dataset is intended to demonstrate the use of business intelligence techniques for accounts receivable analysis rather than evaluate the actual financial performance of the company.
