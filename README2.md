# Moglix Experience

Throughout these projects, I utilized a broad range of technologies, including Angular, Angular Material, RxJS, NgRx, ReactJS, NextJS, Material-UI, and Tailwind CSS for web development. Additionally, I worked with JavaScript, TypeScript, Python, HTML, CSS, MySQL, and DBMS for languages and databases. My expertise extends to data structures and algorithms, with familiarity in ExpressJS and MongoDB, while effectively maintaining version control with Git. I contributed to multiple high-impact projects, showcasing my proficiency in Angular, RxJS, and TypeScript.

- [EOC (Excel on Cloud)](#eoc-excel-on-cloud): is an internal application developed at Moglix to streamline the management of Purchase and Sale orders. The application features a custom Excel-like interface that allows users to efficiently track items throughout the entire lifecycle of orders and products. Specifically designed for the internal buyer team, EOC simplifies the creation of Purchase Orders, enhancing the overall efficiency of the purchasing process.
- [DIGIMRO](#DIGIMRO): DigiMRO is India's leading distributor of multi-category and multi-brand low-voltage electronic security products, offering a vast range of global brands and unparalleled industry expertise in B2B distribution of CCTV, access control, fire, power, audio/video, and network systems, while serving as an indispensable partner for suppliers and customers through its extensive reach, expertise, and logistics capabilities that enhance competitiveness and maintain critical supply chains.
- [Credlix (Nuphi and Exim)](#credlix-nuphi-and-exim): Credlix, a digital supply chain finance platform from Moglix, provides quick, collateral-free working capital solutions for enterprises, suppliers, and exporters in India and Southeast Asia, leveraging Moglix's expertise in end-to-end supply chain transformation for over 700 enterprises and 16,000 SMEs exporting to 53 countries, and offers services such as early payment, vendor finance, channel finance, invoice discounting, and purchase order finance to ensure continuous movement in domestic supply chains and export financing.
- [MaaS](#MaaS): The project streamlines the management of bulk orders, facilitating seamless tracking and updating of financial transactions and customer interactions throughout the order lifecycle.

# EOC (Excel on Cloud)

Work done on EOC (Excel on Cloud) is described below with JIRA ID.

Please feel free to ask for any doubts or clarification regarding specific tasks or descriptions.

## Task 1: (EOC-2802) Pick Supplier Credit Term from Exception List in RFQ & CPO Item Sheet

**Current Behavior:**

When a supplier is mapped in the RFQ or CPO Item Sheet, the supplier credit term is fetched via API from SC.

**Going Forward:**

SCM will maintain an exception list for supplier ID-plant ID combinations. Upon selecting a supplier ID in EOC, the system will check this exception list for a pre-defined credit term and automatically populate it. If no exception is found, the default supplier credit term will be used.

**Impact:**

Automates the credit term selection process, improving accuracy and reducing manual data entry during the RFQ and CPO processes, leading to time savings and fewer errors.

## Task 2: (EOC-2837) Introduce Defaulter Supplier Tagging in EOC

**Task:**

Implement defaulter supplier tagging across the EOC UI and Excel downloads for the RFQ sheet, CPO item sheet, CM approval screens (web and responsive), and CM approval mailer. When a supplier name or ID is entered, a dropdown will display defaulter suppliers marked in red, along with an info icon. Hovering over the icon will reveal metrics such as Net Outstanding Debit Balance, Returns by Value %, and GSTR Default Invoices. The defaulter tagging will remain visible until the RFQ reaches the "PO won" stage, after which the details will turn grey. Download sheets will include columns indicating defaulter status and associated metrics.

**Impact:**

Increases visibility of defaulter suppliers, improving decision-making in RFQ and CPO processes and ensuring proper historical tracking in approval workflows, reducing financial risks.

## Task 3: (EOC-2839) Weekly Report & Mailer Enhancements for SP > ARC Price

- New Weekly Report for SP > ARC Price:
    - Subject: 10 POs punched at SP > ARC Price, ARC price in system to be updated?
    - Mail Body: Notify users that POs have been received at a higher price than the ARC price, requesting them to review and update ARC prices if necessary Attach the relevant report.
    - Receivers: City Heads and KAMs.
    - Frequency: Weekly every Wednesday.
- Weekly Mailer Modifications:
    - Remove City Heads from the subject line.
    - Add sourcing POC email alongside the customer POC (KAM) in the email.
- Internal Mailers:
    - Combine SP > ARC Price and SP < ARC Price line items in internal mailers.
    - Modify subject line to: "[Alert] 61 POs breached ARC Price, price difference worth INR 10,000."

**Impact:**

Enhances accuracy and visibility of ARC data, streamlines price discrepancy reporting, and automates communication, improving operational efficiency and decision-making.

## Task 4: (EOC-2780) ARC Phase 3 in EOC

In ARC Phase 3, the following scope of work is outlined:

- CPN-MSN Mapping & List Price: Map MSN and its description to CPN based on past transaction history of CPO & SPO or from the catalog portal. Pre-fill List Price from the catalog once MSN is mapped and display it on the ARC listing screen and in downloads.
- Override List Price: For ARC Type LP-Discount, if a List Price is already filled, override it with the latest value from the catalog and maintain an audit trail of the changes with dates.
- Data Syncing: Ensure continuous syncing between the catalog and EOC for updated List Price data.
- Backfill UOM: Complete missing UOM for active ARC items.
- Buyers Portal Support: Add fields for HSN, GST, and Image URL in the EOC and include them in bulk downloads but not in the listing UI.
- Design Changes: Allow bulk uploads of ARC data, add a new column for "Product Type" (Domestic/Import) for LP-Discount ARC Types, and ensure ARC discounts vary by product type.
- Audit Data: Capture audit logs for changes in Net Price, List Price, Discount, ARC Validity, MSN, L1 & L2 categories, and ARC Type, with a design to show visibility of these audit changes.

**Impact:** Improves ARC management through enhanced data accuracy, automated List Price syncing, and expanded audit capabilities, while supporting new features in the Buyers Portal.

## Task 5: (EOC-2907) Remove Plant ID Configuration from ARC for Soft Alerts & Weekly Mailers

In ARC Phase 2, soft alerts were shown to selective customers where ARC data cleaning was completed. Now that PAN India data is available and uploaded, the plant ID check needs to be removed. Soft alerts for SP < ARC Price and SP > ARC Price, as well as weekly mailers to KAMs, sourcers, and city heads, should be sent to all customers.

**Impact:** Expands visibility by ensuring soft alerts and weekly mailers reach all customers, improving communication and awareness across the board.

## Task 6: (EOC-2902) Minor Enhancements in Catalog Sheet

Enhance the Catalog Sheet by implementing the following improvements for better efficiency and usage:

- Add filters for Region in the TOP view.
- Add columns for Region, Team Name, CPO Item Type, and Customer POC.
- Remove columns for MSN Type, PO Approval, and Committed Supplier.
- Rearrange and freeze columns as per the attached sheet, and remove columns marked in red.

**Impact:** Streamlines the Catalog Sheet, making it more user-friendly and efficient for the catalog team by improving data visibility and eliminating unnecessary fields.

## Task 7: (EOC-2965) Show Summary of ARC Accounts in ARC Summary Screen

Display a summary count of the following metrics next to the "Total Results" widget on the ARC Summary screen:

- Active Customers: <>
- Active Plant IDs: <>
- Active Brands: <>
- Active CPNs: <>
- Position:
- Place the metrics next to the Total Results widget in the ARC Summary Screen.

**Design:** Refer to the MAAS screenshot for design reference.

**Impact:** Enhances the ARC Summary screen by providing a quick overview of key metrics, improving data accessibility and decision-making.

## Task 8: (EOC-2780) ARC Phase 3 in EOC

In ARC Phase 3, the following tasks are included:

- `CPN-MSN Mapping & List Price`: Map MSN and its description to CPN based on past transaction history (CPO & SPO) or catalog portal. Pre-fill the List Price from the catalog and display it on the ARC listing screen and in downloads.
- `List Price Override`: If a List Price is already filled for LP-Discount ARC Type, override it with the latest value from the catalog, maintaining an audit trail of the changes with date records.
- `Data Syncing`: Ensure continuous syncing between Catalog and EOC for updated List Price data.
- `Backfill UOM`: Complete missing UOM data for active ARC items.
- `Buyers Portal Support`: Capture HSN, GST, and Image URL for ARC catalog listing and purchase in the Buyers Portal. These fields will appear in bulk downloads but not in the UI listing.
- `Bulk Upload Support`: Implement the ability to bulk upload ARC data and add a column for Product Type (Domestic/Import) for LP-Discount ARC Types, varying ARC discounts based on product type.
- `Audit Data Capture`: Track changes in Net Price, List Price, Discount, ARC Validity, MSN, L1 & L2 categories, and ARC Type, with visibility of audit changes.

**Impact:** Improves data accuracy, enhances ARC management by automating price and UOM syncing, supports buyers with additional fields, and enables detailed audit tracking, resulting in better control and efficiency in ARC operations.

## Task 9: (EOC-2915) Revamp RFQ & CPO Item Sheet

The task involves revamping the RFQ and CPO Item Sheets with the following scope of work:

- Header Redesign: Change EOC headers from vertical to horizontal with a floating search bar.
- RFQ Item Sheet Revamp: Introduce quick filters and tab view based on user persona.
- CPO Item Sheet Revamp: Add a top bar for search, quick filters, and tab view based on user persona.
- Portal Redirection: Enable redirection to other portals from EOC.
- Productivity Dashboard: Implement a dashboard for individual users and managers.
- Manager’s View: Add resource-level views for managers in the RFQ and CPO Item Sheets.

**User Workflow:** Separate stories for each of the 7 workflows are created and linked to the Epic for detailed reference.

**Impact:** Enhances user experience, improves navigation, and boosts productivity by adding personalized views and filters, leading to better resource management and efficiency in the RFQ and CPO processes.

## Task 10: (EOC-2923) Introduce Productivity Dashboard in Global Header in EOC

The task is to introduce a Productivity Dashboard in the global header of EOC, with two views: Executive and Manager.

**Workflow:**

    - Executive View:
        - A blue productivity widget will appear in the header, showing the current day's productivity count, increasing as tasks are completed.
        - Displays Your Productivity Count / Avg Productivity Count based on benchmarks.
        - Clicking the widget opens a right-side popup where users can select filters (Today, Yesterday, WTD, MTD).
        - Data points are personalized based on the user's role (CS, Sourcer, KAM). Refer to the provided sheet for specific data points.
    - Manager View:
        - Default text: "Your Team’s Productivity" with the ability to open a popup showing team performance (Today, Yesterday, WTD, MTD).
        - By default, the lowest-performing employee is selected, and managers can select other employees from a dropdown.

**Impact:** Improves productivity tracking and provides real-time insights for both individual users and managers, leading to enhanced performance monitoring and team management.

## Task 11: (EOC-2960) Pre-fill MSN Related Details in RFQ & CPO Sheet

The task involves enhancements to the RFQ Item Sheet and CPO Item Sheet (Item View) as follows:

- Introduce the MSN UOM next to the Suggested MSN from Catalog column.
- Pre-fill MSN UOM and List Price from the catalog portal based on the MSN filled in the MSN Assign column.
- Rename the UOM column to Customer UOM in both Front End (FE) and Back End (BE) of EOC.
- Maintain an audit log for changes made in the above columns.
- The MSN UOM field will not be editable.
- Information will be fetched from the Kafka topic shared by the catalog team.

**Impact:** Enhances data accuracy in the RFQ and CPO sheets by ensuring timely and correct pre-filling of MSN-related details, improving usability and reducing manual errors.

## Task 12: (EOC-2987) Add Most Recent 10 Updates in ARC Listing > Log

The task is to implement a feature that displays the most recent 10 updates in the ARC Listing log, regardless of parameters such as price, discount, brand, or category.

- In ARC Listing > View Log > Audit Fields, introduce a dropdown value: Most Recent.
- Set Most Recent as the default value in the dropdown.
- Always display 10 results for the Most Recent option.
- Show results in descending order based on dates.
- For other audit fields, display audit history for the last 3 months only in the UI.
- Store audit logs for data older than 3 months, enabling sharing of this data in CSV format when required.

**Impact:** Improves accessibility to recent updates in the ARC Listing, enhancing user experience and facilitating better tracking of changes over time.

## Task 13: (EOC-3010) Enhancement in Defaulter Supplier Tagging Task

Currently, defaulter suppliers and their three metrics are displayed in the RFQ Sheet, CPO Item Sheet, CM approval mail, and CM approval screens (web and mobile).

- Net Debit Outstanding Balance:
    - Currently shows both positive and negative values.
    - Update to display negative values only if `net_balance_default_flag`=1 in the `analytics_reporting_default_supplier` table.
    - For `net_balance_default_flag`=0, show "Net Debit Outstanding Balance: -" at all five locations.

**Impact:** Improves the accuracy of defaulter supplier metrics, ensuring clarity in outstanding balances and reducing potential confusion for users.

## Task 14: (EOC-2923) Introduce Productivity Dashboard in Global Header in EOC

The task involves introducing a Productivity Dashboard in the global header of EOC, featuring two views: Executive and Manager.

- Executive View:
    - A blue productivity widget will appear in the header, displaying the current day’s productivity count, which will increase based on completed tasks.
    - Show Your Productivity Count / Avg Productivity Count based on benchmarks of total actions.
    - Clicking the widget opens a popup from the right, defaulting to Today, with options to select Yesterday, WTD, or MTD.
    - The executive view is personalized based on user persona (CS, Sourcer, KAM) to display different productivity data points. Refer to the provided sheet for specific user persona data points.

- Manager View:
    - Displays "Your Team’s Productivity" as the default text.
    - Clicking the widget opens a right-side popup, with Today selected by default, allowing the selection of Yesterday, WTD, or MTD.
    - The email ID of the lowest-performing employee will be pre-selected, with the ability to select another team member from a dropdown.

**Impact:** Enhances productivity tracking and reporting capabilities, providing real-time insights for executives and managers to drive performance improvements and optimize resource management.

## Task 15: (EOC-3052) Credit Term ID to be Sent to SCM

The task aims to resolve the issue of the Credit Term ID not being sent to SCM when users update the Credit Term on the EOC UI.

**Current Issue:** Users currently update the Credit Term in the EOC UI, but the Credit Term ID is not sent to SCM.

**Proposed Solution:**

-Remove the hardcoded supplier credit term list from the EOC and instead sync supplier credit terms centrally as key-value pairs (e.g., "Credit 30 days" - "30").
- When a user selects a supplier name and ID in the RFQ sheet, the corresponding credit term should auto-fill, and users should not be allowed to change it from the UI.
- If the supplier is unregistered, only the supplier name should appear without an ID, allowing the user to select the credit term from a dropdown.
- Ensure the correct Credit Term ID, mapped with the supplier credit term, is passed to SalesOps.

**Impact:** Improves data accuracy by ensuring the correct Credit Term ID is sent to SCM, streamlining the supplier credit term process and enhancing user experience.

## Task 16: (EOC-3022) Enhance Existing Quotation Format to Include More Data Points

The task involves enhancing the existing quotation format to incorporate additional data points as outlined below.

**Scope of Work:**

- QTS Flow Enhancements (RFQ Sheet Changes):
    - Introduce a Search By Quotation Number option, positioned as the last item in the dropdown.
    - Add a Line Number column in the Item Details section, placed next to the Quantity column in both the UI and download formats.
    - Ensure the Line Number appears in the Punch RFQ screen as an optional field.

- QTS Template Changes:
    - Display Customer Credit Days prominently at the top in bold text (e.g., "30 Days from Invoice Submission").
    - Add two columns next to GST% for Total Value (excluding GST%) and Total Value (including GST%) at the item level.
    - Include a Sub Total section: {value without Tax}, Tax: {value} (tax percentage), Total Value: {value including tax}.
    - Add Delivery Terms below the Quotation Date.
    - Introduce a Serial Number column as the first column before Item Description (numbered 1, 2, 3, etc.).

**Impact:** Enhances the quotation format by providing comprehensive data points, improving clarity, and facilitating better decision-making for users.

## Task 17: (EOC-3089) Implement Manager's View at Resource Level for Enquiry Pendency

The task is to introduce a Manager’s View at the resource level for the Enquiry Pendency Dashboard.

**Scope of Work:**

- New Screen:
    - Create a new screen in the Dashboard > Enquiry Pendency Dashboard, positioned first. This dashboard will be accessible only to managers (VP Supply, MD, Regional Head, CS Head, CSL, RSL, Admin Tech/Product) as per business designations in account service.

- Global Filters:
    - Region
    - Team Name
    - Group
    - Plant
    - Customer POC
    - Sourcing POC

- Download Report:
    - Enable downloading reports based on the selected date range.

- Listing Changes:
  - The listing will be at the email ID level, with the sequence of columns changing based on business designation (KAM, Category Buyer, Enterprise Sourcer).
    - RFQ Status: Individual columns for each RFQ status.
    - Business Designation: Displayed as the second column.
    - Grand Total: Sum of all values in all columns (Created, Working, etc.).
    - Aging Days: Average days of items where the status has not changed.
    - Total Pendency: Count of items that have not moved to QTS within 48 hours of creation (excluding Sundays and non-working hours; working hours are 10 AM to - 7 PM, Monday to Saturday).
    - % Pendency: Calculated as Total Pendency / Grand Total.

- Dynamic Updates:
    - The displayed numbers will reflect the current data and update when the user clicks the refresh icon in the window.

- Default Data:
    - The download sheet should work based on selected filters and dates, with the default view showing data for the last 7 days, excluding Sundays.

**Impact:** This enhancement provides managers with a comprehensive view of enquiry pendency, improving oversight and decision-making, while ensuring timely responses to enquiries.

## Task 18: (EOC-3105) HZL Related Requirements

The task aims to automate several processes for HZL orders, particularly those for Team Kohinoor, to improve efficiency and reduce manual work.

- Automate Delivery and Pricing:
    - Set DP-Shipped by Supplier as the default value for delivery type.
    - Automatically set Final TP/Unit as 1.2 * Effective SP.
    - Set Pickup Warehouse as Udaipur when the plant name is Hindustan Zinc Limited-(TVSSCS) Udaipur.

- Bulk Upload Feature:
    - Enable a bulk upload feature with download and upload template functionality for all CPOs from all sources, including HZL.

- Download Template Columns:
    - Supplier ID
    - Final TP per Unit
    - Lead Time
    - Plant ID
    - CPO No.
    - Item ID (mandatory for non-HZL)
    - Line No. (mandatory for HZL; Item ID optional for HZL)
    - CPN
    - Pickup Warehouse
    - Delivery Type

- Upload Validation & Rules:
    - For Team Kohinoor, if Item ID is not available, match based on CPO No. + Plant ID + Line Number and update line items in the CPO details.
    - For other customers, match based on Item ID to update details in the CPO details sheet.
    - Validate that the Supplier ID is active.
    - If any data is blank in the upload template, do not override existing values.

- Handling Data Overrides:
    - If new data is uploaded for an existing line number, the data should override previous entries.
    - Ignore blank fields during overrides to avoid data loss.

- Attached File:
    - The HZL CS executive will fill the data in the attached template provided by the customer. The template includes CPO details like supplier assignments and other fields.

**Impact:**

- Saves 20 manhours per month by automating the filling of fields and validating information.
- Reduces the risk of wrong supplier assignment and saves an additional 45 manhours monthly, with a total time-saving of approximately 65 manhours per month.

## Task 19: (EOC-3146) Add One More Metric in Productivity Dashboard

The task involves adding a new metric to the Productivity Dashboard and making some modifications to existing metrics.

- New Metric Addition:
    - Add a new metric, "MSN Mapped at Enquiry Stage," in the 2nd position on the Productivity Dashboard.
    - This metric will show the count of line items where RFQ is mapped in the MSN Assign column.
    - Set the average benchmark/day for this new metric at 25.

- Renaming and Modifications:
    - Rename the metric "RFQ" to "Enquiry" in the metrics table.
    - Comment out the RFQ Bot punching metric until Ops figures out its integration. This will be turned back on later.

- Logic for the New Metric:
    - Exclude Repeat RFQs from the productivity calculation for the MSN Mapped at Enquiry Stage metric, as they get auto-filled.
    - Productivity should only count when someone overrides the MSN in the column.

**Impact:** Improves productivity tracking by adding a new relevant metric, while renaming and temporarily pausing certain features to streamline operations.

## Task 20: (EOC-3080) CPO Item Sheet Revamp

The task involves revamping the CPO Item Sheet by introducing new global filters, tab structure, and adding/removing/rearranging columns based on the new design.

- Global Filters:
    - Introduce 8 global filters with multi-select checkboxes: Region, Team, Customer Group, Plant, Customer POC, Sourcing POC, Priority, Creation Date.
    - Apply CTA: Users need to click "Apply" after selecting values from the filters.
    - Reset CTA: Resets all selected global filters.

- Save CTA:
    - After updating data in the RFQ sheet, users can save changes by clicking the Save CTA.

- Action Dropdown:
    - All current RFQ actions (7 total) will appear in a dropdown.
    - Validation: If the selected action is not applicable to an RFQ item, a UI validation error will display: "The selected RFQ Item Id: <xx> is not eligible for <action name>!"

- Columns and Filters:
    - Column filters will now appear next to the column header, maintaining the current functionality.
    - Freezing of filters will continue as is.

- Tab Structure:
    - Each tab corresponds to the Broad Stage Status column values, with additional tabs for Cancelled, Cancel & Cloned, and Returned.
    - Default tab: New Order Created.
    - Show an unread count in red for any new inflow of items in a tab not reflected in the current view.

- Updates:
    - Add CPO Source as a global filter with a checkbox, and include this in the download sheet.
    - For Cancelled & Cloned items, introduce two new columns next to Item ID in both the UI and download sheet:
    - Cancelled Item ID
    - Is Cloned Item (Y/N)

**Impact:** Improves the user experience by providing an intuitive tab structure, global filters, and better action visibility, while enhancing data management and efficiency within the CPO Item Sheet.

## Task 21: (EOC-3154) Stop CPO Manual Punching for Net Price ARC Orders with Price Difference >10%

The task is to prevent the manual punching of ARC orders for Net Price CPNs/brands where the price difference between ARC price and SP is greater than 10% (for orders where SP is less than the ARC price). This restriction applies to all verticals, excluding UAE. Only applicable for PO source = EOC.

**Workflow:**

- At the CPO punching stage, when the effective SP is filled and meets the above condition, a UI validation error will display: "CPO punching is not allowed for ARC net price items as price difference (SP < ARC) > 10%".
- Refer to the provided sheet for exact calculations of the SP and ARC price difference.

**Impact:** Prevents punching of CPOs with significant price differences, ensuring accurate pricing for ARC items and reducing the risk of financial discrepancies.

## Task 22: (EOC-3145) Introduce New CPO Source & New CPO Item Type

The task involves adding new CPO item types and inventory options to the CPO details and punch screens, along with updates to the CPO listing screen.

- CPO Details Screen & Punch Screen:
    - New CPO Item Types:
        - Introduce Internal, Sample, and Stock Transfer Note (STN) as new values in the CPO Item Type dropdown.
        - Sample and Internal can be manually selected from the dropdown.
        - STN will be automatically set via API when WMS is the source of CPO creation.
    - Inventory Type in Header Tab:
        - Add an Inventory Type dropdown with two possible values: VMI and JIT.
        - If VMI is selected, further options for VMI Owner will appear, with possible values: Moglix, Supplier, Customer.
    - CPO Details:
        - Introduce a new Inventory Type column with values: VMI - Moglix, VMI - Supplier, VMI - Customer, or JIT.

- CPO Listing Screen:
    - Add a new value in the global filter source dropdown: WMS.
    - For CPOs where the item type is Stock Transfer Note (STN), set the source as WMS.
    - Ensure CPOs with source WMS are visible in the listing.

**Note:** The CPO line item dropdown should be updated wherever it appears, including punch, repeat, cancel, cancel and clone, and edit options.

**Impact:** Enhances flexibility and automation by introducing new CPO item types and inventory management options, streamlining processes for internal, sample, and stock transfer orders, and ensuring accurate categorization of CPO sources.

## Task 23: (EOC-3099) CRMM Automation Project Phase 1

**Description:**

The task is to automate the CRMM project with the following scope of work:

**Scope of Work:**

1. CPO Details Screen Validations:
    - CPO items with CPO Item Type = CRMM will only be allowed to be punched if the plant is in the approved list (within the expiry date).
    - A list of Core and Non-Core categories will be maintained by the catalog portal. RM+Pipes and packaging will be treated as Non-Core.
    - For Non-Core categories, allow CRMM CPO item IDs to be punched for approved plants with CM% approval at SalesOps during supplier assignment.
    - For Core categories, CRMM CPO item IDs can be punched with Mukund's approval until the plant's CRMM expiry date. This applies to the enterprise vertical only.

2. Approval Workflow:
    - On punching a CPO line item for the first time with CPO Item Type = CRMM and from a core category, approval will go to Mukund. If approved, this will be saved until the CRMM expiry date.
    - The CPO will be saved as a draft and will be visible in the PO listing screen with a status of Pending Approval. It will not be visible in the CPO details sheet until approved.
    - Once Mukund approves for any CRMM approved plant for the first time, future approvals for the same plant's core category will not be required at the transaction level.

3. UI Validation for Non-Approved CRMM Plants:
    - If a user selects CRMM as the CPO item type for a non-approved plant, show a UI validation error: "This plant is not an approved CRMM plant, so punching of orders with type CRMM is not allowed!"

4. Handling Internal Plants:
    - For internal plants, the RFQ item ID will remain optional, and any CPO item type can be punched.

5. RFQ Item ID Handling for CRMM Plants:
    - RFQ item ID will be optional for all CPO items punched for CRMM approved plant IDs.

6. Mandatory L1 & L2 Categories at Manual Punching Stage:
    - The L1 & L2 categories columns will be mandatory and pre-filled using the existing analytics API, except for Bulk PO. If no suggestion is available, users will manually select from a dropdown.

7. Prioritization of Mapped RFQ Item IDs:
- If an RFQ item ID is mapped to a CPO item ID, the L1 & L2 categories will be prioritized.

**Impact:**
- Core Category Margin Improvement: This automation improves margins for core categories, particularly for non-CRMM orders.
    - MRO Net GM%: ~2.82% per month
    - MRO Sales: 98 Lacs/month
    - MRO GMV: 3Cr per month for core categories, with no expected increase in this number.

## Task 24: (EOC-3225) CRMM Automation - CRMM Customer Level Renewal Workflow

**Description:**

The task focuses on automating the CRMM customer renewal workflow by tagging Core/Non-Core L1 categories in the CPO details and triggering renewal reminder mailers for CRMM expiry dates at the customer level.

**Scope of Work:**

1. Tagging Categories:
    - Add Core/Non-Core L1 Category next to L2 in both the CPO details sheet and the download sheet.

2. Mailer Triggers:
    - Primary Mail Trigger:
        - Trigger a mail to city heads 7 days before the CRMM expiry date for a plant.
        - Recipients: City heads and regional heads, with the following exceptions:
        - For North and South: Mail to `rupesh.kharbanda@moglix.com`.
        - For East and West: Mail to `anik.basu@moglix.com`.
        - Ahmedabad and Pune: Mail to `ashu.garg@moglix.com`.
        - Exclude `ashu.garg@moglix.com` and kumar.rohit@moglix.com as recipients.
        - CC: `ruchi.garg@moglix.com` and respective CRMM plant city heads.
    - Regional Head Approval:
        - Mail the Regional Head based on plant-region mapping (for multiple heads, any one can approve).
        - Mail to be triggered 7 days before the expiry, with a reminder on the expiry date.
        - Only the Regional Head can approve.
    - Reminder Mail Trigger:
        - A reminder will be sent at 6 AM on the day of expiry if no action has been taken (approval or rejection).

3. Userflow for Mailer:
    - If a company has multiple plants and a CRMM expiry is approaching for one plant, the mail will include a summary of all CRMM plant expiry dates for the customer.
    - Extend validity only for plants expiring within the next 90 days, with all plants receiving the same expiry date (3 months from the first expiring plant if approved).

4. Approval/Rejection:
    - Users can Accept/Reject through a CTA in the mail. Upon approval, the CRMM validity dates will be automatically updated in the account service for the specified plant IDs.

5. Mail Content:
    - Subject Line (Initial Mail): [Review and Extend] CRMM business for <customer name> <company ID>
    - Subject Line (Reminder Mail): [Expiring Today] Approve CRMM business for <customer name> <company ID>
    - The mail body remains unchanged between the original and reminder mail.

**Design:** The design will follow the Core Category approval EDM with the City Head Email ID added below the plant name.

**Data Source:** The mailer data will be fetched from analytics, and Tanya has already shared the details.

**Impact:** Streamlines the CRMM renewal process, automates reminders, and ensures timely approval for expiring plants, reducing manual intervention and improving efficiency.

## Task 25: (EOC-3152) Allow Category Update in Enquiry Details Sheet

**Description:** The task involves enabling updates to the L1 and L2 categories in the Enquiry Details Sheet when no category suggestions are provided by the Analytics API, even if the enquiry type and customer POC are blank.

**Scope of Work:**

- Allow users to manually update L1 and L2 categories in the Enquiry Details Sheet when no suggestions are available from the Analytics API.
- This functionality will apply even if the enquiry type and customer POC fields are blank.

**Impact:** Enables flexibility for users to manually assign categories, improving data accuracy and ensuring categories are updated even in the absence of automated suggestions.

## Task 26: (EOC-3192) Introduce VMI/JIT Tagging & Edit CPO Number

**Description:**

The task involves adding VMI/JIT tagging in various CPO-related workflows and introducing an editable CPO number option for email confirmation cases.

**Scope of Work:**

1. VMI/JIT Tagging:
    - CPO Punching (Header Tab):
        - Introduce an Inventory Type field with two values: VMI and JIT.
        - If VMI is selected, an additional dropdown will appear to select the VMI Owner: Moglix, Supplier, Customer.
        - If VMI with Customer ownership is selected, further options to select Customer Plant ID and VMI 60, 180 dropdown will appear.
        - In the CPO Details section, a new column titled Inventory Type will be added with values: VMI - Moglix, VMI - Supplier, VMI - Customer, or JIT.
        - Pass the selected values to SalesOps for further consumption.
        - If the plant ID is internal, JIT will be disabled, and VMI will be the default selection.
2. Editable CPO Number (Email Confirmation):
   - In Punch PO > Header, add a checkbox titled Email Confirmation next to the CPO Number field.
   - If the Email Confirmation checkbox is selected, the CPO Number field becomes optional (it may or may not be available).
   - For previously created POs where Email Confirmation was enabled, allow users to edit the CPO number and add attachments.
3. UI Design:
- Implement design changes to the Punch PO, Edit PO, Cancel PO, and Cancel & Clone PO screens, as per Flow 8.
4. Download Sheet & CPO Details Updates:
    - Introduce a new column titled Inventory Type with possible values: VMI - Customer and JIT.
    - Position the new column between RFQ Item ID and Allocated Inventory.

**Impact:**

Improves inventory management by allowing VMI/JIT tagging and ownership selection, while enabling greater flexibility in handling email confirmation cases by allowing edits to CPO numbers and adding attachments. This reduces manual errors and enhances the PO workflow.

## Task 27: (EOC-3147) Introduce Bulk Upload as a Feature in CPO Details Screen

**Description:**

The task involves enhancing the existing bulk OMT remarks template by adding new columns and renaming the template to CPO Bulk Upload Template.

**Scope of Work:**

1. New Columns for Bulk Upload:
    - Supplier ID
    - Final TP/Unit
    - Lead Time
    - Plant ID
    - CPO No.
    - Item ID (mandatory for non-HZL)
    - Line No. (mandatory for HZL; Item ID optional)
    - CPN (mandatory for HZL)
    - Pickup Warehouse
    - Delivery Type
    - OMT Status
    - OMT Bucket
    - OMT Remark
    - Supplier Follow-up Date (mm/dd/yyyy)
    - Note: Based on the Supplier ID, fill in Supplier Name and Supplier Credit Terms.

2. Template Validations:
    - For Team Kohinoor, upload data by checking the combination of CPO No + Plant ID + Line Number and update line items in the CPO details.
    - For other customers, update details in the CPO details sheet based on Item ID.
    - If any data is present against a line number and new data is uploaded in the template, it will override the existing data, ensuring the Supplier ID is active.
    - Ignore any blank fields in the template during upload.
3. User Guidance:
    - Attach the file that the HZL CS executive receives from the customer, which will serve as a guide for filling data in the new template.

**Impact:**

Streamlining the bulk upload process improves efficiency in managing CPO details, reduces manual entry errors, and enhances data accuracy by standardizing the upload format.

## Task 28: (EOC-3173) Remove Plants Group Field from CPN Creation (Product Upload) Workflow

**Description:**

The task involves removing the Plants Group column from the CPN creation template and backend due to redundancy and user confusion.

**Scope of Work:**

1. Remove Column:
    - Eliminate the Plants Group column from the CPN creation template.
    - Ensure the column is also removed from the backend.
2. Validation During Upload:
    - Implement validation to ensure that the Plants Group column does not exist in the upload process.
    - If the column is included, generate an error report stating: "Incorrect template used - remove Plants Group column."

**Impact:**

This change simplifies the CPN creation process, reduces user confusion, and ensures a more streamlined workflow by eliminating unnecessary fields.

## Task 29: (EOC-3187) Add Cancel and Clone Reasons at Order and Item Level

**Description:**

The task is to introduce cancel and cancel-and-clone reasons at both the order and item levels.

**Scope of Work:**

1. User Workflow Enhancements:
    - When clicking Cancel or Clone PO from the PO listing, a modal will open for confirmation with Yes and No CTAs.
    - Enhance this modal to include a dropdown for cancel and clone reasons with checkboxes for multi-select, including the following options:
        - Change in SP/Unit
        - Change in HSN
        - Change in Quantity
        - Manual Error during Punching
        - Others (with remarks field)
2. Consistency Across Features:
    - The same dropdown with reasons will appear for both Cancel and Clone PO actions and for Cancel and Clone Line Item actions.
3. Backend Storage:
    - Save the selected reasons in the backend at the CPO item ID level.
4. CPO Details Screen:
    - In the revamped CPO Details screen, under the Cancel and Cloned tab, display the cloned reasons in the listing and include them in the download dump under a new column titled "Cloned Reason."

**Impact:**

This enhancement allows for better tracking of reasons behind cancellations and clones, improving accountability and data accuracy while providing valuable insights into order management processes.

## Task 30: (EOC-3175) Improve Search by Quotation No. in Enquiry Details Screen

**Description:**

The task involves improving the handling and search functionality for the Quotation Number in the Enquiry Details screen.

**Scope of Work:**

- Quotation Number Storage:
    - Save the Quotation Number without any prefix (i.e., no alphabets) and display this format in the Enquiry Details screen and the download sheet.
- Global Search Enhancement:
    - Introduce a global search feature for Quotation Number in a floating search bar.
- Column Filter Functionality:
    - Allow users to search using the column filter of the Quotation Number column by entering numbers only. For example, entering 240013180 should return results for enquiries matching that item.
- Data Migration:
    - Ensure that quotations with numbers from January 2023 onwards are searchable across downloads, searches, and listings.

**Impact:**

This enhancement improves the usability and efficiency of the Enquiry Details screen by providing a clearer and more effective search functionality, facilitating easier access to relevant quotations.

## Task 31: (EOC-3173) Remove Plants Group Field from CPN Creation (Product Upload) Workflow

**Description:**

The task is to eliminate the Plants Group column from the CPN creation template and backend due to its redundancy and the confusion it causes for users.

**Scope of Work:**

- Remove Column:
    - Eliminate the Plants Group column from the CPN creation template.
    - Ensure that this column is also removed from the backend.
- Validation During Upload:
    - Implement validation to ensure the Plants Group column does not appear in the upload process.
    - If the column is included, generate an error report stating: "Incorrect template used - remove Plants Group column."

**Impact:**

This change simplifies the CPN creation process, reduces user confusion, and ensures a more streamlined workflow by eliminating unnecessary fields.

## Task 32: (EOC-3074) Need Report of Productivity Dashboard on Date Basis/Weekly/MTD

**Description:**

The task is to create a report for the productivity dashboard using the specified column format in the attached template.

**Scope of Work:**

- Report Format:
    - Use the attached Productivity Dashboard Report template for structuring the report.
- Frequency of Reports:
    - Monthly Report:
        - Generate the report on the 1st of every month with data from the previous month and send it to the product team (Arpita and Ruchi).
    - Simulation Report:
        - Before the productivity dashboard goes live, run a simulation on production data to generate productivity metrics for the week of 28th Dec - format.
- Download Functionality:
    - Introduce a Download CTA inside the Productivity Widget for the available reporting frequency.

**Impact:**

This task enhances the reporting capabilities of the productivity dashboard, ensuring timely and structured communication of productivity metrics to relevant stakeholders.

## Task 33: (EOC-3293) Allow New Line Item Addition in Open PO for HMCL

**Description:**

The task involves enabling the addition of new line items to Open POs specifically for HMCL plants, with considerations for validity dates and uniqueness of CPNs.

**Scope of Work:**

- User Workflow:
    - In the CPO Listing, when a user clicks on the three dots (⋮) and selects Edit PO, an option to add a new line item should be presented.
    - Users should be allowed to add new line items only while the validity date is active.
    - After the expiry date, the CPO will automatically close, preventing any new line item additions.
- Validation for New Line Items:
    - Ensure that the CPN being added is new and not already present in the Open PO. Only unique CPN line items should exist.
- Limitation:
    - This feature is applicable only for the Edit PO functionality.

**Impact:**

This enhancement allows for flexibility in managing Open POs for HMCL plants, ensuring that users can add necessary line items while maintaining data integrity through CPN uniqueness.

## Task 34: (EOC-3269) Introduce Reports Section in Navigation in EOC

**Description:**

The task is to add a Reports section to the navigation menu in EOC to enhance access to various reporting features.

**Scope of Work:**

- Navigation Structure:
    - Position the Reports section between Others and Account Service in the L1 navigation.
    - L1: Reports
        - L2:
        - Enquiry Pendency - Phase 1
        - CPO Pendency
        - ARC Accounts Performance - Phase 1
        - CB & ES Mapping List
        - TAT Measurement
- User Workflow:
    - Enquiry Pendency Report:
        - Visible only to managers (where account service manager flag = true).
        - Clicking this report will open a new screen displaying a list of email IDs of employees.
        - Refer to Jira EOC-3089 for detailed functionality of this screen.
    - CPO Pendency Report:
        - Also visible only to managers (where account service manager flag = true).
    - ARC Accounts Performance:
        - Three tabs will be available upon clicking the ARC Accounts Performance section.
        - Default data will display for the last 3 months, last 6 months, last 9 months, and last 12 months.
    - CB & ES Mapping List:
        - Show the current mapping of CB & ES with an option to download based on dates.
        - Preview of 10 records will be visible upfront.

**Impact:**

Introducing the Reports section improves navigation and accessibility to critical reports, enabling managers to make informed decisions based on real-time data and enhancing overall operational efficiency.

## Task 35: (EOC-3295) PO Punched on Email Confirmation: PO Number Update and PO Copy Upload

Description:

The task is to tag POs received through email and allow users to update the PO number and upload the PO copy once received from the customer.

**Scope of Work:**

- User Interface Enhancements:
    - When users attempt to punch a PO, a checkbox labeled “No PO PDF, only email confirmation received” will appear under the header tab.
    - Once the checkbox is selected, the CPO number will auto-fill with the current date and time stamp, formatted as “Email confirmation DD/MM/YYYY HH.” Users can modify this number if needed.
- Backend Tagging:
    - EOC will store a separate tag for POs punched based on email confirmation in the backend, ensuring tracking for reporting purposes, even if a CPO number is received.
- CPO Number Update:
    - After punching the CPO, users can update the CPO number and upload the PO copy received from the customer until the status is Delivered with POD.
    Upon updating in EOC, the CPO number will be shared with SalesOps, who will then send the details to EMS to update the invoice.
- Constraints on PO Number Update:
    - The system will not allow the update of the PO number for invoices where a Credit Note (CN) has been created.
    - If a CN is created for the full quantity, updating the PO number and uploading the PO copy will not be allowed in EOC.
    - If the total CNs are for a partial quantity, users can update the PO number and upload the PO copy, but invoices for CNs will not have the PO number generated. The remaining invoices pending will still include the PO number.
- Soft Alerts:
    - If users attempt to update the CPO number and PO PDF after the status is Delivered with POD, a soft alert will be shown: “We are saving CPO number and PO PDF, but this information will not be passed to the Customer Invoice.”

**Impact:**

This enhancement allows for greater flexibility in managing POs received via email, streamlining the process of updating PO details and ensuring accurate invoicing while maintaining necessary checks and validations.

## Task 36: (EOC-3312) PAAS CPO-SPO Creation Automation

**Description:**

The task is to automate the creation process from CPO to SPO for non-integrated customers in the PAAS business, enhancing efficiency and reducing manual intervention.

**Why?**

Currently, in the PAAS business, when a user receives a CPO from customers, the corresponding SPO details are also available. However, the existing system requires manual and sequential processing, which is time-consuming.

**What?**

To address this issue, we aim to implement end-to-end automation from CPO to SPO for non-integrated customers.
  - Phase 1: Automation will extend to supplier assignment. After that, users can check and send the SPO.
  - Phase 2: Based on feedback, SPO will be released automatically.

**User Workflow:**

- Tagging and Validation:
    - Add "PAAS" in CPO item type to identify PAAS transactions, restricting tagging based on customer, plant, validity date, and authorized users.
    - In case of manual punching, show a UI validation error if the user selects a PAAS transaction but is not authorized or if the customer is not a customer
- Upload Functionality:
    - Introduce a CTA under CPO labeled “Bulk Punching,” which will lead to “CPO-SPO Creation.”
    - A new screen will allow users to upload details of CPO & SPO along with PO copies based on PO number.
    - Listing fields will include:
        - File Name
        - Date
        - Status
        - Result
- Dynamic Status Indicators:
    - Statuses to be shown include:
        - Success
        - Failed
        - In-Progress
        - Partial Success
- Preprocessing Workflow:
    - Upon submission, EOC will preprocess the file to check for mandatory fields for CPO and SPO creation based on existing validations.
    - If preprocessing fails for any line item, the status will change to Failed.
    - If all items pass preprocessing, the status will change to Success or Partial Success if supplier assignment fails for any item.
- Points to Note:
    - All existing validations and functionalities will remain operational.
    - The system must handle multiple suppliers for a single item.
    - Manual Punch CPO will function as is, with the addition of the PAAS transaction type.

**Impact:**

The PAAS CPO-SPO creation automation increases efficiency and reduces processing time by eliminating manual tasks, minimizes errors, enhances customer satisfaction, improves tracking and reporting, allows for scalability, ensures compliance, and optimizes resource allocation.

## Task 37: (EOC-3337) LD Applicability at Line Needs to be Added for PAAS Customers While Punching

**Description:**

The task is to introduce the "LD Applicable (Y/N)" field for PAAS customers during the punching process, based on tagging in account service and validity dates.

**Scope of Work:**

- Field Introduction:
    - For non-integrated PAAS customers, display the "LD Applicable (Y/N)" field during the punching process, ensuring it reflects the tagging in account service and the validity date.
- Field Validation:
    - Implement validation to ensure that only "Y" (Yes) or "N" (No) can be entered in the "LD Applicable" field.
- Screen Applicability:
    - This change will be applicable to all relevant screens involved in punching and editing processes.

**Impact:**

This enhancement allows users to easily determine the applicability of LD for PAAS customers, improving accuracy in order processing and ensuring compliance with business rules.

## Task 38: (EOC-3351) CM* Approval Visibility Impacted Due to Access of Teams to Approvers

**Description:**

The task addresses the visibility issues related to CM* approval requests due to approvers not being aware of newly created teams.

**Problem Statement:**

- When a new team is established, approvers as per the Delegation of Authority (DOA) for CM* are often unaware of these new teams. Consequently, may teams leading to situations where approval requests for CM* are raised and remain pending without the approver's knowledge.
- This lack of visibility results in delays, manual coordination efforts, and potential escalations.

**Proposed Solution:**

- Enhance the Pending CM Approval screen* to display a complete list of pending requests associated with each username upfront.
- This visibility allows approvers to see all pending approvals immediately without the need to filter by team.
- If necessary, approvers can still use a team filter to narrow down the list to specific teams, although the complete list will be visible by default.

**Impact:**

This solution improves the visibility of CM* approval requests, facilitates timely approvals, and reduces manual coordination efforts, thereby enhancing overall efficiency in the approval process.

## Task 39: (EOC-3354) PaaS PR Details

**Description:**

Currently, in the PaaS customer environment, the entire enquiry/PR process is managed by Moglix on the customer's ERP system. There is no systemic mechanism to track all such PRs, leading the team to manually download and manage Excel sheets. To provide complete actionable visibility in one place, it is necessary to incorporate PR tracking in EOC.

**Requirements:**

- PaaS Header:
    - Add a “PaaS” header at the top of the relevant pages, visible only to users with the role access “PaaS PR Punching.”
- Sub-Headers under the PaaS Header:
    - PR Summary
    - PR Details
    - PR Dashboard
- PR Summary Page:
    - Upon clicking PR Summary, users will navigate to the PR Summary page (design referenced as PaaS Summary).
    - A “Download Template” button will be available on the top right (ignore any specific text mentioned in the design).
    - After filling out the required fields in the downloaded template, users can click on “Upload Template.”
- Download Template Format:
    - Refer to the sheet “Download Upload Template,” which includes a list of validations for fields (see PR Dashboard Discussion.xlsx).
    - Upon uploading, the line items reflecting the uploaded file will appear (latest items first).
- Status Indicators:
    - The status of the file will initially be “Upload in Progress.”
    - If all validations pass, the status will change to “Successfully Uploaded,” and an output file will be generated.
    - If any validations fail, the status will change to “Validation Failed,” accompanied by a failure output file.
- Output Files:
    - For “Successfully Uploaded” Status:
        - The output file will include PR ID and PR Item ID created against uploaded items.
    - For “Validation Failed” Status:
        - The output file will include the reasons for failure for respective line items.
- Search and Filter Functionality:
    - Search on “PR Summary”:
        - Search functionality will work based on the file name.
    - Filters on “PR Summary”:
        - Filters will include status options (“Upload in Progress,” “Successfully Uploaded,” “Validation Failed”) and date of creation/upload.
- PR Details View:
    - Once the file is “Successfully Uploaded,” items will start reflecting in the PR Details view.
    - Search and Filters on PR Details Sheet:
        - Floating Search: PR ID, PR Item ID, CPN
        - Filters with multiple selection options: Customer Name, Broad Stage, PR Item Creation Date, PR Type, PR Aging Bucket, Sourcer 1, Sourcer 2.
- Field Management:
    - First 10 columns (up to short text) will remain frozen.
    - Make/Brand, L1 & L2 Category will be fetched from the analytics API. If no input is received, users can update these details from a valid list already used by EOC.
- Download PR Dump:
    - Add a “Download PR Dump” CTA similar to the “CPO Dump Download.”
- Role-Based Management:
    - Role-based deletion/closure of line items will be allowed. Users can select checkboxes and use the “Close Item” CTA to delete items.
    - Users will only see their own PRs, while managers will have a view of all users’ PRs.

**Impact:**

Incorporating the PR tracking system into EOC provides a centralized and systematic approach to manage PaaS customer PRs, improving visibility, reducing manual errors, and enhancing overall workflow efficiency.

## Task 40: (EOC-3261) Make EOC Web-Responsive for Login

**Description:**

The task is to ensure that the EOC platform is web-responsive, enabling users to access the CM approval screen and account service from mobile devices.

**Scope of Work:**

- Responsive Design Implementation:
    - Update the EOC web interface to be fully responsive across various screen sizes, focusing on mobile usability.
    - Ensure that the layout, buttons, and input fields adapt seamlessly to different mobile resolutions.
- Testing Across Devices:
    - Conduct thorough testing on multiple mobile devices and browsers to ensure functionality and usability.
    - Verify that all features, particularly the CM approval screen and account service, are accessible and user-friendly on mobile.
- User Experience Enhancements:
    - Optimize touch interactions for mobile users, ensuring that buttons are adequately sized and easily accessible.
    - Improve navigation elements to be mobile-friendly, providing a smooth user experience.

**Impact:**

Making the EOC platform web-responsive enhances accessibility for users on mobile devices, improving their ability to manage CM approvals and access account services on the go, ultimately leading to increased efficiency and user satisfaction.

## Task 41: (EOC-3421) Bulk Packaging Invoicing PO Copy Upload Functionality Enhancement

**Description:**

The task involves enhancing the PO copy upload functionality in the bulk packaging invoicing workflow to improve validation and automation processes.

**Scope of Work:**

- Upload Restrictions:
    - Implement restrictions on PO copy uploads to ensure that automation is not initiated until validation is successful.
    - If validation fails for any line item, the PO copy upload CTA will not be visible for validated line items.
- Automation Initiation:
    - Once the PO copy is successfully uploaded, automation processes will be initiated.
- UI Changes:
    - Hide the CTA for “Bulk PO Order Mapping,” as this customer use case is now redundant.
    - Move the “Upload PO Copy” CTA to the top above the actions section, ensuring that the action “Upload PO Copy to Proceed” is clearly visible.
- Single Customer Data Upload:
    - Ensure that only single customer data uploads are allowed.
    - If bulk POs are uploaded for both customers (Zepto with Group ID 12784 and Kiranakart with Group ID 10956), provide users with the option to upload separate files for each customer.
- Handling Multiple Customer Data:
    - In case multiple customer data is uploaded that includes both Zepto and Kiranakart, users will need to upload a PO copy against the respective PO numbers.
- Visibility of Uploaded Items:
    - If the PO copy has not yet been uploaded, the latest uploaded items will still be visible in the Bulk PO Creation screen, allowing users to upload the necessary PO copies.
- Design Reference:
    - Flow 14: Please refer to the attached flow diagram for visual guidance on the UI enhancements and functionality.

**Impact:**

This enhancement improves the efficiency and accuracy of the bulk packaging invoicing process by ensuring that only valid PO copies are uploaded, thereby streamlining automation and reducing errors in the workflow.

## Task 42: (EOC-3456) Catalog Screen Enhancement

**Description:**

The task involves several enhancements to the Catalog Screen to improve usability, reduce mapping time, and provide better visibility of important information.

**Enhancements:**

- Brand Filter Addition:
    - Feature: Add a Brand Filter at the top of the page, next to the “Need to Work” section.
    - Impact: This will reduce junk MSN by 5% of the overall mapping count (approximately 22K/month) and decrease mapping turnaround time (TAT) by 45 minutes to 1 hour.
- Add “Is ARC” Column:
    - Feature: Introduce an "Is ARC" column in the catalog view next to the CPN column. The team must check this status for all “SA” orders before mapping.
    - Impact: This enhancement will save approximately 1 minute per resource for each SA order line item, with an estimated SA line item count of 9,000 per month.
- Rewiring Logic of Catalog Status Filter:
    - Feature: Modify the Catalog Status Filter so that selecting any value will display only records where MSN is not assigned.
    - New Filter: Add an “MSN Assigned” filter before the Catalog Status filter, with a default setting of No to focus on items where MSN is not assigned.
    - Impact: This adjustment will save approximately 15 seconds of load time each time the filter is applied, with around 25-30 instances per day per user. For a total of 4 users, the overall saving equates to 12.5 hours per month.
- Audit Feature:
    - Feature: Display an Audit Button in the catalog view for the "Remarks from Business" column, similar to the visibility on the CPO item sheet. This feature allows quicker access to audit logs without needing to navigate to the item sheet.
    - Impact: Users will be able to quickly see the sourcer name associated with the MSN shared, improving accountability and tracking.

**Overall Impact:**

These enhancements will streamline the catalog management process, reduce time spent on mapping and searching for information, and improve the overall efficiency of the team handling catalog entries. By implementing these features, the organization can expect a significant boost in productivity and a reduction in manual errors.

## Task 43: (EOC-3461) PaaS PR Dashboard

**Description:**

The PR Pendency Dashboard will provide a comprehensive view of PR pendencies across various stages for PaaS customers.

- Definition of PR Pendency: The following broad statuses will be considered as PR pendency:
    - PR Received
    - RFQ Sent to Supplier
    - Supplier Follow-up Done
    - Quote Received – Partial
    - Quote Received – Complete
    - TR - Sent for Approval
    - TR - Under Clarification
    - TR – Approved
    - Comparison Sheet
    - Negotiation / Auction
    - NFA / Term Sheet

**Dashboard Features:**

- User Views:
    - Manager View: Allows selection of multiple sourcers.
    - Sourcer View: Displays individual sourcer as default.
- Filters:
    - Sourcers/Buyers: Managers can select multiple sourcers; individual sourcers are set by default.
    - Customers: Filter based on customers in pendency.
    - Categories: Filter based on categories in pendency.
    - Duration: Filter based on the PR received date.
    - Buttons: Apply and Reset buttons will be available beside the filters.
- Data Display:
    - The total count of “All PR Pending” and “Total Sourcers” will be displayed below the filters.
    - The pendency graph and its data will adjust based on the selected filters.
- Pendency View:
- The left section under “All PR Pending” will show PR pendency against each sourcer arranged in descending order. Clicking on any PR pendency count will navigate the user to the PR sheet with filtered data.
- Graphs and Visualizations:
    - Graph 1: PR against customers displayed in a bar chart, showing customer-wise PR pendency. Customers with zero pendency will not be displayed. over a reveals counts; double-clicking navigates to the PR sheet.
    - Graph 2: PR pendency by type displayed in a pie chart. Hovering reveals counts; double-clicking navigates to the PR sheet with filtered data.
    - Graph 3: PR Deadline Crossed cases in a bar chart, showing counts and allowing navigation to the PR sheet for specific filters based on overdue status.
    - Graph 4: PR pendency breakdown by aging buckets displayed in a pie chart, with navigation available on double-clicking.
    - Graph 5: PR pendency by broad stage with counts and average aging shown in a horizontal bar chart, enabling navigation to the PR sheet.
    - Graph 6: PR pendency categories count displayed as hollow pies, allowing navigation to the PR sheet on clicking.
    - Graph 7: L1 and L2 categories with respective PR pendency counts, allowing navigation to the PR sheet on clicking.
    - Graph 8: Brand-wise PR pendency count, providing navigation to the PR sheet with necessary filters.
- Implementation:
    - Ensure the dashboard is user-friendly and provides actionable insights.
    - Make sure that each element is interconnected, allowing users to easily navigate from visual representations to detailed data.

**Impact:**

The PaaS PR Dashboard will enhance visibility into the PR pendency process, allowing users to track, manage, and act on PR requests efficiently. It reduces manual effort, improves accountability, and helps identify bottlenecks in the PR workflow, ultimately leading to better decision-making and operational efficiency.

## Task 44: (EOC-3409) ARC Report Enhancement

**Description:**

The task involves updating the ARC report based on inputs received from Ruchi to enhance the visibility and usability of the report.

**Changes Required:**

- Report Overview:
    - The new report will incorporate ARC type and count from the summary section.
- Renaming Fields:
    - Change the label "GM %" to "Sales GM %" to better reflect the content.
- Hide Unnecessary Data:
    - Total GMV and CM1% will be hidden in the report to streamline the information presented.
- Expired Tab Adjustments:
    - The validity from and to fields in the Expired Tab will be fetched from the EOC summary, ensuring that users see the correct validity dates.
- Download Feature:
    - Implement a Download Feature for both the ARC and Expired tabs, allowing users to export data as needed.
- Tab Management:
    - Discard the 2nd tab from the report to simplify the overall structure.

**Impact:**

These enhancements will improve the clarity and functionality of the ARC report, providing users with essential data while eliminating unnecessary information, thereby facilitating better decision-making and reporting efficiency.

## Task 45: (EOC-3483) CPO Item Type "PAAS" Visibility Control

**Description:**

The task is to ensure that the CPO item type "PAAS" is not visible to users who do not have the necessary role access to perform PAAS transactions.

**Requirements:**

- Role-Based Access Control:
    - Users must have the role “PAAS CPO Punching” to view and interact with the CPO item type "PAAS."
- Visibility Logic:
    - Implement logic to hide the "PAAS" item type from users without the required role access. If a user attempts to access the CPO creation screen without the appropriate permissions, the option for "PAAS" should not be displayed.
- Reference Information:
    - Refer to Jira EOC-3312: PAAS CPO-SPO Creation Automation for details on the implementation requirements.
- Role Definition:
    - Collaborate with @Rishabh Verma to define the role name “PAAS CPO Punching” and its purpose clearly, ensuring that users understand the access rights and functionalities associated with this role.

**Impact:**

This enhancement will enhance security and user experience by ensuring that only authorized users can view and interact with the PAAS CPO item type, thereby preventing unauthorized access and potential errors in order processing.

## Task 46: (EOC-3487) Released SA Enhancement

**Description:**

This task involves enhancing the functionality of Released SA (Service Agreement) in response to the dynamic needs of Brake India regarding Open POs/SA received from customers.

**Problem Statement**

Brake India frequently updates its Open POs/SA, necessitating the following functionalities:
  - Addition of Line Items: Customers may want to add new items to their existing SAs.
  - Adjustment of Quantity: Customers may need to increase or decrease the quantities specified in the SA.

**EOC Scope of Work**

- Addition of Items:
    - Implement functionality that allows users to add items to released SAs. This feature should enable seamless updates to existing agreements.
- Updating Quantity:
    - Enable users to update the quantities in the released SA based on customer requests.
    - For cases where the quantity is being reduced, ensure that the maximum reduction is allowed only for pending quantities, specifically for those where delivery schedule has not yet been created.

**Impact:**

These enhancements will improve flexibility and responsiveness to customer needs, ensuring that Brake India can effectively manage and update their service agreements in real time, ultimately leading to improved customer satisfaction and operational efficiency.

## Task 47: (EOC-3502) Enquiry Pendency - Productivity Dashboard for Managers

**Description:**

This task involves updating the Enquiry Pendency section in the Productivity Dashboard for Managers to improve visibility, segregation, and flow monitoring based on Sourcer POC and Customer POC status.

**Change 1: Pendency Segregation by Status**

- Current Issue:
    - Currently, pendency statuses are counted under both Sourcer POC and Customer POC, leading to inflated numbers.
- Requirement:
    - Modify the total pendency count and percentage based on specific statuses, ensuring that a single item is only counted in either Sourcer POC or Customer POC, not both.
    - Customer POC Pendency: Include the following statuses:
        - CM Approved
        - Clarification
        - Quotation Received From Supplier
    - Sourcer POC Pendency: Include the following statuses:
        - Created
        - eRFQ Response Received-Read
        - eRFQ Response Received-Unread
        - Sent to Supplier
        - Working
    - Pendency Count Formula:
        - Sourcer POC Pendency = Created + eRFQ Response Received (Read/Unread) + Sent to Supplier + Working.
        - % Pendency = Total Pendency / Grand Total.

**Change 2: Status Representation**

- Requirement: The status mentioned on the UI should clearly indicate whether it belongs to Sourcing POC or Customer POC.
    - Design Changes:
        - Add hover text:
            - For Customer POC: “Status belongs to Customer POC Pendency.”
            - For Sourcer POC: “Status belongs to Sourcer POC Pendency.”

**Change 3: Grand Total Highlighting**

- Requirement: Based on the Grand Total of pendencies, highlight the Grand Total, Total Pendency, and % Pendency in different colors based on the thresholds below:
    - Green: Grand Total > 350 (High Flow)
    - Yellow: Grand Total between >250 and <=350 (Medium Flow)
    - Red: Grand Total < 250 (Low Flow)

**Change 4: Sorting Functionality**

- Requirement: Enable sorting functionality on all headers in the Productivity Dashboard to allow users to sort by the data they find most relevant.

**Impact:**

These changes will improve the accuracy of pendency tracking, provide clear representation of whether the pendency is related to a Sourcer or Customer POC, and give managers a better understanding of workflow status through the use of color-coded flows. Additionally, the sorting feature will enhance usability, enabling managers to quickly access the most critical data points.

## Task 48: (EOC-3510) Introduction of "Direct CPO" CPO Item Type

**Problem Statement:**

In the current system, CPO types (e.g., RFQ, ARC, CRMM) are restrictive and require an RFQ Item ID, even when customers send CPOs directly without prior quotes. This leads to unnecessary RFQ punching and inflates the RFQ conversion metric.

**Solution:**

Introduce a new CPO Item Type called “Direct CPO”, which allows processing CPOs without an RFQ Item ID.

**Key Features of the "Direct CPO" Type:**

- No RFQ ID Required:
    - When a CPO is received from a customer directly, there will be no need to provide an RFQ ID or RFQ Item ID.
- Order Creation and Approval:
    - After creating and approving the draft, the Direct CPO will remain in an unreleased state.
    - When users attempt to mark the Direct CPO as released, they will see an input screen to capture necessary sourcing details for SPO punching (Supplier ID, - Payment Terms, Delivery Type, etc.).
    - Once all required inputs are provided and marked "Released," the system will:
        - Check if CM*% approval is needed.
        - If no approval is required, the system will auto-approve and release the CPO.
        - If approval is required, an email will be sent to the approver, with a status update to *“CM% Pending Approval”**.
- CM% Approval Process:*
    - The CM% approval* process will follow the existing RFQ DOA, using the Order ID instead of the RFQ ID.
    - Users can update supplier details and re-trigger DOA if needed.
- Additional Features:
    - New CPO Item Type: Prevent multiple item-type selection when a Direct CPO is received.
    - Status Tracking: The CPO sheet will include a new CM Approval Status column (values: Approved, Rejected, Pending from Approver, Auto Approved).
    - Downloadable Reports: All new columns (e.g., CM Approval status, Approver/Rejector) will be included in the download dump.
- UI Changes:
    - A new screen will be created to handle CM approvals for Direct CPOs, repurposing the existing RFQ approval screen to include CPO tagging.

**Key Considerations:**

- Open vs. Closed PO:
    - Open POs cannot be classified as Direct CPO. This type is only valid for Closed POs.
- Cancellation Rules:
    - Cancellation of PO/item is allowed until MRN DONE.
    - If the updated CPO CM*% is >=0 after removing a cancelled item, cancellation will be allowed.
    - Restrict cancellation if CM*% becomes negative.
- Excluded Functionalities:
    - Direct CPO functionality will not be valid for Service Agreements (SAs) and Repeat PO functionality.
- System Integration:
        - SalesOps: Check and plan for potential impact.
        - Power BI/Analytics: Ensure proper tagging for reporting.
**Risks:**

- Cancellation of Items:
    - Risk of cancellation in cases where a high-margin CPO-item is cancelled after CM*% approval at the CPO level.
- Supplier Identification:
    - Users must find suppliers for all items before sending SPOs, otherwise the process cannot be completed.

**Impact:**

This enhancement reduces manual effort, improves data accuracy by eliminating unnecessary RFQ entries, and introduces flexibility for processing direct customer orders

## Task 49: (EOC-3528) UAT Feedbacks - PR Dashboard

**Description:**

The task is to implement feedback from UAT (User Acceptance Testing) for the PR Dashboard to improve functionality and data accuracy.

**Changes Required:**

- Round Off Average PR Aging Days:
    - Implement rounding of the Average PR Aging Days to the nearest whole number to enhance clarity and precision in reporting.
- Add PR Type Filter:
    - Introduce a PR Type Filter to the PR Dashboard to allow users to filter the data based on the specific types of PRs (e.g., RFQ, Direct, etc.).

**Impact:**

These enhancements will improve user experience by providing more accurate and easily interpretable data, as well as enabling better filtering options to refine PR visibility in the dashboard.

## Task 50: (EOC-3537) PR Enhancement - Add PR Type Filter

**Description:**

This task involves enhancing the PR Dashboard by adding a PR Type Filter and incorporating the PR Number in the search functionality.

**Scope of Work:**

- Add PR Type Filter:
    - Implement a new PR Type Filter in the PR Dashboard, allowing users to filter results based on the type of PR (e.g., RFQ, Direct, etc.).
    - The filter should be positioned along with other filters like Customer, Sourcer, and Category.
- Add PR Number in Search:
    - Enhance the search functionality to allow users to search by PR Number.
    - This will enable quick access to specific PRs based on their unique identifier.

**Impact:**

These enhancements will improve usability by providing users with more refined filtering and faster access to specific PRs, streamlining the workflow and improving overall efficiency.

## Task 51: (EOC-3549) Remove Hard-Coded Roles and Move to Module Access Level

**Description:**

This task involves refactoring both the frontend and backend to remove hard-coded roles such as Kam2, Sourcer2, PR Manager, PaaS, etc., and shifting the role management to a more flexible Module Access Level.

**Scope of Work:**

- Remove Hard-Coded Roles:
    - Identify and remove all hard-coded roles in the system (both frontend and backend).
    - Example roles to be removed: Kam2, Sourcer2, PR Manager, PaaS.
- Shift to Module Access Level:
    - Move role-based access control to the Module Level, ensuring that access is determined based on module-specific permissions rather than hard-coded roles.
    - Define and manage roles at the module level in a more dynamic and configurable way.
- Designation-Based Access:
    - Roles such as Kam2 and Sourcer2 should be handled based on designation levels and tied to the specific modules they need access to.
    - Example: A Sourcer might have access to specific sourcing modules rather than being assigned a static role like Sourcer2.
- Module Access Example:
    - PR Manager: Instead of hard-coding a role for PR Manager, assign module access to users based on their designation or responsibilities (e.g., PR Module Access).
    - PaaS: Move the access control for PaaS transactions to module-level access, ensuring only designated users have permission to manage PaaS-specific functions.

**Impact:**

- Improved Flexibility: This change will allow greater flexibility in assigning roles and access rights, making it easier to adjust permissions as organizational roles evolve.
- Centralized Role Management: By shifting to module access levels, role management becomes more centralized and scalable, reducing the need for hard-coded permissions throughout the codebase.
- Enhanced Security: Dynamic role management at the module level ensures that access is restricted based on specific responsibilities, reducing the risk of unauthorized access.
- Maintainability: Moving away from hard-coded roles will simplify code maintenance and allow for more adaptable role-based access control in the future.

## Task 52: (EOC-3514) Allow CDD2 Update Exceptionally

**Description:**

Enable users to update CDD2 beyond 1 year, up to 2 years, with role-based access.

**Scope of Work:**

- CDD2 Update Extension:
    - Allow CDD2 updates up to 2 years, beyond the current 1-year limit.
- Role-Based Access:
    - Create a "CDD2 Update Beyond 1 Year" role to control access.
    - Only users with this role can update CDD2 between 1-2 years.

**Impact:**

Provides flexibility for exceptional cases while maintaining controlled access through role-based permissions.

## Task 53: (EOC-3516) Addition of Long Text for Bulk CPO/SPO Creation

**Description:**

In some SAP orders, long text is received and shared with SalesOps to include in the supplier PO. For non-integrated PAAS CPO punching, an optional "Additional Description" field needs to be added during Bulk CPO creation.

**Scope of Work:**

- Add Additional Description Field:
    - Introduce an optional "Additional Description" field during Bulk CPO creation.
    - This field will be reflected in the EOC CPO details sheet.
    - The information will also be passed to SalesOps for further processing.

**Impact:**

- Clarity & Instructions: The detailed description ensures that suppliers understand requirements precisely, providing legal clarity and specific instructions.
- Efficiency: Clear descriptions help avoid misunderstandings, minimizing delays and errors in fulfilling orders.

## Task 54: (EOC-3550) API Taking Time to Load - SA Updating Process is Slow

**Issue:**

- The getProductGroup API is taking more than 10 seconds to load. When multiple MSNs are involved, the delay multiplies, causing the updateSa API to be called later, resulting in a slow overall SA updating process.
    - Example: If there are 3 MSNs, the getProductGroup API takes 10 seconds per MSN, resulting in a total of 30 seconds before the updateSa API is triggered.

**Steps to Resolve:**

- Optimize getProductGroup API:
    - Investigate and optimize the getProductGroup API to reduce the response time.
    - Consider introducing batch processing if multiple MSNs are requested simultaneously to avoid repeated API calls.
- Asynchronous Processing:
    - Explore asynchronous handling for multiple MSN requests to reduce the overall delay in processing.
    - Allow the updateSa API to be called once all required data is loaded in parallel.

**Impact:**

Optimizing the getProductGroup API and processing multiple MSNs asynchronously will significantly reduce the time taken for the SA updating process, improving the overall performance and user experience.

## Task 55: (EOC-3486) Storage Location and Line Item Number for Brakes India


**Problem Statement:**

    - Line-item numbers need to be mentioned on the invoice based on the Purchase Order (PO) received.
    - Plant-wise store locations need to be indicated on the invoice based on the PO received.

**Solution:**

1. Line-Item Number on Invoice:
    - EOC Scope of Work:
        - Line-item numbers must be reflected on the invoice.
        - For Service Agreements (SA), a Sr. No. field will be added (already available during Delivery Schedule or PO punching).
        - The Sr. No. assigned during SA creation will remain unchanged and will auto-reflect while creating Delivery Schedules (DS).
        - Sr. No. will be passed to SalesOps/EMS for invoicing.
        - Mandatory for Brakes India: Ensure the Sr. No. is made mandatory during the SA creation.
2. Store Location on Invoice:
    - Plant-wise Store Locations:
        - Store location needs to be mentioned on the invoice for each plant. Plant-wise store location data will be provided by the user/business and stored in the Account service.
    - New Header Field:
        - Add a new field for "Store Location" at the header level, applicable to both SA and other PO punchings.
        - The Search functionality should work for both Store ID and Description (similar to how supplier suggestions work).
        - Make this field mandatory where applicable, allowing users to select from a list of store locations.
        - The store location will be passed to SalesOps/EMS for invoicing.

**Impact:**

- Faster Gate Entry: By including line-item numbers and store locations on the invoice, the gate entry process will be expedited.
- Faster Invoice Mapping: Improved invoice mapping at Brakes India's end, leading to quicker processing and fewer delays.

## Task 56: (EOC-3544) Customer ETA Enhancement on EOC

**Description:**

This task aims to enhance the Customer ETA functionality by allowing manual updates and refining the logic used to determine the estimated time of arrival (ETA) for deliveries.

**Current Logic:**

    - The ETA is initially based on CDD1 (Customer Due Date 1).
    - When CDD2 is updated, it takes precedence over CDD1.
    - If CDD2 is surpassed, the ETA remains as CDD2 unless manually updated on EOC.
    - Emails are triggered to the buyer, notifying them of items expected within the next 15 days.

**Requirement:**

- Phase 1:
    - Manual ETA Update:
        - Introduce a field for manual ETA updates.
        - If manually updated, this ETA will reflect in the existing Customer ETA field and take priority over the analytics logic ETA.
    - CDD2 Reason:
        - Add additional reasons to a dropdown for CDD2 updates:
            - On Hold by Customer
            - Lead Time Item - Short CDD
            - Backdated Order
            - PO Specs Change (GST/HSN/Price Issues)
            - Modification in Default Customer CDD
            - CX Aligned Consolidation of Deliveries to Customer Location
            - SPO Raising Constraint - Pickup Date > CDD1
            - CRMM Order Delay
            - Plant Blocked due to AR
            - Customer Schedule Awaited/Delayed
- Phase 2:
    - Add additional columns for bulk updates:
        - CDD2
        - CDD2 Breach Reason
        - Manual ETA
        - Reason for Delay
- Phase 3:
    - Make the Reason for Delay mandatory when ETA exceeds the Final CDD.
- Phase 4 (Future Consideration):
    - Address challenges currently impacting ETA automation:
        - STN Linkages
        - Consolidation of Deliveries
        - Moglix Express
        - Supplier Deliveries In Transit Time
        - Changing Pickup Dates
        - Partial Deliveries

**Impact:**

The enhancements will improve the accuracy and reliability of ETA information, provide users with the flexibility to manually update ETAs, and ensure clear communication with customers regarding delivery timelines. This will lead to better planning and coordination for deliveries, ultimately enhancing customer satisfaction.

## Task 57: (EOC-3578) PO Punching OCR

**Description:**

To reduce manual effort and minimize errors in punching CPOs, we will introduce OCR (Optical Character Recognition) technology. The system will read the uploaded PO copy and autofill fields based on the document contents.

**Implementation Details:**

- Checkbox for OCR Usage:
    - Introduce a checkbox next to the PO copy upload field (default selected).
    - Users can deselect the checkbox if they do not wish to use OCR.
- Auto-Population of Fields:
    - If the OCR is used, relevant fields will be auto-populated from the uploaded document.
    - Users can deselect the checkbox to clear all auto-populated fields.
- Highlighting Logic:
    - Auto-populated fields from the document using OCR will be highlighted in Yellow.
    - If the user modifies an auto-populated field, the color will change to Green.
        - Yellow: Indicates fields filled without manual intervention.
        - Green: Indicates fields filled with manual intervention.
- OCR Application:
    - OCR will be applicable on both header and line item screens.
- File Interaction:
    - Users can view, minimize, and maximize the uploaded file.
    - Users can copy fields from the visible PDF on the screen and paste them into the required fields.
    - An option to view the uploaded PDF in a separate tab will also be available.
- Daily Reporting:
    - Generate daily reports that include:
        - PO Number
        - Number of fields automated
        - Number of automated fields requiring manual intervention
    - If the checkbox is unselected, it will be considered as not automated.
- Initiative Duration:
    - This initiative will run for 1 month. After assessing the impact, a decision will be made on the next steps.

**Impact:**

    - Estimated Volume: Approximately 20,000 line items per month.
    - Time Savings: Each item currently takes about 2 minutes to process, but with OCR, this can be reduced to 1 minute, leading to an estimated savings of 250-300 hours per month.

Implementing OCR for PO punching will streamline the process, enhance efficiency, and reduce the likelihood of errors, ultimately leading to improved operational performance.

## Task 58: (EOC-3579) Vendor Discovery Migration

**Description:**
The current Vendor Discovery platform is built for generating reports. To improve user experience, we need to ensure that users are not required to switch between platforms. As part of this initiative, we will migrate the Vendor Discovery functionality to the EOC platform.

**Requirements:**
- Design: The design should follow the EOC interface and structure.
- HTML: Shared and ready for integration.
- Functionality: The functionality should remain identical to the current system, including responses sent to users via email.

**Impact:**
- Improved User Experience: Users will no longer need to switch between platforms, resulting in a more seamless workflow.
- Consolidated Platform: Integrating Vendor Discovery into EOC will create a single, unified platform for vendor-related operations.
- Increased Efficiency: Migrating this functionality will streamline reporting and notifications, saving users time and reducing the complexity of managing multiple platforms.
- All features and workflows, such as user interactions and notifications, should work seamlessly after migration without altering the user experience.

## Task 59: (EOC-3594) Manager View - Color Coding Gap

**Description:**

A tooltip needs to be added to represent the following color coding when a user hovers over the colors:
- Green Color: Represents a Grand Total > 11 per day, indicating High RFQ Flow.
- Yellow Color: Represents a Grand Total in the range of >8 and <=11 per day, indicating Medium RFQ Flow.
- Red Color: Represents a Grand Total <= 8 per day, indicating Low RFQ Flow.
- This tooltip will provide quick context for users when reviewing RFQ flow metrics.

## Task 60: (EOC-3602) PAAS PR Sheet Enhancement

**Description:**

- Requirement 1:
    - Allow users to upload Moglix Plant along with Customer ID, and enable users to view the Plant Name on the UI. The existing Customer Plant ID will remain - unchanged.
    - The newly added Moglix Plant ID and Plant Name should also be reflected in the downloaded file.
    - Migration: Required for past data as well.

- Requirement 2:
    - Add a Global Filter for "RFQ No." to the sheet.
- Requirement 3:
    - Add new columns before the "Remarks" column:
    - CPO No.
    - CPO Date
    - Payment Terms
    - Validation for payment terms should be added as per the system's rules.
- Requirement 4:
    - Display the Valuation in Cr. when hovering over the charts. Use Total Value (Excl. Tax) to calculate the total valuation by summing up.
    - Apply this to the following graphs:
    - PR Deadline Crossed
    - PR Stages
    - PR against Customer
- Requirement 5:
    - Remove the following columns:
    - TR Date (MM/DD/YYYY)
    - RFQ Date (MM/DD/YYYY)

**Impact:**

- Increased Efficiency: Enhances usability by allowing easy uploads of Moglix plant data, simplifying data entry and visualization.
- Improved Data Accessibility: The addition of "RFQ No." as a global filter and new columns like "CPO No." and "Payment Terms" improves searchability and detailed reporting.
- Better Insights: Displaying valuation in Cr. on charts allows for quick analysis of total value, aiding decision-making.
- Cleaner Interface: Removal of unnecessary columns reduces clutter, making the interface more user-friendly.

## Task 61: (EOC-3657) CPO Punch Header Page Optimization

**Description:**

The current header page of the CPO punch process is experiencing slow performance due to multiple API calls to the Account Service. The task is to optimize this page by reducing and merging API calls, which will lead to improved performance and faster load times.

**Action Plan:**

| Metric           | Before           | After            | Impact                                                                   |
| ---------------- | ---------------- | ---------------- | ------------------------------------------------------------------------ |
| Total Requests   | 36 / 75 requests | 28 / 64 requests | 14.67% decrease in total requests (from 75 to 64), improving load times. |
| DOMContentLoaded | 561 ms           | 270 ms           | 51.87% improvement in DOMContentLoaded time (from 561 ms to 270 ms).     |
| Finish Time      | 6.07 s           | 5.26 s           | 13.34% improvement in Finish time (from 6.07 s to 5.26 s).               |
| Redirection      | 22 requests      | 13 requests      | 40.9% reduction in the number of redirection requests.                   |

**Impact:**

- Performance Boost: Reducing the total number of requests and merging API calls results in faster page load times and better responsiveness.
- Significant Time Savings: A 51.87% improvement in DOMContentLoaded time and a 56.46% reduction in load time helps users interact with the page much faster.
- Optimized Network Usage: A 40.9% reduction in the number of network requests lowers server load, resulting in smoother and more efficient operations.
- Improved User Experience: Faster load times and reduced delays enhance the overall user experience on the CPO punch header page.

## Task 62: (EOC-3623) E-RFQ Enhancement - Vendor Suggestion for Item at RFQ and CPO Item

**Description:**

The task is to introduce vendor suggestions for items on the CPO Details Sheet and Enquiry Details Sheet. This feature will allow users to get vendor suggestions for each item in the RFQ and CPO process, making vendor selection more efficient and accurate.

**Workflow for CPO**

- Vendor Suggestion CTA:
    - When the user selects the "suggest supplier" field while creating a CPO, a CTA (Call-to-Action) will appear on the right side of the field.
    - Upon clicking the CTA, a popup or page will display suggested vendors along with the material description at the top.
- Details Visible in the Popup:
    - Supplier ID
    - Supplier Name
    - Contact Name
    - Email
    - Phone Number
    - Business City
    - Business State
    - Action (Selection Button)
- Select Supplier:
    - The user can select the supplier, and the corresponding details will be automatically filled in on the CPO Details Sheet.

**Workflow for RFQ**

- Vendor Suggestion CTA:
    - When the user selects the "Supplier Name" field during the RFQ process, a CTA will appear on the right side of the field.
- Details Visible in the Popup:
    - Supplier ID
    - Supplier Name
    - Contact Name
    - Email
    - Phone Number
    - Business City
    - Business State
    - Action (Selection Button)
- Select Supplier:
    - The user can either:
        - Select a single supplier: The details will be automatically filled in the Enquiry Details Sheet.
        - Select multiple suppliers using checkboxes: The user can click "Send for RFQ" and will be redirected to the E-RFQ screen, where the selected suppliers will already be populated. The user can then add or delete suppliers as needed.

**Impact:**

- Enhanced Efficiency: Streamlines the process of selecting vendors by providing real-time suggestions and eliminating manual searches.
- Improved Accuracy: Ensures that relevant vendors are suggested based on the item's details, reducing the chances of selecting an unsuitable vendor.
- Time Savings: Reduces the time spent manually entering vendor details for each item, improving the overall workflow for RFQ and CPO processes.
- User Experience: Offers a seamless and intuitive interface, making vendor selection simpler and more accessible for users.

## Task 63: (EOC-3622) Direct CPO - Partial Release Functionality

**Description:**

The existing Direct CPO functionality allows users to release the entire CPO in one go. However, there are scenarios where supplier discovery for some items is completed while others require more time. To address this, we need to enable partial release of CPO items, allowing users to release selected items as they become ready.

**Problem Statement:**

Currently, the entire CPO must be released in one action, which can delay the timely release of SPOs for items that are ready. This can impact supplier response time.

**Proposed Solution:**

Allow users to release CPO items partially as needed. The user will be able to select multiple items for partial release, ensuring that items ready for supplier discovery are released on time, while other items can be updated later.

**Workflow:**

- Partial Release Action:
    - Users can select multiple line items using checkboxes and click the submit button for partial release.
    - A toast message will appear showing the number of line items submitted versus the total line items in the PO.
    - Items that have already been released will be visible in frozen form (unless supplier assignment is canceled/removed in SalesOps).
- Update and Release Remaining Items:
    - Users can later "update and mark release" for the remaining items as supplier discovery is completed.
- DOA (Delegation of Authority) Handling:
    - The DOA will work as-is, similar to the RFQ process.
    - CM%* will be recalculated each time additional partial items are released. The updated CM*% will be visible to the approver on the UI.

**New PO Status:**

- Introduce a new PO type for partial release: "Partial Release."
- @Sovit Kumar and @Amit Singh, please evaluate the impact of introducing this new status.

**CM*% Status Visibility:**

The following use cases for CM*% approval status need to be considered when handling multiple items in different approval statuses:

- Three Different CM% Approval Statuses:*
    - If all three statuses (CM Approval Pending, CM Approval Rejected, and CM* Approved**) are present, display CM Approval Pending*.
- Two Different CM% Approval Statuses:*
    - If at least one item is CM Approval Rejected* and one item is CM Approved*, display CM Approval Rejected*.
    - If at least one item is CM Approval Pending* and one item is CM Approved*, display CM Approval Pending*.

**Impact:**

- Improved Efficiency: Users can release CPO items as they are ready, ensuring timely supplier response and reducing bottlenecks in the procurement process.
- Flexible Release Workflow: By allowing partial releases, this update provides flexibility in the CPO process, aligning better with supplier discovery timelines.
- Clear CM% Visibility:* Enhanced status visibility ensures that users can easily track approval progress, reducing confusion and delays.

## Task 64: (EOC-3649) Need to Add Date Range on ARC Report

**Description:**

Add a fixed date range feature to the ARC Report, based on the current logic. This will allow users to filter the report data within a specified date range for better analysis and reporting.

**Impact:**

- Improved Usability: Users can easily analyze data within specific timeframes, enhancing decision-making processes.
- Enhanced Reporting Accuracy: By allowing targeted date filtering, the report will reflect more relevant and precise data, leading to better insights.
- Increased Efficiency: Reduces the time spent on manual adjustments and searching for data across multiple reports, streamlining the overall reporting workflow.


## Task 65: (EOC-3614) Authorized Brand Distributor Visibility on EOC While Selecting Supplier

**Description:**

Currently, orders can be placed with suppliers who are not authorized distributors, which affects product quality and leads to material returns. To address this issue, when a supplier is selected on EOC, the system will provide visibility on whether the supplier is a Trader, Manufacturer, Authorized Dealer, Service Provider, or Exporter based on the brand and Supplier ID stored in Supplier Central.

    - If the selected supplier is not an Authorized Dealer or Manufacturer, a warning message will display: “Selected supplier is not an Authorized Dealer/Manufacturer.”
    - This information will be displayed alongside the default supplier information on the RFQ and CPO sheets, and will also be included in the approval screen, with unauthorized suppliers highlighted in red.
    - The system will check the brand/Brand ID from the MSN mapped to the item in combination with the Supplier ID to provide this information.
    - If the MSN is not available or mapped, the system will use the brand available along with the CPN.

**Use Cases:**

- RFQ Use Cases: Checks based on the brand and MSN availability to determine the supplier type.
- CPO Use Cases: Similar checks as RFQ use cases to ensure supplier authenticity.

**Impact:**

- Enhanced Supplier Quality: Ensures that only authorized suppliers are considered, reducing the risk of material returns and quality issues.
- Informed Decision-Making: Sourcers will have visibility into supplier authorization status, enabling better decision-making during supplier selection.
- Streamlined Approval Process: The warning message and visibility in the approval screen will help prevent unauthorized supplier orders from being approved, improving overall compliance.
- Improved User Experience: Clear visibility and warnings enhance user confidence in selecting the right suppliers, leading to a smoother procurement process.

## Task 66: (EOC-3676) Role Creation for Vendor Discovery

**Description:**

- To ensure controlled access to the Vendor Discovery feature, a new role will be created for EOC specifically for Vendor Discovery. This role will restrict usage based on access control settings.
- Create Role: Establish a role titled "EOC - Vendor Discovery" to manage access for users.
Module Separation: Implement a separate module for Single Search and Bulk Search functionalities within the Vendor Discovery feature.

**Impact:**

- Enhanced Security: By restricting access to Vendor Discovery, sensitive supplier information is safeguarded, minimizing the risk of unauthorized usage.
- Controlled User Access: Only authorized users can access Vendor Discovery functionalities, improving accountability and compliance.
- Streamlined Processes: Clear role definitions will help users navigate the application more efficiently, focusing only on relevant functionalities according to their access rights.

## Task 67: (EOC-3679) Need to Remove CDD2 Validation Check on Updating Manual ETA

**Why?**

The ETA column must be updated for each line item to ensure that the auto ETA triggers for customers.

**What?**

Remove the CDD2 validation check when updating the Manual ETA field.

**Actions:**

- Attach: Provide any relevant files or documentation.
- Create Subtask: Create a subtask for tracking this change.
- Link Issue: Link this request to the relevant issue for reference.
- Create: Initiate the change request.
- Show Git Development Panel: Ensure visibility of the Git development panel for code tracking and collaboration.

## Task 68: (EOC-3681) EOC UI Unused Code Refactoring and Restructuring

**Description:**

The EOC application has been built using the ICAT codebase since its inception, leading to the accumulation of numerous files within the same structure. To enhance maintainability and performance, a restructuring of the current architecture is necessary.

**Acceptance Criteria:**

- Remove unused code from each module and component to declutter the codebase.
- Review and organize configuration files to ensure a clean and logical structure.
- Assess the current architecture and implement modifications to improve readability and scalability.

**Impact:**

- Improved Maintainability: By removing unused code and restructuring the organization of files and folders, the codebase becomes easier to navigate and maintain, reducing technical debt.
- Enhanced Performance: A cleaner codebase can lead to better application performance by minimizing the footprint of unused components.
- Scalability: A well-organized architecture facilitates future development efforts, making it easier to add new features or modules without confusion.
- Faster Development Cycle: Developers will be able to work more efficiently in a well-structured environment, reducing onboarding time for new team members and speeding up the overall development process.

## Task 69: (EOC-3684) Access Management - Vendor Discovery

**Description:**

Users with a business designation of City Head (CH) and above should have unrestricted access to the Vendor Discovery feature, regardless of their specific role. Other users can gain access to this feature by requesting a role, which will be granted based on approval.

**Implications:**

- Streamlined Access: Ensures that senior management can utilize the Vendor Discovery feature without barriers, facilitating timely decision-making.
- Controlled Permissions: Other users will have access based on role approval, enhancing security and ensuring that only authorized personnel use the feature.
- Improved Workflow: This access management structure promotes efficient use of the Vendor Discovery tool while maintaining oversight and control.

## Task 70: (EOC-3684) Stop User from Entering String on Update "List Price"

**Description:**

In the arcListPrice field, which is currently accepted as a String from the front end, implement a numeric validation check. This will prevent users from entering non-numeric values when updating the "list price" and will automatically convert any string input into a numeric format.

**Impact:**

- Data Integrity: Ensures that only valid numeric values are entered, reducing the risk of errors in calculations and data processing.
- Improved User Experience: By enforcing numeric input, users will receive immediate feedback, preventing confusion and improving the efficiency of data entry.
- Consistency Across Tasks: Standardizing the input format will enhance the overall reliability of related tasks and functionalities that depend on accurate pricing information.
- Reduced Processing Errors: Minimizes the potential for backend processing issues that could arise from incorrect data types being used in calculations or database entries.

## Task 71: (EOC-3634) PO Punching OCR Actual Impact Report

**Description:**

This report provides insights into the effectiveness of the OCR functionality implemented for PO punching. As part of the report, the data was moved to a separate task (refer to Jira EOC-3578: PO Punching OCR).

**Daily Report Requirements:**

- PO Number-wise Breakdown:
    - Number of fields automated through OCR (header and line item separated).
    - Number of automated fields requiring manual intervention (header and line item separated).
    - If the checkbox is unselected, consider it as not automated (header and line item separated).

**Impact:**

- Increased Efficiency: Streamlined the PO punching process, reducing manual data entry time.
- Enhanced Accuracy: Improved data accuracy by minimizing human errors during data entry.
- Better Decision-Making: Provides actionable insights into the OCR's performance for further optimization.

## Task 72: (EOC-3691) Enhancement: Stop Multiple Click on Save Button

**Description:**

Currently, users can click the Save button multiple times, leading to multiple update requests on the Item Sheet and Enquiry Sheet. This enhancement aims to implement a mechanism that waits for the response of the first request before allowing the user to click the Save button again.

**Impact:**

- Reduced Errors: Prevents accidental multiple submissions, reducing the likelihood of conflicting updates and errors.
- Improved User Experience: Enhances the overall user experience by providing clear feedback on the save action and preventing frustration from unexpected behavior.
- Optimized Performance: Decreases the load on the backend by limiting the number of concurrent update requests, leading to more efficient processing.

## Task 73: (EOC-3720) Date Issue: Updating "Need to Work" for Catalog Team

**Description:**

When users are updating the "Need to Work" field for the Catalog team, a timestamp should be shared from the backend. Additionally, validation must be implemented during the saving process to ensure the accuracy and consistency of the date entered.

**Impact:**

- Data Integrity: Ensures that the date information is accurate and consistent, improving the reliability of the updates made by users.
- Improved Tracking: Allows for better tracking of changes in the "Need to Work" field, facilitating more effective project management and accountability.
- Enhanced User Experience: Provides users with clear feedback and validation, reducing the likelihood of errors during data entry.

## Task 74: (EOC-3656) Enterprise Liquidation Process: Introduction of CPO Item Type “Liquidation”

**As-Is Liquidation Process:**

- Region-wise liquidation teams created (e.g., Team North).
- Scrap dealers/buyers registered as plants with CL ≥ 1.
- Liquidation team punches RFQ for scrap buyer plant with a dummy supplier.
- RFQ approval obtained from the City Head.
- Post-approval, CPO is punched as “RFQ” CPO type without supplier mapping.
- Inventory auto-allocated for liquidation; reflected as RFQ orders in PowerBI.

**Proposed Liquidation Process:**

- Introduces a new CPO item type, “Liquidation,” for the liquidation team.
- Approval workflow remains; CPO is punched without mapping a supplier.
- Changes in selection criteria for users (only closed/unreleased PO).
- Additional fields for TP and delivery mode added during drafting.
- CPO approval status visible in listing and detail pages.
- Delivery modes specified: customer pickup or Moglix delivery.

**Points to Note:**

- CM*% approval visible with statuses (Approved, Rejected, Pending).
- Approval flow defined based on CPO value thresholds.

**Impact:**

- Streamlined Workflow: Reduces manual steps in the liquidation process, enhancing efficiency.
- Improved Tracking: Clear visibility of approval statuses and better monitoring of liquidation orders.
- Reduced Errors: Decreases the chance of non-compliance by ensuring proper handling of liquidation orders.
- Increased Transparency: Facilitates better communication and documentation in the approval process.

## Task 75: (EOC-3705) Brand Authorization Tagging on Pending CPO CM* Approval Screen

**Description:**

Brand Authorization Tagging needs to be added to the Pending CPO CM* Approval Screen. Additionally, this tagging should be included in the email requests raised for approvals.

**Impact:**

- Improved Compliance: Ensures that only authorized brands are approved, reducing the chances of unauthorized suppliers.
- Better Visibility: Provides clear brand authorization information to approvers, leading to informed decision-making.
- Streamlined Process: Incorporates tagging into email communications, enhancing the approval workflow and reducing errors.

## Task 76: (EOC-3753) Adoption of Vendor Discovery at Line Item (CPO and RFQ Page)

**Description:**

- Implement search functionality on RFQ and CPO pages.
- Track user interactions (GA) for Search CTA with user ID, date, and click details.
- Implement GA on Send for RFQ CTA.
- Data tagging for ERFQ, distinguishing between item-level CTA and bulk CTA actions (development required).

**Impact:**

- Improved Tracking: GA event tracking enables better insight into user interactions for both CPO and RFQ pages.
- Enhanced Efficiency: Item and bulk-level tagging allows for better data segmentation and analysis, optimizing the vendor discovery process.
- Actionable Insights: Provides granular data to improve user experience and vendor interaction workflows.

## Task 77: (EOC-3752) Adoption Vendor Discovery

**Description:**

- Track the count of users having access to Single Search and Bulk Search features.
- Single Search: Apply GA on Search CTA to track date-wise unique clicks along with user email IDs.
- Bulk Search: Track file uploads along with User ID and date.

**Impact:**

- Enhanced Monitoring: Provides visibility into how many users are utilizing single and bulk search functionalities.
- Detailed Insights: GA tracking for both single and bulk searches helps identify usage patterns, improving decision-making for feature optimization.
- User Behavior Analysis: Allows better understanding of search behavior, facilitating potential enhancements for the vendor discovery process.
































































































# DIGIMRO
# Credlix (Nuphi and Exim)
# MaaS