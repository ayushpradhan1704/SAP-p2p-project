# Screenshot Guide

## SAP P2P Project — Screenshot Documentation

This guide explains what screenshots to take, when to take them, how to name the files, and where to store them.

---

## Where to Store Screenshots

All screenshots go in the `/screenshots` folder in the project root.

```
sap-p2p-project/
└── screenshots/
    ├── 01_ME51N_PR_creation.png
    ├── 02_ME41_RFQ_creation.png
    ├── 03_ME49_vendor_comparison.png
    ├── 04_ME21N_PO_creation.png
    ├── 05_MIGO_goods_receipt.png
    ├── 06_MIRO_invoice_verification.png
    ├── 07_F110_payment_run.png
    └── 08_document_flow.png
```

---

## File Naming Convention

Use this exact format: `[step number]_[tcode]_[short description].png`

- Always use lowercase
- Use underscores, not spaces
- Number the steps (01, 02, 03...) so they stay in order

---

## Screenshot-by-Screenshot Guide

---

### Screenshot 1 — Purchase Requisition

**File:** `01_ME51N_PR_creation.png`  
**T-Code:** ME51N  
**When to take it:** After filling in all fields but before saving, AND after saving (to show PR number)

**What should be visible:**
- The ME51N screen with material entered (CHIP-ATM-328P)
- Quantity: 100 EA
- Required delivery date: 15.04.2026
- Plant: TN01
- Storage Location: SL01
- The PR number displayed at the bottom after saving (e.g., "Purchase requisition 1000012345 created")

**Tip:** Take one screenshot before saving and one after so you can show both the input and the confirmation.

---

### Screenshot 2 — Request for Quotation

**File:** `02_ME41_RFQ_creation.png`  
**T-Code:** ME41  
**When to take it:** After entering the RFQ details with vendor info visible

**What should be visible:**
- The RFQ header screen showing quotation deadline
- The vendor list tab showing all three vendors (MicroElec, ChipWorld, TechParts)
- Material and quantity in the line items
- RFQ document number after saving

**Tip:** If possible, take a screenshot of all three vendor line items visible on one screen.

---

### Screenshot 3 — Vendor Comparison

**File:** `03_ME49_vendor_comparison.png`  
**T-Code:** ME49  
**When to take it:** After all vendor quotes are entered and the comparison report is generated

**What should be visible:**
- The price comparison table with all three vendors side by side
- Prices clearly visible for each vendor
- The best (lowest price) vendor visually highlighted or selected
- Total value column showing the difference between vendors

**Tip:** This is one of the most visually impactful screenshots — make sure the comparison table is fully visible.

---

### Screenshot 4 — Purchase Order

**File:** `04_ME21N_PO_creation.png`  
**T-Code:** ME21N  
**When to take it:** After PO is filled and saved

**What should be visible:**
- Vendor field: ChipWorld India
- Material: CHIP-ATM-328P
- Quantity: 100 EA
- Net Price: ₹138
- Total value: ₹13,800
- Delivery date: 12.04.2026
- PO number in the header after saving

**Tip:** Take a screenshot of both the header tab (vendor, payment terms) and the item detail tab (price, quantity).

---

### Screenshot 5 — Goods Receipt

**File:** `05_MIGO_goods_receipt.png`  
**T-Code:** MIGO  
**When to take it:** After selecting "Goods Receipt" against "Purchase Order" and before/after posting

**What should be visible:**
- MIGO screen with transaction "Goods Receipt" and reference "Purchase Order"
- PO number entered: 4500001234
- Movement Type: 101
- Quantity received: 100 EA
- Storage location: SL01
- Posting date: 11.04.2026
- Material document number after posting (confirmation message)

---

### Screenshot 6 — Invoice Verification

**File:** `06_MIRO_invoice_verification.png`  
**T-Code:** MIRO  
**When to take it:** After entering invoice details and before/after posting

**What should be visible:**
- Transaction type: Invoice
- PO reference: 4500001234
- Invoice date and posting date
- Amount: ₹13,800
- The item list pulled from PO showing the GR quantity matched
- Green traffic light or "Balance = 0" indicator showing successful match
- Invoice document number after posting

**Tip:** The balance showing "0.00" is the most important part of this screenshot — it confirms the 3-way match worked.

---

### Screenshot 7 — Automatic Payment Run

**File:** `07_F110_payment_run.png`  
**T-Code:** F110  
**When to take it:** After the payment run is executed

**What should be visible:**
- Payment run parameters (date, company code, vendor)
- Payment run log showing invoices selected for payment
- Payment document number generated
- Amount paid: ₹13,800
- Vendor: ChipWorld India

**Tip:** The "Payment run completed" message and the payment log summary are the key things to capture.

---

### Screenshot 8 — Document Flow

**File:** `08_document_flow.png`  
**T-Code:** Access from within any document (Environment > Document Flow)  
**When to take it:** From the PO screen after all steps are completed

**What should be visible:**
- The complete document chain:
  - Purchase Requisition
  - Purchase Order
  - Goods Receipt / Material Document
  - Invoice Document
  - Payment Document
- All documents showing status "Completed" or "Cleared"

**Tip:** This is the most important screenshot of the whole project — it shows the full P2P cycle in one view. Make sure the screen is fully expanded so all document numbers are readable.

---

## Quick Reference Table

| # | T-Code | File Name | Key Item to Show |
|---|---|---|---|
| 1 | ME51N | `01_ME51N_PR_creation.png` | PR number + confirmation |
| 2 | ME41 | `02_ME41_RFQ_creation.png` | RFQ with vendor list |
| 3 | ME49 | `03_ME49_vendor_comparison.png` | Price comparison table |
| 4 | ME21N | `04_ME21N_PO_creation.png` | PO with price and vendor |
| 5 | MIGO | `05_MIGO_goods_receipt.png` | GR with movement type 101 |
| 6 | MIRO | `06_MIRO_invoice_verification.png` | Balance = 0 (3-way match) |
| 7 | F110 | `07_F110_payment_run.png` | Payment posted + cleared |
| 8 | Any | `08_document_flow.png` | Full document chain |

---

## General Tips

- Always take a screenshot immediately after saving — SAP shows a confirmation message at the bottom of the screen with the document number
- Use Windows Snipping Tool or Press `Alt + Print Screen` to capture the active SAP window only
- If running SAP in a virtual machine, use the VM's screenshot tool
- Crop out your personal login username from screenshots before publishing to GitHub

---

*Author: Ayush Pradhan | Roll No: 23053271 | KIIT University*
