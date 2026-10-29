# Configuration Guide (Odoo 19)

## 1. Installed Apps

Inventory, Purchase, Sales, Invoicing / Accounting, CRM, Contacts, Quality.

## 2. General Settings

Inventory settings:
- Lots & Serial Numbers: enabled
- Expiration Dates: enabled
- Storage Locations: enabled

Invoicing settings:
- Sales Credit Limit: enabled, default limit 20,000 EGP, with blocking when the limit is exceeded

Sales settings:
- Pricelists: enabled

## 3. Product Category

Inventory > Configuration > Product Categories > create **Medicines**:
- Force Removal Strategy: First Expiry First Out (FEFO)
- Costing Method: Average Cost (AVCO)
- Inventory Valuation: Automated (perpetual)

## 4. Locations

Inventory > Configuration > Locations:
- WH/Stock: Removal Strategy FEFO
- Cold Storage (child of WH/Stock): Removal Strategy FEFO, used for insulin products
- Quarantine (child of WH): used for failed batches and returns

## 5. Putaway Rules

Inventory > Configuration > Putaway Rules, from WH/Stock to Cold Storage for:
- Lantus SoloStar Insulin 100 IU
- Humalog Mix 25 KwikPen
- Mixtard 30 Penfill 100 IU

## 6. Quality Control Point

Quality > Quality Control > Control Points > New:
- Title: Receiving Inspection
- Operations: Receipts
- Type: Pass - Fail
- Team: Main Quality Team
- Products: empty (applies to all products)

## 7. Master Data Import

- Contacts > Import records: `data/partners.csv` (customers with credit limits, and vendors)
- Inventory > Products > Import records: `data/products.csv` (medicines tracked by lots with expiry settings)

Expiry columns use Odoo technical names: `use_expiration_date`, `expiration_time`, `use_time`, `removal_time`, `alert_time`.

## 8. Pricelist

Sales > Products > Pricelists > "Hospitals and Distributors":
- 10% discount from 50 units
- 15% discount from 200 units

Assigned to the hospitals and sub-distributors in Contacts > Sales & Purchase tab.

## 9. Company

Settings > Companies > Update Info: company name Pharma Bridge, country Egypt.
