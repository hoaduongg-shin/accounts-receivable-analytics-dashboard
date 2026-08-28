# Business Requirements Document (BRD)

## 1. Project Overview

This project develops a Power BI dashboard to support the monitoring and analysis of short-term accounts receivable for a company operating in the postal and delivery industry.

The dashboard focuses on consolidating receivables-related information from the business process, including order processing, shipment, reconciliation, invoicing, and payment. The project uses simulated data covering the period from Q1/2024 to Q4/2025.

The analysis covers receivables status, overdue balances, collection performance, customer payment behavior, and related cash flow risks.

---

## 2. Business Context

Short-term accounts receivable are associated with multiple stages of the company's business operations. Information related to receivables is generated throughout the process from order creation and shipment to reconciliation, invoicing, and payment.

Receivables management therefore requires the monitoring of multiple indicators, including outstanding balances, overdue receivables, payment status, collection performance, and customer payment behavior.

The project proposes a centralized analytical dashboard to organize this information and support monitoring at both an overall and detailed level.

---

## 3. Business Problem

The management of short-term accounts receivable involves data generated from different business activities and processes.

This makes it necessary to consolidate and analyze information in order to:

- Monitor the overall accounts receivable situation.
- Track changes in outstanding and overdue balances.
- Evaluate collection performance.
- Analyze customer payment behavior.
- Identify customers or receivables requiring further attention.
- Support the assessment of potential impacts on cash flow.

---

## 4. Project Objectives

The project aims to:

- Analyze the context and management requirements of short-term accounts receivable.
- Develop a dataset reflecting the receivables-related business process.
- Organize and model data for analysis and visualization.
- Define key performance indicators for receivables and collection management.
- Develop a Power BI dashboard for monitoring and analysis.
- Support the identification of receivables, payment behavior, and collection-related risks.

---

## 5. Stakeholders and Target Users

| Stakeholder / User | Role in the Project | Information Needs |
|---|---|---|
| Accounts Receivable / Finance Team | Primary user | Monitor receivables, overdue balances, invoices, payments, and collection performance. |
| Management | Decision-making user | Monitor the overall receivables situation and identify areas requiring attention. |
| Related Business Units | Supporting users | Access relevant information related to customers, payments, and receivables. |

---

## 6. Project Scope

### In Scope

The project focuses on short-term accounts receivable and related business activities, including:

- Orders and related transactions.
- Shipment and delivery information.
- Reconciliation and revenue-related activities.
- Invoices and payment status.
- Accounts receivable.
- Overdue receivables.
- Customer payment behavior.
- Collection performance.

The analysis period covers **Q1/2024 to Q4/2025**.

### Out of Scope

The project does not include:

- Direct integration with the company's operational systems.
- Real-time data updates.
- Deployment in a production environment.

---

## 7. Business Process

The data model and dashboard are based on the following receivables-related business flow:

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

This process represents the main flow used to track the formation and settlement of receivables.

## 8. Key Business Questions

The dashboard is designed to support the following questions:

### Overall Receivables
- What is the current level of outstanding accounts receivable?
- How are receivables changing over time?
- What proportion of receivables is overdue?
### Collection Performance
- How effective is the collection process?
- How long does it take, on average, to collect receivables?
- How is collection performance changing over time?
### Customer Analysis
- Which customers have the largest outstanding balances?
- Which customers have delayed payment behavior?
- How concentrated are receivables among customers?
### Payment Analysis
- What proportion of payments is made on time or late?
- How are payment patterns changing over time?
- Which invoices remain outstanding or overdue?

9. High-Level Requirements

The dashboard should provide:

| Requirement          | Description                                                                           |
| -------------------- | ------------------------------------------------------------------------------------- |
| Overall monitoring   | Provide an overall view of short-term accounts receivable and collection performance. |
| Customer analysis    | Support analysis of outstanding balances and payment behavior by customer.            |
| Payment analysis     | Monitor payment status, on-time and late payments, and outstanding invoices.          |
| KPI monitoring       | Display key indicators related to receivables and collection performance.             |
| Time-based analysis  | Support analysis of changes and trends over the study period.                         |
| Interactive analysis | Allow users to filter and explore information at different levels of detail.          |

The report is organized into three analytical areas:

- Overview – overall monitoring of accounts receivable.
- Customer – customer-level analysis of receivables and payment behavior.
- Payment – analysis of payment status and collection performance.

## 10. Project Constraints and Limitations

The project uses simulated data developed based on the business process, operational logic, and reference information used in the research.

Therefore:

- The data does not represent actual operational data from the company.
- The dashboard does not provide real-time information.
- The analysis is dependent on the assumptions used when constructing the simulated dataset.
- Some underlying causes of overdue receivables cannot be identified solely from the available data.
- The solution has not been deployed or validated in a production environment.

## Document Status

This BRD documents the business requirements and analytical scope used for the development of the Short-term Accounts Receivable Analytics Dashboard.

The company has been anonymized, and the project is presented for academic and portfolio purposes.
