# Project Overview

## SAP Procure-to-Pay (P2P) — Full Purchasing Cycle

---

### About This Project

This project is a hands-on demonstration of the SAP Procure-to-Pay (P2P) cycle using the SAP MM (Materials Management) and FI (Financial Accounting) modules. It was created as a capstone project for the SAP Data Analytics Engineering course at KIIT University.

The project follows a real-world business scenario from start to finish — starting from identifying a purchasing need and ending with a vendor payment.

---

### Company Scenario: TechNova Industries Pvt. Ltd.

**Company Name:** TechNova Industries Pvt. Ltd.  
**Industry:** Electronics Manufacturing  
**Location:** Bhubaneswar, Odisha, India  
**Size:** Mid-sized company (~500 employees)  
**SAP System:** SAP ECC 6.0 (simulated environment)

TechNova Industries manufactures consumer electronics and requires regular procurement of raw materials, components, and office supplies. Before SAP implementation, the company used manual processes which caused delays, errors, and financial losses.

**Departments involved:**
- Warehouse / Store (raises purchase requisitions)
- Purchase Department (handles vendor selection and POs)
- Finance / Accounts (handles invoices and payments)

---

### Problem Before SAP

| Problem | Impact |
|---|---|
| Manual requisition approvals via email | Delays of 3–5 days per request |
| No vendor comparison process | Higher procurement costs |
| Paper-based goods receipt | Risk of errors and missing deliveries |
| Manual invoice matching | Duplicate payments to vendors |
| No payment tracking | Cash flow forecasting was impossible |

---

### Solution with SAP P2P

After implementing the SAP P2P process:

- All requisitions are raised digitally with automatic routing
- Vendors are selected based on price and delivery performance
- Goods receipt is recorded in real time updating inventory
- Three-way matching (PO + GR + Invoice) prevents errors
- Automatic payment runs handle vendor payments on schedule

---

### Scope of This Project

This project covers the following SAP activities:

1. **Purchase Requisition (PR)** — Warehouse raises a request for 100 units of microcontroller chips
2. **Request for Quotation (RFQ)** — Purchasing sends RFQ to 3 vendors
3. **Vendor Comparison** — Prices compared, best vendor selected
4. **Purchase Order (PO)** — Formal PO raised and sent to vendor
5. **Goods Receipt (GR)** — Chips arrive, warehouse confirms receipt
6. **Invoice Verification** — Finance verifies vendor invoice against PO and GR
7. **Vendor Payment** — Automatic payment run executed

---

### Tools and Environment

| Tool | Details |
|---|---|
| SAP System | SAP ECC 6.0 / S/4HANA (sandbox) |
| Module | MM (Materials Management), FI (Financial Accounting) |
| Client | 800 (training client) |
| Company Code | TN01 (TechNova Industries) |
| Plant | TN01 (Bhubaneswar Plant) |
| Storage Location | SL01 (Main Warehouse) |

---

### Project Files

| File / Folder | Description |
|---|---|
| `README.md` | Project introduction and overview |
| `docs/project_overview.md` | This file — business context |
| `docs/p2p_process.md` | Step-by-step SAP process guide |
| `screenshots/` | SAP transaction screenshots |
| `report/final_report.md` | Complete academic report |

---

**Author:** Ayush Pradhan  
**Roll No:** 23053271  
**KIIT University**
