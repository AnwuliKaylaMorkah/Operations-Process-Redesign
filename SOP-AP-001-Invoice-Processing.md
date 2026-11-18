# Standard Operating Procedure: Automated Invoice Intake & 3-Way Matching
**Document ID:** SOP-AP-001  
**Version:** 2.0 (Post-Redesign)  
**Process Owner:** Business Operations & Finance Controls  
**Target SLA:** 5 Business Days (Receipt to Payment Scheduling)

---

## 1. Purpose & Scope
This SOP defines the standardized workflow for receiving, validating, approving, and scheduling supplier invoices for payment. It applies to all operational entities and ensures strict segregation of duties, audit readiness, and working capital optimization.

## 2. Roles & Prerequisites
* **ERP / AP Automation System:** Configured with OCR capture and automated 3-way matching.
* **Valid Purchase Order (PO):** Required for all non-recurring spend above €500.
* **Goods Received Note (GRN):** Must be logged by Warehouse/Operations within 24 hours of delivery.

## 3. Step-by-Step Procedure

### Step 1: Centralized Intake & Validation (Day 0)
1. All supplier invoices must be submitted electronically to `invoices@company.com` or directly via the Supplier Portal.
2. OCR software extracts Header Data (Supplier Name, VAT ID, Invoice #, Date, Total) and Line-Item Data.
3. System automatically runs a **Duplicate Check** (matching Supplier ID + Invoice Number + Amount). Duplicates are auto-rejected with an automated email notification to the vendor.

### Step 2: Automated Three-Way Matching (Day 1)
The system cross-references the **Supplier Invoice** against the **Purchase Order (PO)** and the **Goods Received Note (GRN)**:
* **Straight-Through Processing (STP):** If line items match 100% (or fall within the approved **±2% / €50 price variance tolerance**), the invoice bypasses manual review and moves directly to Step 4.
* **Exception Flagging:** If quantity mismatches or price variances exceed ±2%, the invoice is placed on `Hold - Exception` and routed to the appropriate owner.

### Step 3: Exception Resolution & Escalation (Days 2–3)
* **Missing GRN:** System notifies the Receiving/Warehouse Lead. Must be confirmed within **24 business hours**.
* **Price Variance (>2%):** System routes a ticket to the Procurement Buyer to either issue a PO amendment or request a Credit Note from the supplier within **48 business hours**.
* **SLA Escalation:** Any exception unresolved after 48 hours automatically escalates to the Operations Team Lead.

### Step 4: Payment Scheduling & Audit Trail (Days 4–5)
1. Approved invoices are batched according to payment terms (`2/10 Net 30` prioritized to capture early-payment discounts).
2. Finance Manager reviews and releases the payment batch (enforcing Segregation of Duties: invoice approvers cannot release bank payments).
3. All timestamps, user approvals, and variance notes are archived in the ERP for external audit compliance.
