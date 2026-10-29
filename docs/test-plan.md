# Test Plan (UAT)

| ID | Scenario | Steps | Expected result |
| --- | --- | --- | --- |
| T1 | Receive stock with lots | Confirm a purchase order and receive 100 units split into two lots with different expiry dates | Two lots created with their expiry dates |
| T2 | FEFO picking | Confirm a sale order for 30 units of the same product | The delivery reserves the lot that expires first |
| T3 | Expired lot protection | Try to deliver a lot past its expiry date | The system warns and the lot is not delivered |
| T4 | Credit limit | Confirm a 12,000 EGP order for a customer with a 10,000 EGP limit | A credit limit warning or block appears |
| T5 | Quality check | Validate a receipt with a failed check | The check is failed and the batch can be moved to quarantine |
| T6 | Cold storage | Receive an insulin product | It is suggested for Cold Storage |
| T7 | Invoice and payment | Invoice a delivered order and register the payment | Invoice is paid and the customer balance is zero |
| T8 | Traceability | Open the lot and view its traceability | Vendor receipt and customer deliveries are listed |
| T9 | Access rights | Log in as the warehouse user and as a sales rep | Each user sees only the menus of their role |
| T10 | Reordering | Lower stock under the minimum of a product with a reordering rule | A purchase quotation is proposed |
