# Operational Process Redesign: Accounts Payable (AP) & Three-Way Matching

## 1. Executive Summary
* **Objective:** Eliminate approval bottlenecks, late payment penalties, and manual data-entry errors in a mid-sized international firm's Accounts Payable workflow.
* **Core Problem:** Manual email-based invoice routing caused an average **14.5-day processing cycle**, resulting in missed early-payment discounts (2/10 Net 30) and a **12% exception/rework rate**.
* **Solution:** Redesigned the workflow using automated Optical Character Recognition (OCR) intake, rule-based 3-way matching tolerances, and clear SLA-backed escalation paths.
* **Projected Impact:** Reduced cycle time by **65% (from 14.5 days to 5 days)**, cut manual touchpoints by **60%**, and captured **€48,000+ annually** in early-payment discounts.

---

## 2. "Before" State: Fragmented Manual Workflow
Invoices arrived via multiple unstructured channels, required manual spreadsheet entry, and stalled in department heads' email inboxes without visibility or SLAs.

```mermaid
flowchart TD
    A[Supplier Emails PDF/Paper Invoice] --> B[AP Clerk Manually Downloads & Prints]
    B --> C[Manual Data Entry into ERP]
    C --> D{PO Exists?}
    D -- No --> E[Email Department Head for Ad-Hoc Approval]
    E --> F[Chasing Emails / 5-10 Day Delay]
    D -- Yes --> G[Manual Check of PO vs. Receipt vs. Invoice]
    G --> H{Discrepancy?}
    H -- Yes --> I[Manual Back-and-Forth with Supplier & Warehouse]
    H -- No --> J[Queue for Weekly Batch Payment]
    F --> J
    I --> J
    J --> K[Late Payment Penalties & Missed Discounts]


flowchart TD
    A[Supplier Submits to Dedicated AP Portal / OCR Inbox] --> B[Automated OCR Data Extraction & Duplicate Check]
    B --> C{3-Way Match: PO + Goods Receipt + Invoice}
    C -- Exact Match or Within ±2% Tolerance --> D[Auto-Approved for Scheduled Payment Run]
    C -- Discrepancy > 2% or Missing GRN --> E[Auto-Routed Exception Ticket with 48h SLA]
    E --> F[Owner Resolves in Portal: Warehouse or Buyer]
    F --> C
    D --> G[Payment Executed via ERP Before Day 10]
    G --> H[2% Early Payment Discount Captured & Full Audit Trail Logged]
