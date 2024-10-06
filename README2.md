# Moglix Experience

**Worked on 5 projects [EOC (Excel on Cloud)](#eoc-excel-on-cloud), [DIGIMRO](#DIGIMRO), [Credlix (Nuphi and Exim)](#credlix-nuphi-and-exim), and [MaaS](#MaaS).**

# EOC (Excel on Cloud)

Work done on EOC (Excel on Cloud) is described below with JIRA ID.

Please feel free to ask for any doubts or clarification regarding specific tasks or descriptions.

## Task 1: (EOC-2802) Pick Supplier Credit Term from Exception List in RFQ & CPO Item Sheet

**Current Behavior:** When a supplier is mapped in the RFQ or CPO Item Sheet, the supplier credit term is fetched via API from SC.

**Going Forward:** SCM will maintain a separate exception list for supplier ID-plant ID combinations. When a supplier ID is selected on EOC, the system will check the exception list for a credit term and pre-fill it in EOC; otherwise, the default supplier credit term will be used.

**Impact:** Automates credit term selection, improving accuracy and reducing manual input in the RFQ and CPO process.

## Task 2: (EOC-2837) Introduce Defaulter Supplier Tagging in EOC

The task is to implement defaulter supplier tagging in the EOC UI and Excel downloads across the RFQ sheet, CPO item sheet, CM approval screen (web and responsive), and CM approval mailer. When a supplier name or ID is entered in the UI, a suggestion dropdown will appear with defaulter suppliers marked with red tagging and an info icon. On hovering over the icon, metrics such as Net Outstanding Debit Balance, Returns by Value %, and GSTR Default Invoices will be displayed. The defaulter tagging will be persistent until the RFQ reaches the "PO won" stage, after which all details will turn grey. Download sheets will include columns indicating whether the supplier is a defaulter, along with the defaulter metrics.

**Impact:** Enhances visibility of defaulter suppliers, improving decision-making during RFQ and CPO processes and ensuring accurate historical tracking in approval flows.

## Task 3: (EOC-2839) ARC Changes from Ruchi & Sandeep

- Introduce a new weekly report for SP > ARC Price:
    - Subject: 10 POs punched at SP > ARC Price, ARC price in system to be updated?
    - Mail Body: Inform users that CPOs have been received at a higher price than ARC price and request checking the details for possible updates. Attach the report.
    - Receivers: City Heads and KAMs
    - Frequency: Weekly on Wednesday.
- Modify weekly mailers by removing City Heads from the subject line and adding sourcing POC email along with customer POC (KAM).
- For internal weekly mailers, combine SP > ARC Price and SP < ARC Price line items. Modify the subject line to: [Alert] 61 POs breached ARC Price, price difference worth INR 10,000.

**Impact:** Improves ARC data accuracy, enhances visibility through reports and filters, and automates communication of price discrepancies, improving operational efficiency and decision-making.



# DIGIMRO
# Credlix (Nuphi and Exim)
# MaaS