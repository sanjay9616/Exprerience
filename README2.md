# Moglix Experience

**Worked on 5 projects MaaS, Credlix (Nuphi and Exim), EOC, and DIGIMRO.**

# 1. EOC (Excel on Cloud)

| S No. | TASK                                                                                     | JIRA ID                                                             |
| ----- | ---------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| 1     | [Adoption of Vendor Discovery at Line Item GA](#EOC-3753)                                | <a href="https://moglix.atlassian.net/browse/EOC-3753">EOC-3753</a> |
| 2     | [Add Brand Authorization Tagging to the Pending CPO CM* Approval Screen.](#EOC-3705)     | <a href="https://moglix.atlassian.net/browse/EOC-3705">EOC-3705</a> |
| 2     | [Enterprise Liquidation Process: Introduction of CPO Item Type 'Liquidation'](#EOC-3656) | <a href="https://moglix.atlassian.net/browse/EOC-3656">EOC-3656</a> |
| 2     | [Date Issue in EOC UI](#EOC-3720)                                                        | <a href="https://moglix.atlassian.net/browse/EOC-3720">EOC-3720</a> |

### <span id="EOC-3753"></span> Adoption of Vendor Discovery at Line Item GA

**Task:** Implement GA tracking for Search CTA on RFQ and CPO pages (user ID, date, click), GA for "Send for RFQ" CTA, and tag ERFQ data to indicate whether it was sent through item-level or bulk CTA.

**Impact:** Enhanced tracking and analytics for user interactions and ERFQ actions, improving data insights and decision-making.

### <span id="EOC-3705"></span> Add Brand Authorization Tagging to the Pending CPO CM* Approval Screen.

**Task:** Add Brand Authorization Tagging to the Pending CPO CM* Approval Screen and include it in email requests raised.

**Impact:** Ensures consistent tracking of brand authorizations and improves communication in approval processes.

### <span id="EOC-3656"></span> Enterprise Liquidation Process: Introduction of CPO Item Type 'Liquidation'

**As-Is Liquidation Process**

Region-wise liquidation teams (e.g., Team North Team 3) manage liquidation by creating scrap dealer/buyer plants with CLs and punching RFQs for scrap buyers and dummy suppliers. The original buy price (TP) and new selling price (SP) are defined, with RFQ approval from the City Head. Upon approval, a CPO is created as “RFQ” CPO-type, and inventory is auto-allocated, displayed as RFQ orders in PowerBI.

**Proposed Liquidation Process**

Region-wise liquidation teams create a new CPO type “Liquidation” for scrap buyers without a supplier. CPO approval is required from the City Head, with Jasmeet and Sandeep CC’d for values over Rs. 20,000. Inventory is auto-allocated post-approval, and PowerBI displays it as a liquidation order. Warehouse users can select “Liquidation” for closed, unreleased POs only, with additional fields like TP and delivery mode available during drafting. Users must input mandatory details before submitting for CM* approval based on the defined DOA criteria, with status visible on the listing page and CPO details sheet.

**Impact:** The proposed process improves efficiency and accuracy in liquidation management, reduces manual errors, and enhances tracking and reporting capabilities.

### <span id="EOC-3720"></span> Date Issue in EOC UI

Ensure the system date is correct when users update records; implement backend date sharing and validation for the "Need to Work" field, with timestamps displayed in the EOC UI for future reference.

**Impact:** Enhances data accuracy and prevents issues related to incorrect dates, improving user experience and system reliability.









**[⬆ Back to EOC (Excel on Cloud)](#1-eoc-excel-on-cloud)**


# 2. Credlix (Nuphi and Exim)
# 3. DIGIMRO
# 4. MaaS