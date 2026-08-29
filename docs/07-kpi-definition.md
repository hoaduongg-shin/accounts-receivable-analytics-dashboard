# KPI Definitions

## 1. Overview

The dashboard uses 11 KPIs to monitor short-term accounts receivable, collection performance, customer receivables, and payment behavior.

The KPI framework is organized into three analytical areas:

- Overview
- Customer
- Payment

The selected indicators focus on receivables scale, collection efficiency, overdue risk, and customer payment behavior.

---

## 2. KPI Framework

| Analytical Area | Focus |
|---|---|
| **Overview** | Overall receivables position, collection performance, and overdue risk. |
| **Customer** | Outstanding balances, overdue receivables, and collection performance by customer. |
| **Payment** | Payment status, payment timing, and compliance with credit terms. |

---

## 3. Overview KPIs

| KPI | Definition | Business Purpose |
|---|---|---|
| **Total Accounts Receivable** | Total outstanding short-term receivables at the reporting date. | Monitor the overall scale of receivables. |
| **Overdue Receivables Rate** | The proportion of receivables that remain unpaid after the due date. | Assess overdue debt risk. |
| **Days Sales Outstanding (DSO)** | The average number of days required to collect receivables. | Evaluate collection speed. |
| **Collection Effectiveness Index (CEI)** | Measures the effectiveness of receivables collection during the reporting period. | Evaluate collection performance. |

These indicators provide an overall view of receivables scale, collection efficiency, and overdue risk. :contentReference[oaicite:1]{index=1}

---

## 4. Customer KPIs

| KPI | Definition | Business Purpose |
|---|---|---|
| **Customer Outstanding Balance** | The remaining receivable balance associated with each customer. | Identify customers with significant outstanding balances. |
| **Customer Overdue Balance** | The portion of a customer's receivables that has exceeded the payment due date. | Identify customers contributing to overdue debt. |
| **Customer Collection Performance** | Collection results analyzed at the customer level. | Compare collection performance across customers. |
| **Receivables Concentration** | The extent to which receivables are concentrated among major customers. | Identify concentration risk. |

Customer-level analysis supports the identification of customers with large outstanding balances, overdue receivables, or delayed payment behavior.

---

## 5. Payment KPIs

| KPI | Definition | Business Purpose |
|---|---|---|
| **Outstanding Invoice Rate** | The proportion of invoices that remain unpaid. | Monitor the level of unsettled invoices. |
| **On-time Payment Customers** | The number of customers making payments within the agreed payment period. | Monitor compliance with payment terms. |
| **Late Payment Customers** | The number of customers making payments after the agreed payment period. | Identify delayed payment behavior. |

The payment analysis focuses on outstanding invoices and the distinction between on-time and late payment behavior. :contentReference[oaicite:2]{index=2}

---

## 6. KPI Relationships

The KPIs are intended to be interpreted together rather than independently.

```text
Accounts Receivable
        ↓
Outstanding and Overdue Balances
        ↓
Collection Performance
   ┌──────────────┐
   │     DSO      │
   │     CEI      │
   └──────────────┘
        ↓
Customer Analysis
        ↓
Payment Behavior
   ┌──────────────┐
   │   On-time    │
   │     Late     │
   └──────────────┘
```

For example, a high overdue receivables rate may be examined further through DSO, CEI, customer outstanding balances, and payment behavior.

## 7. Analytical Use

The KPI framework supports analysis from the overall receivables position to customer and payment-level details.

```
Overview
   ↓
What is the current receivables position?

Customer
   ↓
Which customers contribute to outstanding or overdue receivables?

Payment
   ↓
How are customers fulfilling their payment obligations?
```

This structure follows the three-page dashboard design described in the project: Overview → Customer → Payment.

## 8. Implementation

The KPIs were implemented in Power BI using DAX measures and calculated from the simulated data model.

Monthly receivables summary tables were used to support KPI calculation and trend analysis over the reporting period.

> Implementation: The KPIs were implemented as DAX measures in Power BI. The detailed calculation logic is maintained within the Power BI (.pbix) file and is not included in the public repository.
