# Final Project Report

---

# SAP Procure-to-Pay (P2P) — Full Purchasing Cycle

---

**Submitted by:** Ayush Pradhan  
**Roll Number:** 23053271  
**Programme:** B.Tech — Computer Science and Engineering (CSE)  
**Course:** SAP Data Analytics Engineering  
**University:** Kalinga Institute of Industrial Technology (KIIT), Bhubaneswar  
**Academic Year:** 2025–26  
**Submission Date:** April 2026  

---

## 1. Problem Statement

In many mid-sized manufacturing companies in India, procurement is still handled through a combination of spreadsheets, emails, and phone calls. While this may work at a small scale, it creates significant problems as the company grows:

- There is no single system of record for purchase requests
- Vendors are selected informally without documented comparison
- Goods received are tracked in paper registers that can be lost or misread
- Vendor invoices are matched manually against POs, which is slow and error-prone
- Payments are often delayed or made in error (duplicates are common)

**TechNova Industries Pvt. Ltd.**, a fictional electronics manufacturer based in Bhubaneswar, faced all of these challenges. The company needed a structured, automated procurement system to control costs, ensure vendor accountability, and maintain accurate financial records.

This project addresses these problems by implementing the full SAP Procure-to-Pay (P2P) cycle using SAP MM and SAP FI modules.

---

## 2. Objectives

The objectives of this project are:

1. To understand the complete Procure-to-Pay business process from a practical perspective
2. To learn and execute each SAP transaction related to the P2P cycle
3. To demonstrate how SAP MM and SAP FI modules work together in procurement
4. To show how the 3-way match (PO + GR + Invoice) prevents financial errors
5. To document the entire process clearly with transaction codes, data, and screenshots
6. To present the process using a consistent real-world company scenario

---

## 3. Solution Description

The solution implemented in this project is the standard SAP P2P process using the following SAP components:

- **SAP MM (Materials Management):** Handles the entire procurement lifecycle from PR to GR
- **SAP FI (Financial Accounting):** Handles invoice posting and payment processing

The process was configured and executed in a SAP training environment (SAP ECC 6.0 sandbox). A fictional company, TechNova Industries (Company Code: TN01), was used throughout to simulate a realistic procurement scenario.

The project scenario involves TechNova purchasing **100 units of ATmega328P microcontroller chips** from an approved vendor. This single scenario is used to walk through all 7 steps of the P2P cycle from Purchase Requisition to Vendor Payment.

---

## 4. SAP P2P Process Explanation with T-Codes

### Step 1 — Purchase Requisition | T-Code: ME51N

The warehouse department raises a PR for 100 units of microcontroller chips. This document is internal — it goes to the Purchasing team for review, not to any vendor.

Key data entered: material code, quantity (100 EA), required date (15.04.2026), plant (TN01), storage location (SL01), and cost center.

**Output:** PR document number generated (e.g., 1000012345)

---

### Step 2 — Request for Quotation | T-Code: ME41

The Purchasing team creates RFQ documents and sends them to three approved vendors. Each vendor is asked to provide their unit price, delivery lead time, and payment terms.

Vendors contacted:
- MicroElec Supplies (V1001) — quoted ₹150/unit
- ChipWorld India (V1002) — quoted ₹138/unit
- TechParts Hub (V1003) — quoted ₹145/unit

**Output:** Three RFQ numbers generated (6000001, 6000002, 6000003)

---

### Step 3 — Vendor Comparison | T-Code: ME49

SAP displays all vendor quotes in a comparison screen. The purchasing team evaluates the prices and delivery terms. ChipWorld India offers the lowest price (₹138/unit) and fastest delivery (5 days), making them the preferred vendor.

**Output:** Best vendor selected and marked in SAP; rejection letters optionally sent to others

---

### Step 4 — Purchase Order | T-Code: ME21N

A formal PO is created referencing the PR and the accepted RFQ from ChipWorld India. The PO specifies 100 units at ₹138/unit = ₹13,800 total. Payment terms are Net 30 days.

**Output:** PO number 4500001234 generated and sent to vendor

---

### Step 5 — Goods Receipt | T-Code: MIGO

On 11.04.2026, the chips arrive at TechNova's warehouse. The warehouse staff opens MIGO, references PO# 4500001234, and confirms the receipt of 100 units. SAP updates the stock immediately.

