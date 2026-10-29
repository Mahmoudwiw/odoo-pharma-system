# Odoo 19 ERP for a Pharmaceutical Distribution Company

DEPI Odoo ERP Application Consultant Track - Graduation Project

A complete Odoo 19 implementation for **Pharma Bridge**, a pharmaceutical distributor in Egypt that buys medicines from manufacturers and sells them to pharmacies, hospitals and sub-distributors.

The whole system is built with **standard Odoo configuration only**. No custom code is required.

## Business Problem

The company works with spreadsheets and paper, which causes stock mismatches, expired stock, late collections and no reliable way to trace a batch during a recall.

## What the System Does

| Area | Solution in Odoo 19 |
| --- | --- |
| Batch and expiry control | Lots and Expiration Dates on every medicine |
| Stock rotation | FEFO (First Expiry First Out) removal strategy |
| Cold chain | Cold Storage location (2-8 C) with putaway rules for insulin products |
| Receiving inspection | Quality control point (Pass / Fail) on receipts |
| Returns and expired stock | Quarantine location |
| Customer credit control | Sales Credit Limit with a limit per customer |
| Pricing | Pricelist with quantity discounts for hospitals and distributors |
| Costing | Average cost with automated (perpetual) inventory valuation |
| Traceability | Lot traceability from vendor receipt to customer delivery |

## Modules Used

Inventory, Purchase, Sales, Invoicing / Accounting, Quality, CRM, Contacts.

## Repository Structure

```
.
├── README.md
├── data/
│   ├── partners.csv        # 15 customers and 8 vendors (with credit limits)
│   └── products.csv        # 30 medicines (lot tracking, expiry settings)
├── docs/
│   ├── configuration-guide.md
│   └── test-plan.md
├── presentation/
│   ├── Pharma_Bridge_Presentation.pdf
│   └── Pharma_Bridge_Presentation.pptx   # with transitions and animations
└── screenshots/            # system screenshots
```

The full project documentation (Project Planning, Stakeholder Analysis, Database Design, UI/UX Design) is submitted separately as a PDF link.

## How to Reproduce the System

1. Create an Odoo 19 Enterprise database (the Quality app requires Enterprise).
2. Install: Inventory, Purchase, Sales, Invoicing, CRM, Quality.
3. Follow `docs/configuration-guide.md` step by step.
4. Import `data/partners.csv` from Contacts (Favorites > Import records), then `data/products.csv` from Inventory > Products.
5. Run the scenarios in `docs/test-plan.md`.

## Demo Scenarios

1. Purchase 100 units of one medicine and receive them in two lots with different expiry dates.
2. Pass the receiving quality check and validate the receipt.
3. Receive an insulin product and see it routed to Cold Storage.
4. Sell to a pharmacy and see FEFO reserve the lot that expires first.
5. Try a sale above the customer's credit limit and see the warning.
6. Open the lot traceability report for a recall scenario.

## Data Note

All company names, contacts, phone numbers and prices are sample data created for demonstration only.

## Team

| Name | Role |
| --- | --- |
| Mahmoud Abdelhamid Elmetwally | Team Leader |
| Ahmed Walid | Team Member |
| Mazen Eldeeb | Team Member |
| Abdelrahman Lotfy | Team Member |

Instructor: Ehab Mahmoud

Digital Egypt Pioneers Initiative (DEPI) - Odoo ERP Application Consultant Track
