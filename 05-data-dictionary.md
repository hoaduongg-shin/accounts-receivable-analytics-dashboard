# Data Dictionary

## 1. Overview

This document describes the main datasets and fields used in the Short-term Accounts Receivable Analytics Dashboard.

The data model includes master data, operational transactions, receivables-related transactions, and monthly summary tables. The structure reflects the business flow from order creation to invoicing, payment, and accounts receivable analysis.

> The company and selected implementation details have been anonymized. This document describes the data structure used for analysis and does not disclose the underlying data generation rules.

---

## 2. Dataset Groups

| Data Group | Tables | Purpose |
|---|---|---|
| Master Data | `partner`, `contract`, `dim_service`, `dim_location`, `dim_date` | Provides descriptive information used for filtering and grouping. |
| Operational Data | `order`, `shipment` | Records the main operational activities related to order fulfillment and delivery. |
| Receivables Data | `invoice`, `invoice_line`, `payment`, `payment_allocation`, `cod`, `settlement` | Supports the tracking of invoicing, payment, COD, reconciliation, and receivables settlement. |
| Monthly Summary Data | `monthly_ar_customer`, `monthly_ar_other`, `monthly_ar_prepaid` | Supports monthly receivables monitoring and KPI analysis. |

---

## 3. Master Data

### 3.1 `partner`

Contains information about customers or business partners involved in receivables-related transactions.

| Field | Description |
|---|---|
| `partner_id` | Unique identifier of the partner. |
| Partner attributes | Descriptive information used to classify and analyze customers or business partners. |

---

### 3.2 `contract`

Contains contract-related information associated with business partners and payment arrangements.

| Field | Description |
|---|---|
| Contract identifier | Unique identifier of the contract. |
| Partner reference | Identifies the related business partner. |
| Contract attributes | Information used to support the analysis of contractual and payment relationships. |

---

### 3.3 `dim_service`

Contains the service categories used in operational and receivables analysis.

| Field | Description |
|---|---|
| Service identifier | Unique identifier of the service. |
| Service attributes | Descriptive information used to classify services. |

---

### 3.4 `dim_location`

Contains location or organizational information used for geographical and operational analysis.

| Field | Description |
|---|---|
| Location identifier | Unique identifier of the location. |
| Location attributes | Information used to classify locations or operational areas. |

---

### 3.5 `dim_date`

Contains calendar information used for time-based analysis.

| Field | Description |
|---|---|
| Date key | Unique identifier for the date. |
| Date attributes | Calendar information used for analysis by day, month, quarter, and year. |

---

## 4. Operational Data

### 4.1 `order`

Represents the initial business transaction and acts as a central entity in the operational flow.

| Field | Description |
|---|---|
| `order_id` | Unique identifier of the order. |
| `partner_id` | Identifies the customer or business partner associated with the order. |
| Related references | Links the order to relevant service, location, contract, and operational information. |
| Order attributes | Information describing the order and its business status. |

---

### 4.2 `shipment`

Contains delivery and shipment information generated from the order process.

| Field | Description |
|---|---|
| `shipment_id` | Unique identifier of the shipment. |
| `order_id` | Identifies the related order. |
| Shipment attributes | Information related to shipment status and operational processing. |
| Related references | Links the shipment to relevant operational dimensions. |

---

## 5. Receivables and Settlement Data

### 5.1 `invoice`

Contains invoice-level information used to track receivables.

| Field | Description |
|---|---|
| `invoice_id` | Unique identifier of the invoice. |
| `partner_id` | Identifies the partner associated with the invoice. |
| `issue_date` | Date on which the invoice was issued. |
| `flow_direction` | Indicates the direction of the transaction, including receivables-related records. |
| Invoice attributes | Additional information related to invoice status and settlement. |

---

### 5.2 `invoice_line`

Contains detailed monetary amounts associated with each invoice.

| Field | Description |
|---|---|
| Invoice reference | Identifies the related invoice. |
| `amount` | Monetary amount recorded for the invoice line. |
| Line attributes | Additional information describing the invoice component. |

Invoice-level values can be derived by aggregating `amount` by `invoice_id`. :contentReference[oaicite:1]{index=1}

---

### 5.3 `payment`

Contains records of payments received from customers or business partners.

| Field | Description |
|---|---|
| `payment_id` | Unique identifier of the payment. |
| `partner_id` | Identifies the partner making the payment. |
| `payment_date` | Date on which the payment was recorded. |
| `amount` | Amount received. |
| `method` | Payment method. |

The payment structure in the dataset is linked to individual invoices through the `payment_allocation` table. :contentReference[oaicite:2]{index=2}

---

### 5.4 `payment_allocation`

Maps payments to invoices.

| Field | Description |
|---|---|
| `allocation_id` | Unique identifier of the payment allocation. |
| `payment_id` | Identifies the related payment. |
| `invoice_id` | Identifies the invoice receiving the payment allocation. |
| `amount` | Amount allocated from the payment to the invoice. |

This table is used to determine how much of an invoice has been settled and to calculate the remaining receivable balance. :contentReference[oaicite:3]{index=3}

---

### 5.5 `cod`

Contains information related to cash-on-delivery transactions.

The table supports the monitoring of COD amounts and their settlement status within the broader receivables process.

---

### 5.6 `settlement`

Contains reconciliation and settlement-related records.

The table supports the tracking of transactions that require reconciliation or settlement before the related receivable position is finalized.

---

## 6. Monthly Accounts Receivable Tables

### 6.1 `monthly_ar_customer`

Contains monthly customer accounts receivable information.

| Field | Description |
|---|---|
| `month_end` | Reporting date for the monthly balance. |
| `opening_balance` | Accounts receivable balance at the beginning of the period. |
| `invoice_in_month` | Receivables generated from invoices during the month. |
| `payment_in_month` | Payments allocated during the month. |
| `ar_customer_balance` | Closing customer accounts receivable balance. |

The monthly balance follows the relationship:

```text
Closing Balance
= Opening Balance
+ Invoice Amount
- Payment Amount
```

The fields used in this monthly table are reflected in the data generation and calculation process.

### 6.2 `monthly_ar_other`

Contains monthly information for other short-term receivables.

The table is used to support trend monitoring and KPI analysis for receivables outside the main customer receivables group.

### 6.3 `monthly_ar_prepaid`

Contains monthly information related to prepaid amounts that have not yet been fully settled.

The table supports the monitoring and analysis of prepaid balances within the short-term receivables scope.

## 7. Key Identifiers

The main identifiers used to establish relationships between datasets include:

| Identifier      | Primary Usage                                                         |
| --------------- | --------------------------------------------------------------------- |
| `partner_id`    | Identifies customers or business partners.                            |
| `order_id`      | Identifies orders and related operational transactions.               |
| `shipment_id`   | Identifies shipment records.                                          |
| `invoice_id`    | Identifies invoices and related invoice lines or payment allocations. |
| `payment_id`    | Identifies payments and their allocations.                            |
| `allocation_id` | Identifies individual payment-to-invoice allocations.                 |

These identifiers are standardized to support relationships across operational, payment, and receivables data.

## 8. Data Usage

The datasets support the following analytical flow:

```
Master Data
     +
Operational Transactions
     +
Invoices
     +
Payments and Allocations
        ↓
Accounts Receivable Analysis
        ↓
Monthly Monitoring
        ↓
KPI Calculation
        ↓
Dashboard Reporting
```

The detailed relationships between these tables are documented in [`06-data-model.md`](06-data-model.md).