**Output:** Material Document 5000001234 posted; inventory updated; GR/IR clearing entry created in FI

---

### Step 6 — Invoice Verification | T-Code: MIRO

ChipWorld India sends an invoice for ₹13,800. The Finance team enters it in MIRO, referencing the PO number. SAP performs the 3-way match automatically:

- **PO says:** 100 units at ₹138 = ₹13,800 ✅
- **GR says:** 100 units received ✅
- **Invoice says:** ₹13,800 ✅

The match is successful, and the invoice is approved for payment.

**Output:** Invoice document 5105000123 posted; vendor account credited with ₹13,800

---

### Step 7 — Vendor Payment | T-Code: F110

On 11.05.2026 (30 days after invoice posting), the Finance manager runs F110. SAP identifies the ₹13,800 payable to ChipWorld India and processes the payment via bank transfer.

**Output:** Payment document 1400000456 posted; vendor account cleared; bank file generated

---

## 5. Screenshots Description

The following screenshots were captured during the project and are stored in the `/screenshots` folder as per the naming convention:

| Screenshot | File Name | What It Shows |
|---|---|---|
| 1 | `01_ME51N_PR_creation.png` | The ME51N screen with PR filled for 100 units of chips |
| 2 | `02_ME41_RFQ_creation.png` | RFQ creation screen showing vendor list and material details |
| 3 | `03_ME49_vendor_comparison.png` | Comparison table with all three vendor quotes |
| 4 | `04_ME21N_PO_creation.png` | PO screen with ChipWorld India, quantity, price, and delivery date |
| 5 | `05_MIGO_goods_receipt.png` | MIGO screen showing GR against PO with movement type 101 |
| 6 | `06_MIRO_invoice_verification.png` | MIRO screen with 3-way match success indication |
| 7 | `07_F110_payment_run.png` | F110 payment run summary showing cleared vendor invoice |
| 8 | `08_document_flow.png` | Complete document chain from PR to Payment in SAP |

---

## 6. Technology Stack

| Component | Details |
|---|---|
| ERP System | SAP ECC 6.0 (training sandbox) |
| Primary Module | SAP MM (Materials Management) |
| Secondary Module | SAP FI (Financial Accounting) |
| Interface | SAP GUI 7.60 |
| Operating System | Windows 10 (client machine) |
| Documentation | Markdown, GitHub-style project structure |
| Report Format | PDF / Markdown |

---

## 7. Unique Points of This Project

- A single consistent company scenario (TechNova Industries) is used across all steps to make the process feel connected and realistic
- The project covers both procurement (MM) and accounting (FI) to show true end-to-end flow
- The 3-way matching concept is explained clearly with matching data values across PO, GR, and Invoice
- All SAP fields and values used are documented so the process can be reproduced easily
- The document flow is shown as a complete chain, not just individual transactions

---

## 8. Future Improvements

If this project were to be extended further, the following enhancements would be valuable:

1. **Approval Workflow:** Adding PR and PO approval routing using SAP Business Workflow
2. **Vendor Portal Integration:** Using SAP SRM to allow vendors to submit quotes online
3. **Reporting and Analytics:** Creating SAP Analytics Cloud dashboards to monitor procurement KPIs (e.g., PO cycle time, invoice error rate, on-time delivery %)
4. **Partial Goods Receipt:** Demonstrating scenarios where only partial delivery is received
5. **Credit Memo Process:** Showing how to handle returns and vendor credit notes
6. **Integration with SAP S/4HANA:** Migrating the same process to S/4HANA and comparing the Fiori-based experience

---

## 9. Conclusion

This project successfully demonstrates the complete Procure-to-Pay (P2P) cycle in SAP, covering all seven major steps from Purchase Requisition to Vendor Payment. Using the business scenario of TechNova Industries purchasing microcontroller chips, the project shows how SAP MM and SAP FI work together to create a seamless, error-resistant procurement workflow.

The most important learning from this project is how the 3-way match in MIRO prevents financial errors by ensuring that the company only pays for what it ordered (PO) and what it actually received (GR). This single feature alone eliminates a large number of payment disputes and duplicate payments that are common in manual procurement systems.

SAP's P2P process brings transparency, auditability, and efficiency to procurement — making it one of the most critical business processes for any organization using an ERP system.

---

*End of Report*

---

**Author:** Ayush Pradhan  
**Roll No:** 23053271  
**KIIT University**
