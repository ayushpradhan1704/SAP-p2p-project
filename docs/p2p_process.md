# SAP Procure-to-Pay (P2P) Process Guide

## Company: TechNova Industries Pvt. Ltd.

This document explains each step of the P2P process in detail — including the purpose, inputs, outputs, and a real-world example from TechNova Industries.

---

## Step 1: Purchase Requisition (PR)

**T-Code: ME51N**

### What is it?
A Purchase Requisition is an internal document raised by a department when they need to buy something. It is NOT sent to the vendor — it is just a formal request to the purchasing department saying "we need this item."

### Purpose
- Formally communicate a procurement need
- Get approval before spending money
- Provide details like quantity, required date, and material

### Input
- Material number or description
- Quantity required
- Required delivery date
- Plant and storage location
- Cost center (who is paying for it)

### Output
- PR document with a unique PR number (e.g., PR# 1000012345)
- This PR becomes the base for the RFQ and PO

### Real-World Example (TechNova)
The warehouse manager at TechNova notices that microcontroller chip inventory is running low. He raises a PR in SAP for **100 units of ATmega328P microcontroller chips** required by **15th April 2026**. The PR is routed to the Purchase Department for action.

### Key SAP Fields
| Field | Value (Example) |
|---|---|
| Material | CHIP-ATM-328P |
| Quantity | 100 EA |
| Required Date | 15.04.2026 |
| Plant | TN01 |
| Storage Location | SL01 |
| Account Assignment | Cost Center 1001 |

---

## Step 2: Request for Quotation (RFQ)

**T-Code: ME41**

### What is it?
An RFQ is a document sent to multiple vendors asking them to submit their price and delivery terms for the required material. It helps the company compare offers before committing to a purchase.

### Purpose
- Get competitive prices from multiple vendors
- Ensure fair procurement
- Collect delivery timeline and payment terms from vendors

### Input
- PR number (reference)
- List of vendors to contact
- Submission deadline for quotes

### Output
- RFQ documents sent to each vendor (e.g., RFQ# 6000001, 6000002, 6000003)
- Vendors respond with their prices

### Real-World Example (TechNova)
The purchasing team at TechNova creates RFQs and sends them to three approved vendors:
- **Vendor A: MicroElec Supplies** — Quote: ₹150/unit
- **Vendor B: ChipWorld India** — Quote: ₹138/unit
- **Vendor C: TechParts Hub** — Quote: ₹145/unit

### Key SAP Fields
| Field | Value (Example) |
|---|---|
| Quotation Deadline | 05.04.2026 |
| Vendor 1 | MicroElec Supplies (V1001) |
| Vendor 2 | ChipWorld India (V1002) |
| Vendor 3 | TechParts Hub (V1003) |
| Material | CHIP-ATM-328P |
| Quantity | 100 EA |

---

## Step 3: Vendor Comparison / Quotation Evaluation

**T-Code: ME49**

### What is it?
Once vendors respond to the RFQ, SAP helps the purchasing team compare all quotations side by side. The best vendor is selected based on price, delivery time, and quality rating.

### Purpose
- Compare prices from all vendors in one view
- Mark the most favorable quote
- Reject other vendors formally (optional)

### Input
- All RFQ responses entered into SAP
- Price per unit from each vendor
- Delivery lead times

### Output
- Price comparison report
- Selected vendor (best quote marked with a checkmark in SAP)
- Rejected vendors notified

### Real-World Example (TechNova)
Using ME49, the purchasing team runs the comparison report:

| Vendor | Unit Price | Total (100 units) | Delivery Days |
|---|---|---|---|
| MicroElec Supplies | ₹150 | ₹15,000 | 7 days |
| **ChipWorld India** | **₹138** | **₹13,800** | **5 days** |
| TechParts Hub | ₹145 | ₹14,500 | 6 days |

**ChipWorld India** is selected as the best vendor (lowest price + fastest delivery).

---

## Step 4: Purchase Order (PO)

**T-Code: ME21N**

### What is it?
A Purchase Order is a legally binding document sent to the selected vendor confirming the purchase. It contains quantity, price, delivery date, and payment terms.

### Purpose
- Formally commit to buying from the selected vendor
- Provide legal documentation of the purchase agreement
- Serve as the reference document for GR and Invoice

### Input
- Vendor selected from quotation comparison
- PR reference number
- Agreed price, quantity, and delivery date

### Output
- PO document with unique PO number (e.g., PO# 4500001234)
- PO sent to vendor (ChipWorld India)

### Real-World Example (TechNova)
TechNova raises PO# 4500001234 for:
- 100 units of ATmega328P microcontroller chips
- Unit Price: ₹138
- Total Value: ₹13,800
- Delivery by: 12.04.2026
- Payment Terms: Net 30 days

The PO is approved and sent to ChipWorld India electronically.

### Key SAP Fields
| Field | Value |
|---|---|
| PO Number | 4500001234 |
| Vendor | ChipWorld India (V1002) |
| Material | CHIP-ATM-328P |
| Quantity | 100 EA |
| Net Price | ₹138/unit |
| Delivery Date | 12.04.2026 |
| Payment Terms | NT30 (Net 30 days) |

---

## Step 5: Goods Receipt (GR)

**T-Code: MIGO**

### What is it?
When the goods physically arrive at the company's warehouse, the warehouse team records the receipt in SAP. This updates the inventory and confirms that the delivery has been made against the PO.

### Purpose
- Record actual receipt of goods into the system
- Update inventory levels in real time
- Create a GR document linked to the PO (used for 3-way matching later)

### Input
- PO number reference
- Quantity actually received
- Storage location where goods are placed

### Output
- Material Document (e.g., MD# 5000001234) — confirms stock increase
- Accounting Document — inventory value updated in FI
- GR/IR (Goods Receipt / Invoice Receipt) clearing entry created

### Real-World Example (TechNova)
On 11th April 2026, the delivery from ChipWorld India arrives. The warehouse team opens MIGO in SAP, enters PO# 4500001234, and confirms receipt of 100 units of the microcontroller chips. SAP automatically:
- Increases stock by 100 units in storage location SL01
- Posts an accounting entry: Dr. Inventory Account / Cr. GR/IR Account

### Key SAP Fields
| Field | Value |
|---|---|
| Movement Type | 101 (GR against PO) |
| PO Reference | 4500001234 |
| Quantity Received | 100 EA |
| Storage Location | SL01 |
| Posting Date | 11.04.2026 |

---

## Step 6: Invoice Verification

**T-Code: MIRO**

### What is it?
After goods are received, the vendor sends an invoice to TechNova's Finance team. The Finance team enters the invoice in SAP and the system performs a 3-way match:
- **PO** (what was ordered)
- **GR** (what was received)
- **Invoice** (what the vendor is billing)

If all three match within tolerance, the invoice is automatically cleared for payment.

### Purpose
- Verify vendor invoice accuracy
- Prevent overpayment or duplicate payments
- Post a liability entry in the FI module

### Input
- Vendor invoice document
- PO number reference
- GR document reference

### Output
- Invoice document in SAP (e.g., Invoice# 5105000123)
- Accounting entry: Dr. GR/IR Account / Cr. Vendor Account
- Invoice status: "Ready for Payment"

### Real-World Example (TechNova)
ChipWorld India sends an invoice for ₹13,800 (100 units × ₹138). The Finance team at TechNova opens MIRO, enters the vendor invoice number, references PO# 4500001234, and SAP automatically pulls the GR data. The 3-way match passes, and the invoice is posted successfully.

### Key SAP Fields
| Field | Value |
|---|---|
| Transaction | Invoice |
| PO Reference | 4500001234 |
| Vendor | ChipWorld India (V1002) |
| Invoice Date | 14.04.2026 |
| Invoice Amount | ₹13,800 |
| Tax Code | V0 (0% GST for demo) |

---

## Step 7: Vendor Payment

**T-Code: F110**

### What is it?
F110 is the Automatic Payment Program in SAP FI. It runs a payment batch based on due dates and payment terms. It identifies all open invoices due for payment and processes them automatically.

### Purpose
- Pay vendors on time as per agreed payment terms
- Avoid manual payment processing errors
- Automatically generate payment advices and bank transfer instructions

### Input
- Payment run date
- Company code
- Vendor account(s)
- Payment method (bank transfer, cheque, etc.)

### Output
- Payment document posted in SAP
- Bank file generated (sent to bank)
- Vendor account cleared (balance becomes zero)
- Payment advice note generated for vendor

### Real-World Example (TechNova)
On 11th May 2026 (30 days after invoice posting), the Finance manager at TechNova runs F110. SAP identifies the pending invoice of ₹13,800 for ChipWorld India, generates a bank transfer instruction, and posts the payment document. The vendor's open line item is cleared automatically.

### Key SAP Fields
| Field | Value |
|---|---|
| Payment Run Date | 11.05.2026 |
| Company Code | TN01 |
| Payment Method | T (Bank Transfer) |
| Vendor | ChipWorld India (V1002) |
| Invoice Amount Paid | ₹13,800 |

---

## Document Flow Summary

The complete document chain for this P2P cycle looks like this:

```
PR# 1000012345 (ME51N)
       ↓
RFQ# 6000001/2/3 (ME41)
       ↓
Vendor Comparison (ME49) → ChipWorld India selected
       ↓
PO# 4500001234 (ME21N)
       ↓
Material Doc# 5000001234 (MIGO)
       ↓
Invoice# 5105000123 (MIRO)
       ↓
Payment Doc# 1400000456 (F110)
```

This complete chain can be viewed inside SAP using the **Document Flow** feature (Environment > Document Flow from within any document screen).

---

**Author:** Ayush Pradhan  
**Roll No:** 23053271  
**KIIT University**
