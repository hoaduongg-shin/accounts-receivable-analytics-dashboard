# Data Preparation and Quality

## 1. Overview

The dataset was developed because direct access to the company's operational data was not available.

The data preparation process focused on constructing a simulated dataset, standardizing key fields, and creating analytical variables required for accounts receivable analysis and dashboard development.

---

## 2. Data Simulation Basis

The simulated dataset covers the period from **Q1/2024 to Q4/2025**.

The dataset was developed based on the following principles:

| Basis | Application in the Dataset |
|---|---|
| **Financial reference** | The scale of short-term accounts receivable was referenced from the company's financial reports for 2024 and 2025, including related disclosures on receivables and related parties. |
| **Business logic** | The simulation applied rules related to reconciliation, invoicing, COD payments, debt offsetting, and customer payment cycles under contractual terms. |
| **Operational characteristics** | The data reflects order seasonality, changes in shipment volume, and differences in payment timing among B2B, B2C, and e-commerce customers. |
| **Accounting standards** | Receivables aging and bad debt provision classification follow the principles referenced from Circular 200/2014/TT-BTC. |

---

## 3. Data Preparation Process

### Step 1. Data Construction

The dataset was constructed to reflect the main business and receivables lifecycle:

```text
Order
  ↓
Shipment and Delivery
  ↓
Revenue / Reconciliation
  ↓
Invoice
  ↓
Payment
  ↓
Accounts Receivable
```

The data includes multiple business layers, covering master data, operational transactions, invoices, payments, and accounts receivable.

### Step 2. Encoding and Standardization

Key identifiers were standardized to support relationships between datasets, including:

- `partner_id`
- `order_id`
- `shipment_id`
- `invoice_id`

Business categories were also standardized, including:

- Customer groups.
- Services.
- Locations.
- Shipment status.
- Payment status.

This preparation supports consistent filtering, analysis, and relationships within the dashboard.

### Step 3. Derived Variables

Additional variables were created from the standardized data to support receivables analysis.

These include:

- Remaining accounts receivable balance.
- Days overdue.
- Receivables aging.
- Pending COD.
- Unsettled prepaid amounts.

The standardized data was then used to calculate analytical KPIs, including:

- Days Sales Outstanding (DSO).
- Collection Effectiveness Index (CEI).
- Overdue Receivables Rate.
- Accounts Receivable Turnover.

Detailed KPI definitions and calculation logic are documented separately in `07-kpi-definition.md`.

## 4. Data Quality Considerations

Because the dataset consists of multiple related business tables, consistency between records and relationships is important for analysis.

The preparation process therefore focused on:

- Standardizing identifiers used to link tables.
- Standardizing business categories and status fields.
- Ensuring the consistency of relationships between operational transactions, invoices, and payments.
- Creating derived variables from standardized data before KPI calculation.

Data quality in this project is considered primarily in relation to the consistency and analytical usability of the simulated dataset.

5. Output

After preparation, the dataset was used as the input for:

```
Standardized Data
        ↓
Derived Variables
        ↓
Data Relationships
        ↓
KPI Calculation
        ↓
Power BI Dashboard
```

The prepared data supports the analysis of customer receivables, COD, service-related receivables, prepaid amounts, payment behavior, and receivables trends.

The detailed table structure is documented in `05-data-dictionary.md`, while the relationships between datasets are described in `06-data-model.md`.

## 6. Limitations

The dataset is simulated for academic and analytical purposes.

Therefore:

- The values and transaction patterns are based on predefined rules and assumptions.
- The dataset does not represent actual operational data from the company.
- Data quality is assessed within the context of the simulated data construction and analytical requirements.
- The results should not be interpreted as the company's actual financial or operational performance.
