# Dashboard Design

## 1. Overview

The dashboard was developed to support the monitoring and analysis of short-term accounts receivable for a postal and delivery enterprise.

The design follows an analytical flow from the overall receivables position to customer-level analysis and payment behavior:

```text
Overview
   ↓
Customer
   ↓
Payment
```

This structure addresses three main questions:

1. How much receivables are currently outstanding?
2. Which customers contribute to outstanding and overdue receivables?
3. How are customers fulfilling their payment obligations?

The dashboard is designed according to a three-level information structure:

```
Overview KPIs
     ↓
Detailed Analysis
     ↓
Cause Analysis
```

## 2. Dashboard Structure

The system consists of three analytical pages.

| Dashboard    | Main Focus                                                                         |
| ------------ | ---------------------------------------------------------------------------------- |
| **Overview** | Overall receivables position, collection efficiency, and overdue debt risk.        |
| **Customer** | Outstanding balances, overdue receivables, and collection performance by customer. |
| **Payment**  | Customer payment behavior, payment timing, and operational receivables.            |

The three pages are connected through a continuous analytical flow, allowing users to move from the overall receivables position to customer-level details and payment behavior.

## 3. Overview Dashboard

The Overview Dashboard provides a general view of short-term accounts receivable and collection performance.

The main analysis focuses on:

- Total short-term accounts receivable.
- Current and overdue receivables.
- Days Sales Outstanding (DSO).
- Collection Effectiveness Index (CEI).
- Changes in receivables over time.

The purpose of this page is to help users quickly assess the scale of receivables, the level of overdue debt, and the overall efficiency of collection.

The Overview Dashboard provides the starting point for further investigation when indicators show signs of receivables or cash flow risk.

## 4. Customer Dashboard

The Customer Dashboard focuses on the contribution of individual customers to the overall receivables position.

The analysis includes:

- Customer outstanding balances.
- Overdue receivables by customer.
- Collection performance.
- Receivables structure by fee type.
- Customers with a high proportion of outstanding invoices.

This page supports the identification of customers that contribute significantly to outstanding or overdue receivables.

The analysis in the project also showed that receivables were concentrated primarily in Delivery-related fees, while several customers had relatively high outstanding invoice rates.

## 5. Payment Dashboard

The Payment Dashboard focuses on customer payment behavior and operational receivables.

The main analysis includes:

- Customers making on-time payments.
- Customers making late payments.
- Payment history and trends over time.
- COD-related receivables.
- Prepaid amounts to suppliers.
- Other operational receivables.

This page is used to evaluate compliance with payment terms, identify delayed payment behavior, and monitor receivables related to operational cash flows.

## 6. Interaction and Context

The dashboard includes interactive features to support different levels of analysis.

These include:

- Slicers for time, customer, and receivables categories.
- Drill-down for detailed analysis.
- Drill-through from summary information to specific customers or receivables.
- Tooltips for additional KPI and visual context.

Charts also include supporting elements such as target lines, KPI explanations, and clear measurement units where applicable.

## 7. Design Principles

The dashboard design follows several principles described in the project:

- Information is organized from summary to detail.
- The number of visuals is limited to avoid information overload.
- KPIs, detailed explanations, and cause analysis are presented in separate information layers.
- Colors and conditional indicators are used to support the identification of performance and risk.
- Interactive functions allow users to move from an overall view to detailed analysis.

8. Analytical Outcome

The dashboard supports the identification of key issues in short-term receivables management.

Based on the simulated data analysis for 2025:

- Total accounts receivable reached approximately VND 1,667 billion.
- Overdue receivables accounted for 53.04% of total receivables.
- DSO reached 28 days, exceeding the reference credit policy threshold of approximately 25 days.
- CEI reached 95.22%, indicating relatively effective collection performance, although delayed payments remained concentrated among large customers with more flexible credit terms.

These results demonstrate the analytical flow of the dashboard: identifying the overall receivables position, locating the main sources of risk, and examining customer payment behavior.

> All analytical results are based on the simulated dataset developed for this project and do not represent the actual financial or operational performance of any company.

9. Dashboard Navigation

```
┌─────────────┐
│  OVERVIEW   │
│             │
│ • AR Scale  │
│ • Overdue   │
│ • DSO       │
│ • CEI       │
└──────┬──────┘
       │
       ▼
┌─────────────┐
│  CUSTOMER   │
│             │
│ • Balance   │
│ • Overdue   │
│ • Fee Type  │
│ • Risk      │
└──────┬──────┘
       │
       ▼
┌─────────────┐
│   PAYMENT   │
│             │
│ • On-time   │
│ • Late      │
│ • COD       │
│ • Prepaid   │
└─────────────┘
```

The dashboard navigation follows the same analytical sequence used throughout the project: overall receivables → customer analysis → payment behavior.
