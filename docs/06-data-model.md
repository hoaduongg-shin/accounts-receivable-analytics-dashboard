# Data Model

## 1. Overview

The data model supports the analysis of short-term accounts receivable across the business process from order creation to invoicing, payment, and receivables monitoring.

The model contains multiple fact tables representing different business processes and analytical purposes. These fact tables are connected to shared dimension tables, allowing data to be analyzed across common dimensions such as customers, services, locations, contracts, and time.

Therefore, the model is designed as a **Galaxy Schema (Fact Constellation)**.

![Data_model](images/data_model.png)

---

## 2. Modeling Approach

A Galaxy Schema consists of multiple fact tables that share common dimension tables.

In this project, different business processes are represented through separate transactional and summary tables, including:

- Operational transactions.
- Shipment activities.
- Invoicing.
- Payments and payment allocation.
- COD and settlement activities.
- Monthly accounts receivable snapshots.

These tables are connected to shared dimensions where applicable, allowing the dashboard to analyze accounts receivable from different perspectives.

```text
                 SHARED DIMENSIONS
       ┌──────────────┼──────────────┐
       │              │              │
    Partner        Service        Location
       │              │              │
    Contract          Date       Other Attributes
       │
       ▼
        MULTIPLE FACT / TRANSACTION TABLES
       │
 ┌─────┼─────────┬──────────┬──────────────┐
 │     │         │          │              │
Order Shipment  Invoice   Payment         COD
 │               │          │
 │               └────┬─────┘
 │                    │
 │           Payment Allocation
 │
 └──────────── Settlement

       ↓

     MONTHLY AR SNAPSHOTS

 ┌────────────────┬────────────────┬────────────────┐
 │                │                │
monthly_ar_customer monthly_ar_other monthly_ar_prepaid
```

## 3. Dimension Tables

Dimension tables provide descriptive attributes used for filtering, grouping, and analyzing data across multiple business processes.

| Table          | Role                                                                |
| -------------- | ------------------------------------------------------------------- |
| `partner`      | Stores information about customers and business partners.           |
| `contract`     | Stores contract information associated with business relationships. |
| `dim_service`  | Stores service categories.                                          |
| `dim_location` | Stores location or operational area information.                    |
| `dim_date`     | Provides calendar attributes for time-based analysis.               |

These dimensions can be shared across different transactional and analytical tables.

## 4. Operational and Transactional Tables

The operational layer represents business activities related to the formation of receivables.

| Table        | Role                                                             |
| ------------ | ---------------------------------------------------------------- |
| `order`      | Represents the initial business transaction.                     |
| `shipment`   | Records shipment and delivery activities associated with orders. |
| `cod`        | Records cash-on-delivery related transactions.                   |
| `settlement` | Records reconciliation and settlement activities.                |

These tables represent different stages of the operational process that may contribute to the formation and settlement of accounts receivable.

## 5. Receivables and Payment Tables

The receivables layer supports the monitoring of invoicing and payment settlement.

| Table                | Role                                                           |
| -------------------- | -------------------------------------------------------------- |
| `invoice`            | Records receivables generated from invoicing activities.       |
| `invoice_line`       | Stores detailed monetary components associated with invoices.  |
| `payment`            | Records payments received from customers or business partners. |
| `payment_allocation` | Maps payment amounts to individual invoices.                   |

The `payment_allocation` table acts as a bridge between payments and invoices, allowing payments to be allocated to one or more invoices.

This structure supports the calculation of paid amounts, outstanding balances, and receivables status.

## 6. Monthly Accounts Receivable Snapshot Tables

In addition to transactional data, the model includes monthly summary tables for monitoring accounts receivable over time.

| Table                 | Role                                                                   |
| --------------------- | ---------------------------------------------------------------------- |
| `monthly_ar_customer` | Stores monthly customer accounts receivable balances and movements.    |
| `monthly_ar_other`    | Stores monthly balances for other short-term receivables.              |
| `monthly_ar_prepaid`  | Stores monthly balances related to prepaid amounts pending settlement. |

These tables support KPI calculation and trend analysis at the monthly level.

## 7. Main Relationships

The model uses business identifiers to connect dimensions and transactional tables.

```
partner
   │
   ├──────< contract
   │
   ├──────< order
   │           │
   │           └──────< shipment
   │
   └──────< invoice
                 │
                 └──────< invoice_line


payment
   │
   └──────< payment_allocation >────── invoice
```

The main identifiers include:

| Identifier      | Primary Usage                                                       |
| --------------- | ------------------------------------------------------------------- |
| `partner_id`    | Connects customers and business partners with related transactions. |
| `contract_id`   | Connects contract-related information with business activities.     |
| `order_id`      | Connects orders with related operational transactions.              |
| `shipment_id`   | Identifies shipment records.                                        |
| `invoice_id`    | Connects invoices with invoice details and payment allocations.     |
| `payment_id`    | Connects payments with payment allocations.                         |
| `allocation_id` | Identifies individual payment-to-invoice allocations.               |

8. Analytical Flow

The Galaxy Schema supports analysis across multiple business processes.

```
Shared Dimensions
        ↓
Operational Transactions
        ↓
Invoices and Receivables
        ↓
Payments and Settlement
        ↓
Monthly AR Snapshots
        ↓
KPI Calculation
        ↓
Dashboard Analysis
```

This structure allows the dashboard to analyze accounts receivable from both transactional and aggregated perspectives.

## 9. Data Model Design

The model separates different business processes into multiple related tables instead of storing all information in a single fact table.

This approach supports:

- Analysis across different stages of the business process.
- Shared analysis dimensions such as customer, service, location, and time.
- Separate handling of operational, invoicing, payment, and settlement activities.
- Monthly monitoring of accounts receivable balances.

The resulting structure is a Galaxy Schema (Fact Constellation) consisting of multiple fact or transaction tables connected through shared dimensions and business identifiers.

## 10. Data Model Diagram

The complete relationship structure is illustrated in the project's data model diagram.

> The diagram focuses on the analytical relationships between datasets. Internal data generation rules and implementation details are not included in the public repository.
