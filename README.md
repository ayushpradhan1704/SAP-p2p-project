# 🛒 SAP Procure-to-Pay (P2P) — Full Purchasing Cycle

> A SAP MM capstone project demonstrating the complete end-to-end Procure-to-Pay process using SAP ERP.

---

## 👤 Author Details

| Field | Details |
|---|---|
| **Name** | Ayush Pradhan |
| **Roll Number** | 23053271 |
| **Programme** | B.Tech |
| **Specialization** | Computer Science and Engineering (CSE) |
| **Course** | SAP Data Analytics Engineering |
| **University** | Kalinga Institute of Industrial Technology (KIIT) |

---

## 📌 Introduction

The Procure-to-Pay (P2P) process is one of the most fundamental business workflows in any organization. It covers everything from identifying a need for goods or services to making the final payment to the vendor. This project demonstrates the complete P2P cycle using SAP Materials Management (MM) and Financial Accounting (FI) modules within an SAP ERP environment.

The project uses a fictional company called **TechNova Industries Pvt. Ltd.** — a mid-sized electronics manufacturing firm — as the business context throughout all documentation and demonstrations.

---

## 🧩 Business Problem

TechNova Industries was managing its procurement activities using spreadsheets and email approvals. This created several issues:

- No real-time visibility into purchase orders or delivery status
- Duplicate vendor payments due to manual invoice matching
- Delays in approvals because there was no structured workflow
- No centralized vendor database for comparison and selection

The goal of this project was to implement SAP MM's P2P cycle to eliminate these inefficiencies and bring full process automation and traceability.

---

## 🎯 Objectives

- Understand and configure the full P2P cycle in SAP MM
- Execute each transaction step using the correct T-Codes
- Demonstrate document flow from Purchase Requisition to Payment
- Show integration between SAP MM and SAP FI modules
- Document the entire process clearly for academic and practical reference

---

## 🔧 SAP Modules Used

| Module | Full Name | Role in P2P |
|---|---|---|
| **MM** | Materials Management | Handles purchasing, goods receipt, inventory |
| **FI** | Financial Accounting | Handles invoice verification and vendor payment |

---

## 🔄 End-to-End Workflow

```
[Business Need Identified]
         |
         v
 ┌───────────────────┐
 │  Purchase         │  T-Code: ME51N
 │  Requisition (PR) │  (Internal purchase request created)
 └────────┬──────────┘
          |
          v
 ┌───────────────────┐
 │  Request for      │  T-Code: ME41
 │  Quotation (RFQ)  │  (Sent to multiple vendors for quotes)
 └────────┬──────────┘
          |
          v
 ┌───────────────────┐
 │  Vendor           │  T-Code: ME49
 │  Comparison       │  (Quotes compared, best vendor selected)
 └────────┬──────────┘
          |
          v
 ┌───────────────────┐
 │  Purchase Order   │  T-Code: ME21N
 │  (PO)             │  (Formal order sent to selected vendor)
 └────────┬──────────┘
          |
          v
 ┌───────────────────┐
 │  Goods Receipt    │  T-Code: MIGO
 │  (GR)             │  (Physical goods received and confirmed)
 └────────┬──────────┘
          |
          v
 ┌───────────────────┐
 │  Invoice          │  T-Code: MIRO
 │  Verification     │  (Vendor invoice matched against PO & GR)
 └────────┬──────────┘
          |
          v
 ┌───────────────────┐
 │  Vendor Payment   │  T-Code: F110
 │  (Automatic)      │  (Payment made to vendor via F110 run)
 └───────────────────┘
```

---

## ✅ Features

- Complete 7-step P2P process demonstrated
- Real business scenario using TechNova Industries
- Document flow linkage across all SAP transactions
- Integration between MM and FI shown clearly
- Screenshot documentation for each key step
- Simple, academic-friendly language throughout

---

## 📋 Process Overview

| Step | Activity | T-Code | Module |
|---|---|---|---|
| 1 | Purchase Requisition | ME51N | MM |
| 2 | Request for Quotation | ME41 | MM |
| 3 | Vendor Comparison | ME49 | MM |
| 4 | Purchase Order | ME21N | MM |
| 5 | Goods Receipt | MIGO | MM |
| 6 | Invoice Verification | MIRO | FI/MM |
| 7 | Vendor Payment | F110 | FI |

---

## 🖼️ Screenshots

All screenshots are stored in the `/screenshots` folder as per the naming convention. The following are captured for each step:

| File Name | Description |
|---|---|
| `01_ME51N_PR_creation.png` | Purchase Requisition creation screen |
| `02_ME41_RFQ_creation.png` | RFQ creation with vendor details |
| `03_ME49_vendor_comparison.png` | Price comparison sheet across vendors |
| `04_ME21N_PO_creation.png` | Purchase Order with line items |
| `05_MIGO_goods_receipt.png` | Goods Receipt confirmation screen |
| `06_MIRO_invoice_verification.png` | Invoice posting with 3-way match |
| `07_F110_payment_run.png` | Automatic payment run output |
| `08_document_flow.png` | Full document flow chain in SAP |

---

## 📚 Learning Outcomes

After completing this project, I was able to:

- Understand how procurement flows through an ERP system end to end
- Execute SAP MM transactions with confidence
- Understand how SAP MM and SAP FI are integrated
- Identify how document flow works (PR → RFQ → PO → GR → Invoice → Payment)
- Appreciate the value of 3-way matching in preventing duplicate payments

---

## 🚀 Future Improvements

- Add **SAP SRM** (Supplier Relationship Management) for vendor portal integration
- Include **batch jobs** for automated goods receipt posting
- Explore **Fiori apps** for mobile-based approval workflows
- Add **reporting** using SAP Analytics Cloud or S/4HANA Embedded Analytics
- Implement **workflow approval** at the PR stage using SAP Business Workflow

---

## 📁 Project Structure

```
sap-p2p-project/
│── README.md                   ← You are here
│── docs/
│    ├── project_overview.md    ← Business context and scope
│    ├── p2p_process.md         ← Detailed step-by-step process guide
│── screenshots/                ← SAP transaction screenshots (see guide)
│── report/
│    ├── final_report.md        ← Full academic report (4–5 pages)
```

---

## 🏫 Disclaimer

This project is created for academic purposes as part of the SAP Data Analytics Engineering course at KIIT University. All company names and data used are fictional.

---

Screenshots are stored in the `/screenshots` folder as per the naming convention described in `screenshots/SCREENSHOT_GUIDE.md`.

---

*Made with ❤️ by Ayush Pradhan | KIIT University | 2025–26*

---

**Author:** Ayush Pradhan  
**Roll No:** 23053271  
**KIIT University**
