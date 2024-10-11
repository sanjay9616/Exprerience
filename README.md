# Moglix Experience

Contributed to multiple high-impact projects, showcasing expertise and utilized a broad range of technologies, including Angular, Angular Material, RxJS, NgRx, ReactJS, NextJS, Material-UI, and Tailwind CSS for web development. Additionally, I worked with JavaScript, TypeScript, Python, HTML, CSS, MySQL, and DBMS for languages and databases. My expertise extends to data structures and algorithms, with familiarity in ExpressJS and MongoDB, while effectively maintaining version control with Git. I contributed to multiple high-impact projects, showcasing my proficiency in Angular, RxJS, and TypeScript.

- [EOC (Excel on Cloud)](#eoc-excel-on-cloud): is an internal application developed at Moglix to streamline the management of Purchase and Sale orders. The application features a custom Excel-like interface that allows users to efficiently track items throughout the entire lifecycle of orders and products. Specifically designed for the internal buyer team, EOC simplifies the creation of Purchase Orders, enhancing the overall efficiency of the purchasing process.
- [Credlix (Nuphi and Exim)](#credlix-nuphi-and-exim): Credlix, a digital supply chain finance platform from Moglix, provides quick, collateral-free working capital solutions for enterprises, suppliers, and exporters in India and Southeast Asia, leveraging Moglix's expertise in end-to-end supply chain transformation for over 700 enterprises and 16,000 SMEs exporting to 53 countries, and offers services such as early payment, vendor finance, channel finance, invoice discounting, and purchase order finance to ensure continuous movement in domestic supply chains and export financing.
- [DIGIMRO](#DIGIMRO): DigiMRO is India's leading distributor of multi-category and multi-brand low-voltage electronic security products, offering a vast range of global brands and unparalleled industry expertise in B2B distribution of CCTV, access control, fire, power, audio/video, and network systems, while serving as an indispensable partner for suppliers and customers through its extensive reach, expertise, and logistics capabilities that enhance competitiveness and maintain critical supply chains.
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



# Credlix (Nuphi and Exim)

## Implementation of Login and Signup Flow for Domestic and Exporter

**Description:**

I developed the login and signup flow for both domestic users and exporters in the Credlix platform using Angular Material design. The implementation focused on a seamless user experience, ensuring that the UI was intuitive and responsive. This involved designing and integrating form components with validation, authentication services, and conditional routing based on user roles.

**Impact:**

- Improved User Experience: The use of Angular Material provided a modern and accessible UI, enhancing the overall look and feel of the platform.
- Streamlined Onboarding: A clear and efficient signup process reduced the time users spent registering, contributing to higher conversion rates for new users.
- Role-Based Functionality: The separation of flows for domestic and exporter users allowed for a more tailored experience, catering to the specific needs of each user type.

## Implementation of Proforma Invoice Calculation

**Description:**

I developed the proforma invoice calculation functionality, automating the generation of invoices based on user inputs, including product details, pricing, taxes, and discounts. This implementation ensures accuracy in invoice generation and reduces manual intervention, enabling a smoother process for users to preview and manage their proforma invoices.

**Impact:**

Increased Efficiency: Automated calculations minimized manual errors, speeding up the invoice generation process.
Improved Accuracy: The system ensured precise calculations, leading to better compliance and customer trust.
Enhanced User Satisfaction: Users experienced a more streamlined approach to creating and managing invoices, improving overall satisfaction with the platform.

## Angular Version 7 to 12 with Strict Mode Enabled

**Description:**

The upgrade from Angular 7 to Angular 12 involved a series of systematic steps to modernize the application and incorporate the latest Angular features and best practices. This process ensured that the application remained up-to-date, maintainable, and efficient. The decision to enable strict mode further reinforced type safety and code robustness, aligning with Angular's recommendations for optimal development practices.

**Key Steps Involved:**

- Version Migration:
    - Upgrade Angular CLI: Updated Angular CLI from version 7 to version 12 by using incremental updates (version-by-version) to avoid breaking changes. This ensured a smooth transition and compatibility across versions.
    - Refactor for Deprecated Features: Addressed deprecated APIs and features as per Angular's migration guidelines. This included updating libraries, RxJS imports, and HTTP client syntax changes, ensuring all modules were compliant with Angular 12 standards.
    - Third-Party Library Updates: Updated third-party dependencies and Angular Material to the latest versions to ensure compatibility with Angular 12.
- Enabled Strict Mode:
    - Enabling strict mode involved setting the strict flag to true in the tsconfig.json file. This introduced stricter type checks, including:
        - Strict Type Checking: More precise inference of types, helping to catch potential runtime errors at compile time.
        - Null Safety: Detection of null and undefined values at an early stage, preventing null reference errors in production.
        - No Implicit Any: Enforcing explicit typing for all variables and functions, ensuring the code is strongly typed.
        - Strict Template Checking: Strengthened template binding checks to align with the component’s types, ensuring that templates are correctly bound to component logic.
- Tree-Shakable Modules: Angular 12 improved tree-shaking capabilities, which meant unused code was automatically removed from the production build, reducing the bundle size.
- Optimized Build Process:
    - Faster Builds: Angular 12 introduced faster compilation with Ivy, which significantly improved development build times and reduced bundle sizes.
    - Improved Localization: The i18n (internationalization) capabilities were enhanced, making the app more adaptable to multiple languages, which was useful for scaling to international markets.
- TypeScript Upgrade: Upgraded the TypeScript version to 4.8.4, which unlocked new language features, better type inference, and faster builds.

**Impact:**

- Performance Boost: The Ivy engine in Angular 12 improved compilation times and memory consumption, making the app faster to develop, build, and run.
- Code Consistency and Safety: Strict mode introduced stronger type-checking throughout the application, which reduced bugs, increased maintainability, and made refactoring easier.
- Enhanced Developer Experience: By catching more errors during compile time and optimizing the build processes, the development cycle became smoother and more reliable.
- Smaller Bundle Size: Tree-shaking and optimizations in Angular 12 reduced the overall bundle size, enhancing the application's load times and improving the user experience.
- Scalability: The update future-proofed the codebase, making it easier to adopt future Angular updates and scale the application with new features and optimizations.


# DIGIMRO

## Angular Version 7 to 12 with Strict Mode Enabled

**Description:**

Post-login, customers are segmented into two groups: ADI and BRISK. Based on the customer type, different brands, products, and categories are displayed. For ADI customers, a specific list of brands is shown, while BRISK customers see a different set of brands. This brand mapping extends to the top brands banner, ensuring a tailored experience for both customer types.

**ADI Customer Brands:**

- Algatec
- Audiotrak
- Bosch
- Electro-Voice
- Honeywell
- Morley
- Protek
- Ravel
- Rosslare
- Texecom
- Timewatch
- Veracity
- Vesda
- Wbox
- Optex
- Securico
- Smart I
- System Sensor
- Assa Abloy
- Eaton
- Fargo
- GST
- Hanwha Techwin
- NUUO
- Western Digital
- Agni
- Apollo
- Cybernetics
- Alba Urmet
- Hid
- Idcube
- Idemia
- Matrix
- Time Watch
- Yale
- ALGATEC
- IDEMIA
- CYBERNATICS
- FARGO
- HID
- HONEYWELL
- IDCUBE
- ROSSLARE
- SMART I
- TIME WATCH
- AUDIOTRAK
- BOSCH
- BOSCH EV
- HIKVISION
- PROTEK
- WBOX
- WESTERN DIGITAL
- AGNI
- APOLLO
- ASES
- EATON
- MORLEY
- RAVEL
- SYSTEM SENSOR
- VESDA
- REALITY
- IOTA
- OPTEX
- SECURICO
- TEXECOM
- EONSECURE
- EONAV

**Impact:**

- Personalized User Experience: Displaying brands based on the customer type ensures that ADI and BRISK customers only see relevant products, increasing the likelihood of engagement and conversions.
- Enhanced Customer Satisfaction: By showing tailored brands and products post-login, customers feel a more customized shopping experience, leading to higher satisfaction and retention.
- Improved Efficiency: Streamlining the product catalog based on customer type reduces irrelevant content, helping users quickly find the products they are most interested in.
- Consistent Branding: The same approach applied to the top brands banner ensures consistency in brand visibility, creating a cohesive experience across the platform.

## Update to DigiMRO Contact Us Page for ADI and BRISK Customer Support

**Workflow Overview:**

- Brand Selection:
    - Customers can search from a static list of brands (as defined in the brand BU.csv file).
    - Based on the selected brand, either ADI or BRISK contact details will be displayed.
- Support Details:
    - If an ADI brand is selected, show the existing ADI contact details (Flow 1).
    - If a BRISK brand is selected, show the following BRISK contact details.
    - BRISK Customer Support Details
- Centralized Contact Information:
    - Phone No: +91 20 25464825
    - Calling Time: (Same text as for ADI)
    - Email: salespune@briskelectronics.com
    - Subtext: (Same as ADI)

**Brisk Office Locations & Contact Info:**

- Pune
    - Company Name: Brisk Electronics Pvt. Ltd.
    - Location: Brisk Electronics Private Limited · 414, 4th Floor, Building No 1, Siddharth Tower, Kothrud, Pune, Maharashtra 411038, India
    - Address: 319/320, Siddharth Tower, Bldg. No.1, G A Kulkarni Path, Kothrud, Pune – 411038. INDIA.
    - Contact Number: +91 20 66203233
    - Email: salespune@briskelectronics.com
- Ahmedabad
    - Company Name: Brisk Electronics Pvt. Ltd.
    - Location: Brisk Electronics Pvt. Ltd. · Plot no 512 1 near Ramol police chowki, Phase IV, Vatva GIDC, Ahmedabad, Gujarat 382445, India
    - Address: 304, Gala Argos, Kalgi Cross Road, Ellisbridge, Ahmedabad – 380006. INDIA.
    - Contact Number: +91 79 35114713, 48902419
    - Email: brisk.amdavad@gmail.com
- Nagpur
    - Company Name: Brisk Electronics Pvt. Ltd.
    - Location: Brisk Electronics Pvt. Ltd. · Block No.S-4, Plot No. D-1, Midc, Hingna, Nagpur, Nildoh ct, Maharashtra 440016, India
    - Address: Plot No.98, MIDC Hingna, Near Wadi Hingna T Point, Opp. Modigold, Nagpur – 440028. INDIA.
    - Contact Number: +91 8380074026
    - Email: salesnagpur@briskelectronics.com
- Mumbai
    - Company Name: Brisk Electronics Pvt. Ltd.
    - Location: Brisk Electronics · BRISK ELECTRONICS, Tiwari Compound, 29 8, SV Rd, Krishna Colony, Dahisar East, Mumbai, Maharashtra 400068, India
    - Address: Plot No.391, 409 Diamond Plaza, Dr. Dadasaheb Bhadakamkar Marg, Girgaon, Mumbai – 400004. INDIA.
    - Contact Number: +91 22 62375837
    - Email: salesmumbai@briskelectronics.com
- Kolhapur
    - Company Name: Brisk Electronics Pvt. Ltd.
    - Location: Brisk Electronics Pvt. Ltd. · Plot No.9, Isolation Hospital Rd, Nehru Nagar, Samrat Colony, Datta Colony, Kolhapur, Maharashtra 416012, India
    - Address: D-23, Kolhapur Udyam Co-opretive Society Ltd, 1328/34, Y.P.Powar Nagar, Kolhapur – 416006. INDIA.
    - Contact Number: +91 231 2692450
    - Email: saleskolhapur@briskelectronics.com

**Implementation Steps:**

- Update Contact Us Page Layout:
    - Add a search input for customers to select their brand from the static list provided.
- Brand-based Conditional Rendering:
    - Use brand selection to conditionally display either the ADI contact flow or the BRISK contact details listed above.
- Consistency in Design:
    - Ensure both ADI and BRISK support details maintain a consistent format and style for better user experience.

**Impact**

- Enhanced User Experience:
    - By allowing customers to select brands and display relevant contact information, the update provides a tailored experience. This makes it easier for customers to find the support they need, reducing frustration and increasing satisfaction.
- Increased Engagement:
    - With a clear and accessible way to contact support, customers are more likely to reach out when they have questions or issues. This proactive communication can lead to higher engagement rates with the support team.
- Improved Customer Satisfaction:
    - Providing specific contact details based on customer type (ADI vs. BRISK) ensures that customers receive the most relevant information. This personalized approach can enhance overall customer satisfaction and loyalty.
- Streamlined Support Processes:
    - Centralizing contact information based on brand selection helps streamline support processes. Support teams can better prepare for inquiries by anticipating the types of issues or questions that may arise based on the brand selected.
- Brand-Specific Knowledge:
    - The update allows support staff to focus on brand-specific knowledge and expertise, improving the quality of assistance provided to customers. This can lead to faster resolution times and better overall support experiences.
- Operational Efficiency:
    - By categorizing support requests by brand, the support team can more effectively allocate resources and manage workloads, leading to improved efficiency and response times.
- Reduced Response Time:
    - With clear contact details and streamlined communication channels, customers can expect faster responses to their inquiries, which can lead to increased trust and confidence in the brand.
- Better Data Collection:
    - The implementation of a brand selection feature allows for better data collection on customer inquiries, enabling the company to identify trends and areas for improvement in products and services.
- Increased Conversion Rates:
    - A well-structured contact page can help drive conversions by instilling confidence in potential customers who may be seeking support before making a purchase decision. Knowing they can easily access assistance may encourage them to proceed with their purchases


# MaaS

## Task 1: (MAAS-1012) Implement Project Exposure Calculation and Display

**Description:**

Develop and integrate the logic for calculating and displaying Project Exposure, Customer Exposure, and Supplier Exposure in the Project Financials section of the MaaS project. The exposure metrics are crucial for tracking the financial health of the project, particularly highlighting the gaps between customer receivables and supplier payables.

The logic to be implemented for each exposure type is as follows:

**Project Exposure:** `Project Exposure = Customer Exposure − Supplier Exposure`

**Supplier Exposure:** `Supplier Exposure = Amount Payable − Supplier Payment Done − Supplier RM Supplied`

**Customer Exposure:** `Customer Exposure = Customer Payment Received − Amount Receivables`

The calculated values should be displayed in the Project Financials section with a user-friendly interface, aligning with the UX design provided in Flow 1.

**Impact:**

- Improved Financial Transparency: Providing real-time visibility into project financials allows stakeholders to monitor customer payments and supplier liabilities, leading to better decision-making and project financial management.
- Risk Mitigation: By showing the differences between Customer Exposure and Supplier Exposure, potential financial risks can be flagged early, helping mitigate cash flow issues.
- Streamlined Financial Management: Clear visibility of Project Exposure aids project managers in evaluating financial gaps, ensuring that any shortfalls or surpluses are addressed promptly.
- Enhanced Reporting: This feature simplifies financial reporting for stakeholders, enabling them to assess the overall financial status of a project at any given point.

## Task 2: (MAAS-1018) Implementation of BOM for Drafted

**Task Description:**

Implement the Bill of Materials (BOM) Changes for the drafted stage of the project and ensure that the necessary features and UI elements are added for seamless user interaction. The key requirements are as follows:

- Attach Link to Issue:
    - Implement functionality to attach the link for the current issue and display it under the Git Development Panel for easy access and tracking.
- Create New Stages via Autocomplete:
    - Add an autocomplete feature for mapping stages. When users query for a stage that does not match existing entries, provide an option to "Create New Stage". This should be facilitated using a "Create Stage" button, enabling users to create stages quickly and efficiently.
- Add Icon for Procurement Types in Stages List:
    - Display an icon next to procurement types in the Stages List section. For now, use the following icon: `<i class="ri-pages-line"></i>`
    - Ensure that the icon is placed in the correct location in the UI and adheres to the design guidelines.

**Task Impact:**

- Streamlined Workflow: By enabling the creation of new stages directly from the autocomplete feature, the task creation process becomes faster and more efficient, improving the user experience.
- Better Issue Tracking: Attaching the issue link in the Git Development Panel allows for easier navigation and tracking of development tasks, making - collaboration more effective for the development team.
- Enhanced Usability: Adding icons for procurement types in the Stages List improves the visual clarity and usability of the interface, helping users to quickly identify procurement-related stages.

## Task 2: (MAAS-1024) FE Implementation of Customer Payment Term

**Task Description:**

- Term Sheet Click Event:
  - When the user clicks on the "Term Sheet" button, call the following API to fetch distinct stages:
  - API: http://localhost:7073/stage/fetch-distinct-stages?projectId=468
  - Method: GET
        ```json
        [
            { "idStage": 605, "stageName": "RM Inspection" },
            { "idStage": 599, "stageName": "Black inspection" },
            { "idStage": 620, "stageName": "Final Inspection" },
            { "idStage": 601, "stageName": "Loading" }
        ]
        ```
  - Populate the Stage Select Menu with the response data for both Customer and Supplier payment stage menus.
- Fetching Customer Payment Terms:
    - After fetching the stages, call the following API to retrieve customer payment terms:
    - API: http://localhost:7073/customer-payment-term/fetch?projectId=463
    - Method: GET
    - Response
        ```json
        {
            "customerName": "Thermax Babcock & Wilcox Energy Solutions Pvt. Ltd - Pune",
            "poValue": 575454.14,
            "totalOS": 575454.14,
            "totalOD": 575454.14,
            "customerPaymentTerms": [
                {
                "projectId": 463,
                "id": 59,
                "paymentTermType": "AFTER_DISPATCH",
                "paymentPercentage": 100.0,
                "days": 45,
                "stage": null,
                "outstanding": 575454.14,
                "overdue": 575454.14,
                "cashIn": {
                    "id": 179,
                    "transactionDate": 1671215400000,
                    "cashIn": 100.0
                    }
                }
            ]
        }
        ```
- UI Changes:
    - Total Invoice Amount: Change the label to Total Po Value for both customer and supplier.
    - Total OS: Sum of all customerPaymentTerms[n].outstanding.
    - Total OD: Sum of all customerPaymentTerms[n].overdue.
    - Completion Weightage: Sum of all customerPaymentTerms[n].paymentPercentage. Show as a percentage (e.g., 10% instead of 10/100%).
- List Accordion:
    - Display payment terms in an accordion style, where each term has the following properties:
        - paymentTermType
        - paymentPercentage
        - days
        - outstanding (as OS)
        - overdue (as OD)
    - Each payment term will have Edit and Delete options.
- Edit Mode:
    - On clicking Edit, the UI changes to show Save and Delete buttons, and all fields become editable.
    - When the user clicks Save, call the following API:
        - API: http://localhost:7073/customer-payment-term/save?projectId=468
        - Method: POST
        - Request Body
        ```json
            {
                "id": 89,
                "paymentTermType": "AFTER_DISPATCH",
                "paymentPercentage": 20,
                "days": 5,
                "idStage": null
            }
        ```
        - Send idStage only if a stage is selected from the dropdown menu.
        - If id is null, a new term will be created. If id has a value, the existing term will be updated.
- Delete Functionality:
    - On clicking Delete, call the following API:
        - API: http://localhost:7073/customer-payment-term/delete?termId=90
        - Method: DELETE
        - On success, recalculate Total OS and Total OD.
- Recalculate Values:
    - After saving or deleting a payment term, recalculate:
        - Total OS: Sum of all customerPaymentTerms[n].outstanding.
        - Total OD: Sum of all customerPaymentTerms[n].overdue.

**Task Impact:**

- Enhanced User Experience: This task provides a more intuitive interface for managing customer and supplier payment terms. Users can easily edit and delete terms, improving workflow efficiency.
- Real-Time Data Handling: With immediate recalculations of Total OS and Total OD, users are presented with accurate financial data instantly.
- Streamlined Payment Management: Automating the population of stages and terms ensures consistency and accuracy across the project payment terms.

## Task 3: (MAAS-1028) Update in UI for Addition of Non-Mandatory Fields

**Task Description:**

- New Fields to be Added:
    - Rejection Quantity:
        - Default value: 0 for any new stage lot.
        - Placement: As shown in the attached picture.
    - Tolerance Quantity (tolerenceQty):
        - Default value: 0 for any new stage lot.
        - Placement: As shown in the attached picture.
- UI Calculations:
    - Completion Percentage: (completedQty + rejectionQty) / (tolerenceQty + plannedQty) * 100
    - Remaining Quantity: (tolerenceQty + plannedQty) - (completedQty + rejectionQty)
- Field Constraints:
    - Negative Values: Fields cannot have negative values.
    - Maximum Value: Fields cannot exceed the value of the Planned Quantity.
- API Reference:
    - Please refer to the API documentation: Postman API Documentation for the necessary endpoints and methods.

**Task Impact:**

- Data Integrity: By enforcing constraints on negative values and ensuring quantities don't exceed the planned quantity, this task ensures data accuracy.
- UI Enhancement: Introducing the new fields and calculations provides better tracking and visibility of project quantities, leading to more informed decision-making.
- Project Tracking: The calculated completion percentage and remaining quantities will give users a clearer understanding of the project’s status.

## Task 4: (MAAS-1030) Implementations BOM - For Other Statuses (Other than Drafted)

**Task Description:**

- API Reference:
    - URL: https://maas-dev.moglilabs.com/project/lot/stage-tracker?type=view&headerId=449&lotId=3609&lot=0
    - API to fetch data:
    - Endpoint: stage/stageLot/fetchHeader/projectId/468/lotId/3591
    - Response: trackerResponses → stageLotResponses
- Conditions for View:
    - If stageLotResponses[0].stageType === 'REGULAR', show the default view.
    - If stageLotResponses[0].stageType === 'PROCUREMENT', show the Procurement view.
- Procurement View Example:
    - API response snippet for Procurement Materials:
    ```json
        "procurementMaterials": [
            {
                "idMaterial": 1,
                "nameMaterial": "Material 1",
                "unitMaterial": "unit",
                "qtyMaterial": 2
            },
            {
                "idMaterial": 2,
                "nameMaterial": "Material 2",
                "unitMaterial": "unit",
                "qtyMaterial": 3
            }
        ]
    ```
- Views to Implement:
    - Material Details: (Change label to Material Required)
        - Fields:
            - Name: nameMaterial
            - Unit: unitMaterial
            - Required Quantity: qtyMaterial * plannedQuantity
            - Received Quantity: User-defined field: procurementMaterials[0].receivedQty
    - Material Required: (Change label to Material Details)
        - Fields:
            - Name: nameMaterial
            - Unit: unitMaterial
            - Quantity: qtyMaterial
- Value Change Events:
    - On Total Required Quantity (Planned Quantity):
        - When plannedQuantity is updated, update the Required Quantity for all materials:
            - Formula: procurementMaterials[0].requiredQty = qtyMaterial * plannedQuantity
    - On Ready for Manufacturing (Completed Quantity):
    - Calculate Ready Quantity for all materials:
    - Formula: readyQty = receivedQty / qtyMaterial
    - The minimum value of all readyQty should be used as the Ready for Manufacturing value.

**Task Impact:**

- Improved BOM Tracking: Implementing this will allow better tracking of required and received materials during procurement.
- Accurate Calculation: Real-time updates for required and ready quantities will ensure the project's manufacturing stage is based on accurate material availability.
- User Experience: The two distinct views (Regular and Procurement) will provide tailored information, enhancing user interaction and understanding of material requirements.

## Task 5: (MAAS-1044) FE - Feature Flow for BOM (DRAFTED)

**Task Description:**

- This feature is aimed at enhancing the Bill of Materials (BOM) feature when the status is Drafted.

**API Reference:**

- Endpoint: https://maas-core-dev.moglilabs.com/stage/fetch-stage-lot?projectId=508
- Sample Response:
```json
{
    "fkIdStage": 526,
    "fkIdLot": 4423,
    "idStageLot": 6658,
    "stageType": "PROCUREMENT",
    "stageLotSequence": 6658,
    "plannedStartDate": 1664476200000,
    "plannedEndDate": 1667154600000,
    "plannedQuantity": 20,
    "uom": "packet",
    "weightage": 45,
    "procurementMaterials": [
        {
            "idMaterial": 1,
            "nameMaterial": "Material 1",
            "unitMaterial": "unit",
            "qtyMaterial": 2
        },
        {
            "idMaterial": 2,
            "nameMaterial": "Material 2",
            "unitMaterial": "unit",
            "qtyMaterial": 3
        }
    ]
}
```

**Feature Flow Details:**

- When User Clicks on Edit Icon:
    - A popup will open for the user to edit the stage lot details.
    - Popup Select Option:
    - Use the stageType from the API response to map the select options inside the popup.
    - Based on the stageType:
        - If "Regular" is selected:
        - Remove the Materials Required section from the popup.
        - If "Procurement" is selected:
        - Show the Materials Required section.
        - Note: If the stageType is set to Regular, the user can change it to Procurement but cannot change it back to Regular once the selection is made.
- Material Details (When Procurement is Selected):
    - Show the material details section when Procurement is selected, using the response fields:
        - Name: nameMaterial
        - Unit: unitMaterial
        - Quantity: qtyMaterial
- Updating the Stage Lot:
    - Once the user makes the necessary changes, use the save API to update the stage lot.
    - API Endpoint: http://localhost:7073/stage/stageLot/save
    - Send the response similar to the one above, with any updated values:
```json
{
    "fkIdStage": 526,
    "fkIdLot": 4423,
    "idStageLot": 6658,
    "stageType": "PROCUREMENT",
    "stageLotSequence": 6658,
    "plannedStartDate": 1664476200000,
    "plannedEndDate": 1667154600000,
    "plannedQuantity": 20,
    "uom": "packet",
    "weightage": 45,
    "procurementMaterials": [
        {
            "idMaterial": 1,
            "nameMaterial": "Material 1",
            "unitMaterial": "unit",
            "qtyMaterial": 2
        },
        {
            "idMaterial": 2,
            "nameMaterial": "Material 2",
            "unitMaterial": "unit",
            "qtyMaterial": 3
        }
    ]
}
```
**Expected Results:**

- Dynamic Material Section: Show or hide the materials section based on the stage type.
- Save Flow: When saving the stage lot, the changes will reflect properly based on user inputs, ensuring correct procurement materials and data updates.

## Task 6: (MAAS-1054) Implementing Project Report Popup with Finance XLS Data

**Description:**

This task involves implementing functionality that allows users to view a financial report in a new tab when they click on the Finance XLS icon located on the Project List page. The report will be fetched from an API endpoint (GET: http://localhost:7073/report/fetch-finance-xls-report) and rendered as HTML content in a new browser tab. This feature aims to enhance user experience by providing quick access to detailed financial information related to projects.

**Impact:**

- Improved User Experience:
    - Users will have quick access to financial reports directly from the project list page without navigating away.
    - It reduces the number of clicks required to retrieve and view finance-related data.
- Increased Efficiency:
    - The direct display of the financial report in a new tab ensures that users do not have to manually download or process XLS files for quick views.
    - This leads to faster decision-making and streamlined report access.
- Enhanced Interface:
    - Integrating this functionality with the Git development panel ensures that the report linking and attachment process is cohesive within the overall project management workflow.
    - The Show Git Development Panel feature ensures that all related development issues, commits, and branches are linked directly to the finance report, increasing transparency and traceability during development.

## Task 7: (MAAS-1057) Frontend Implementation for Refreshing Portal after Release

**Description:**

- This task involves handling API responses with a 426 error code (Upgrade Required). When an API returns this status code, the following actions must be implemented:
- Display Message:
        - Show a message to the user retrieved from the API response (this would typically explain that an update is required).
- Refresh the Application:
    - After displaying the message, the portal should be refreshed by navigating to the same route, ensuring that the app reloads without the user losing their current position.
    - This ensures that users receive important update messages and the application automatically refreshes for them to continue using the latest version.

**Impact:**

- Improved User Experience:
    - Users will be informed when an app update is required and be guided smoothly through the process of refreshing the portal.
    - The refresh action will help avoid potential confusion or disruption during release upgrades.
- Seamless Transition Post-Update:
    - Automatically refreshing the app after showing the message ensures that the user gets the updated version without needing to manually navigate or refresh the page, reducing friction during rollouts.
- Enhanced Error Handling:
    - Handling 426 Upgrade Required error codes will ensure that the app gracefully informs users about required updates instead of failing silently.

## Task 8: (MAAS-1072) Frontend Feature Flow (Procurement) for BOM - Drafted Stage Lot

**Description:**

This task involves implementing the Procurement feature flow for Bill of Materials (BOM) in the Drafted stage of the project. It includes saving, updating, and populating the procurement materials for a stage lot. The UI will allow users to add, edit, and save materials for procurement with appropriate validation.

**UI Interaction Flow:**

- Edit Stage Lot:
    - Click on the Edit Stage Lot button to open the details for the stage lot.
- Adding New Row:
    - Click the Add New Row button to add a new material.
    - Each new row should have:
        - Name Field: Input text field (Always).
        - Unit Field: Input text field (Always).
        - Quantity Field: Input number field (Only positive numbers, non-zero, and up to 4 decimal places).
    - Validation:
        - The Add New Row button should be disabled if any of the three fields (Name, Unit, Quantity) are empty or have invalid values (e.g., empty string, space).
- Populating Data:
    - When the user closes the popup or saves the changes, the Procurement Materials section will be populated with data from the API response.
    - API for fetching stage lot details:
        - Endpoint: GET http://localhost:7073/stage/fetch-stage-lot?projectId=449
        - Use the parent API to update the response and populate rows of procurement materials (only for the Procurement stage, not regular stages).
- Header of Stage Lot Popup:
    - Change the header to:
        - Lot No. 3609 will be replaced with Fittings and Flanges (use sequenceLotName, not idLot).
    - Remove the subscript portion (as seen in the provided image).

## Task 9: (MAAS-1077) Revamp of Stage Creation (Drafted)

**Description:**

This task involves revamping the stage creation process for drafted stages by moving the functionality from a popup interface to a more streamlined view. The goal is to enhance the user experience by making stage creation easier and more accessible.

**Key Changes:**

- Move Functionality:
    - The existing stage creation functionality, currently presented in a popup (as shown in the provided image), will be moved to a dedicated section or page.
- UI Update:
    - Change the button label to:
    - "Create New Stage" (Ensure the 'C' in "Create" is capitalized, as well as the rest of the text).

**Steps for Implementation:**

- Relocate Stage Creation UI:
    - Identify the existing popup functionality and transition it into a full-page view or dedicated section.
    - Ensure all the fields and interactions from the popup are preserved in the new layout.
- Update the Button Label:
    - Update the label on the Create New Stage button to ensure it follows proper capitalization: "Create New Stage".


**Impact:**

- Improved User Flow:
    - Moving the stage creation out of a popup will reduce interruptions, providing a more fluid and accessible experience.
    - Users will have a larger workspace to input data and create new stages without dealing with the constraints of a small modal window.
- Clarity and Efficiency:
    - The updated interface will improve clarity, allowing users to focus on the task of creating a stage without distraction.
    - Ensuring consistent capitalization in UI elements (like Create New Stage) maintains a professional and polished look, contributing to overall design consistency.

## Task 10: (MAAS-1089) Fixes on StageLot Popup View (Drafted)

**Description:**

This task involves implementing several fixes and enhancements to the StageLot Popup View for drafted stages. The goal is to improve user experience by ensuring data integrity and proper visibility of required fields.

**Key Fixes and Enhancements:**

- Visibility of Add New Row Button:
    - The "Add New Row" button should always be visible and should never be hidden, ensuring users can add materials as needed without restrictions.
- Final Validation on Continue:
    - When the user clicks on Continue, perform a final check for any empty fields:
    - If any field is empty, highlight it in red and display a message, e.g., "Field name is required."
    - This will help prevent incomplete submissions and guide users to fill in all necessary information.
- Handling Quantity in Rows:
    - Upon adding a second row, ensure that the quantity field does not get removed from the first row. This ensures all input fields remain intact when users add new materials.
- Retaining Data on Popup Reopen:
    - When the user clicks on Continue, the popup should close, and upon reopening the Edit Stage Lot, the previously saved material responses should be displayed.
    - Use the response from the Save Stage Lot API call to replace the parent StageLot by its ID, ensuring that previously saved data is retained without making additional API calls.
- Delete Icon Functionality:
    - Implement the functionality for the delete icon next to each material row:
    - Clicking the delete icon should remove the corresponding created or existing row, allowing users to manage their material list effectively.

**Impact:**

- Enhanced User Experience:
    - Ensuring that the Add New Row button is always visible and validating fields will improve usability and prevent frustration when users forget to fill in required fields.
- Data Integrity:
    - Retaining previously saved data when reopening the popup ensures a smoother workflow and reduces the need for repetitive data entry, enhancing overall productivity.
- Efficient Material Management:
    - The delete functionality for material rows will allow users to manage their lists dynamically, ensuring they can remove entries as necessary without confusion.

## Task 11: (MAAS-1096) Fixes on Stage Page (Drafted)

Description:

This task involves implementing several fixes and enhancements to the Stage Page for drafted stages. The objective is to improve usability and ensure data integrity while providing a more intuitive interface.

**Key Fixes and Enhancements:**

- Maximum Limit for Stage Name:
    - Implement a character limit of 16 characters for the Stage Name input field to ensure consistency and avoid overly long names.
- Properly Disable "Create New Stage" Button:
    - Ensure the "Create New Stage" button is disabled correctly when conditions are not met, similar to how the "Report" button is disabled on the project list page.
- Update Button Label:
    - Change the label of the + Create New Stage button to + CREATE NEW STAGE to provide clearer visibility and emphasis.
- Cursor Change on Hover:
    - Implement the following cursor changes for the Stage Name div:
    - On hover: Change cursor to grab.
    - When draggable is active: Change cursor to grabbing.
- Text Placement Formatting:
    - Update the text placement for the display of dates, quantity, weightage, and sequence as follows:
- Change from:
    - Start Date : 12-Oct-2022, End Date 12-Oct-2022, Planned Quantity 2.9, Weightage 33.33%, Sequence 10191
    - To:
    - Start Date : 12-Oct-2022, End Date : 12-Oct-2022, Planned Quantity : 2.9, Weightage : 33.33%.
- Weightage Validation:
    - Implement a condition to ensure that the sum of all weightages for the stages is 100%. This condition should be checked when the user clicks the NEXT button, preventing progression if the total does not meet the requirement.

**Impact:**

- Enhanced User Experience:
    - Setting a maximum limit for the Stage Name ensures user inputs are manageable and prevents UI overflow.
    - Disabling the Create New Stage button under appropriate conditions provides a clear indication of when actions can be taken, enhancing usability.
- Improved Clarity and Formatting:
    - Changing the button label and updating text placements will create a more user-friendly interface that is easier to read and understand.
    - The cursor changes provide intuitive feedback for user interactions, enhancing overall engagement.
- Data Integrity and Validation:
    - Implementing weightage validation ensures data consistency and prevents errors related to stage weight distribution, promoting accuracy in project management.

## Task 12: (MAAS-1109) Project Navigation: Include Stages in Top Navigation Menu & Adding a Previous Button

**Description:**

This task aims to enhance project navigation by incorporating Stages in the top navigation menu and adding a Previous button to facilitate backward navigation. These changes will improve user experience and allow for smoother transitions between project components.

**Key Changes:**

- Add Stages to Navigation Menu:
    - Integrate Stages into the existing top navigation menu, enabling users to easily access the stages from any project page.
    - Ensure that the Stages menu item is visible and accessible for all users.
- Implement Navigation from Lot Page:
    - Enable navigation from the Lot Page to the Stages Page using a NEXT button.
    - Ensure that clicking the NEXT button directs users to the corresponding stages for the current project.
- Add a Previous Button:
    - Introduce a Previous button located to the left of the NEXT button for easy backward navigation.
    - The Previous button should be consistently visible across all types of projects, providing a straightforward way for users to return to the prior view.

**Impact:**

- Improved Navigation Flow:
     -Adding Stages to the navigation menu allows users to quickly switch between project components, enhancing workflow efficiency.
    - The Previous button provides users with a simple means to navigate back without needing to rely on browser back functionality.
- Enhanced User Experience:
    - Simplifying navigation helps users to feel more in control of their project flow, leading to increased satisfaction and productivity.
    - Clear navigation pathways contribute to a more intuitive interface, making it easier for users to access important project information.
- Consistent Accessibility:
    - The visibility of the Previous button across all project types ensures a uniform experience, reducing confusion and enhancing usability.

## Task 13: (MAAS-1130) New Changes from Ruchi: Drafted BOM Stage Creation Page

**Description:**

This task involves implementing new changes to the Drafted BOM Stage Creation page as per the latest requirements provided by Ruchi. The changes aim to enhance the user interface and streamline the data entry process.

**Key Changes:**

- Add Icon Beside Stage Name:
    - Include an icon next to the Stage Name field to enhance visual appeal and provide a clearer indication of the purpose of the field.
    - The icon to be added is <i class="ri-pages-line"></i>.
    - Placement: The icon should be positioned next to the Stage Name input field, specifically for stages of type PROCUREMENT.
- Remove Stage Sequence Input Field:
    - Eliminate the Stage Sequence input field from the Drafted BOM Stage Creation page to simplify the form and reduce potential input errors.
    - Ensure that the removal does not impact other functionalities or data validation processes associated with stage creation.

**Impact:**

- Improved User Experience:
    - Adding the icon provides users with visual cues, improving the overall user experience and making the interface more intuitive.
    - Removing the unnecessary input field streamlines the stage creation process, making it faster and more efficient.
- Enhanced Clarity:
    - The icon next to the Stage Name helps in quickly identifying the purpose of the field, reducing ambiguity for users during data entry.
    - Simplifying the form by removing the Stage Sequence field minimizes confusion and focuses users on the most relevant inputs.

## Task 13: (MAAS-1134) UI Fixes in BOM Stage Tracking Page

**Description:**

This task involves making essential UI fixes to the BOM Stage Tracking page on the MaaS | Moglix platform (QA environment). These updates aim to enhance user experience and improve data visibility on the page.

**Key Changes:**

- Addition of Input Date Fields:
    - Fields to be Added:
        - Forecast Start Date
        - Forecast End Date
        - Actual Start Date
        - Actual End Date
    - Placement: The input fields should be arranged according to the provided layout in the reference image below:
- Add Display Texts Below Existing Fields:
    - Text to be Added:
        - Add display texts below the Ready for Manufacturing and Total Required Qty fields for better context and information clarity.
        - Reference Layout: The texts should follow the layout as shown in the image below:
- Changes in Table of BOM:
    - Table Enhancements:
        - Add the class scrollbar to the table div to ensure better scrolling functionality.
        - Implement a fixed header for the table to improve the readability of the column headers while scrolling through the BOM items.

**Impact:**

- Enhanced User Interface:
    - The addition of date fields allows users to input and track critical project timelines more effectively.
    - Display texts provide necessary information, improving user understanding and reducing errors during data entry.
- Improved Usability:
    - A fixed header in the BOM table makes it easier for users to keep track of the columns while scrolling through large datasets.
    - The scrollbar class improves the overall scrolling experience, especially when dealing with extensive BOM lists.

## Task 14: (MAAS-1138) Weightage - For Drafted Check

**Description:**

This task involves implementing an API call to auto-populate the weightage in the drafted check section. The goal is to ensure that the weightage for stages and lots is calculated accurately, providing users with a clear understanding of project progress.

**Implementation Steps:**

- API Call to Auto Populate Weightage:
    - API Endpoint: http://localhost:7073/project/autoUpdate/weightage/468
    - Method: PUT
    - Parameters: 468 (projectId) should be dynamically replaced based on the project being processed.
    - Response Handling:
        - On receiving a 200 OK response from the API, trigger a second API call to fetch updated stage lot data.
- Fetch Stage Lot Data:
    - Call the API: http://localhost:7073/stage/fetch-stage-lot?projectId=468
    - This API will retrieve the latest stage lot data necessary to repopulate the UI.
- Calculating Weightage:
    - Top Lot Weightage:
        - Calculate the total weightage for the top lot by summing the weightage of all associated stages.
    - Top Overall Progress Weightage:
        - Compute the overall project progress weightage by summing all lot weightages.
- UI Updates:
    - Display the calculated top lot weightage in the UI where relevant.
    - Show the top overall progress weightage, incorporating an animated progress bar if feasible.
    - Ensure that the UI updates dynamically after the weightage is populated.
- Animation for Progress Bar (Optional):
    - If possible, add a smooth animation effect to the progress bar that visually represents the weightage updates. This could involve gradually increasing the filled portion of the bar as the calculations are completed.

**Impact:**

- Accurate Weightage Representation:
    - The implementation will ensure that users have access to the most current and accurate weightage data, enabling better decision-making and project tracking.
- Enhanced User Experience:
    - The addition of an animated progress bar will provide users with a visually engaging way to monitor project progress, improving overall user satisfaction and interaction with the application.
- Efficiency Improvements:
    - Automatically updating weightage and recalculating stage and lot weights minimizes manual input errors and ensures consistency across project tracking.

## Task 15: (MAAS-1168) Project List: Store Filter Values for Session Management

**Description:**

This task focuses on enhancing user experience on the project list page by maintaining filter values across sessions. The objective is to ensure that selected filter values persist even when users navigate away from the page, providing a seamless experience without requiring users to reapply filters.

**Impact:**

- Improved User Experience:
    - Users will appreciate the convenience of not having to reapply filters after navigating away and returning to the project list page.
- Efficiency:
    - This feature reduces the time spent on re-selecting filters, allowing users to focus on their tasks more effectively.
- State Persistence:
    - By storing filter values in sessionStorage, the application can maintain the state of user selections, enhancing the overall reliability of the filtering mechanism.

## Task 16: (MAAS-1171) UI Fix for Po Qty & Indian Currency Format in 'More Details' Section

**Description:**

This task involves updating the display format for Purchase Order (Po) Quantity to ensure it is limited to two decimal places. Additionally, the Indian currency format should be applied to the amount, with proper commas and a fixed two-decimal display.

**Impact:**

- Enhanced Readability:
    - Ensuring Po Qty is always displayed with two decimals improves data clarity and consistency.
    - The Indian currency format (₹ 2,12,12,121.00) is more familiar to users in India, enhancing readability and user experience.
- Professional Appearance:
    - Formatting numbers appropriately lends a polished, professional look to the UI, making the system appear more reliable and user-friendly.

## Task 17: (MAAS-1202) Reordering and Implementing SPOC Fields with Dropdown Options

**Description:**

This task involves reordering the SPOC (Single Point of Contact) fields based on the new design requirements. Two fields, Product Manager SPOC and Sales SPOC, will be mandatory and should be placed in the header. The input for these fields will be converted into dropdown menus, with options fetched from the provided API.

**Impact:**

- Improved User Experience:
    - Users can easily select the relevant SPOC from dropdowns, reducing input errors and improving form usability.
    - Mandatory fields ensure critical information is always provided.
- Seamless Integration with API:
    - The API binding ensures that the latest SPOC options are dynamically fetched, providing up-to-date choices for users.

## Task 18: (MAAS-1212) Update API Documentation and Implement Changes for Sales POC in Project Header

**Summary:**

This update involves making adjustments to the API interactions related to Sales POCs in the header of the project page. The APIs for fetching, saving, and updating project details have been modified, with additional properties introduced for handling Sales POC information. The key updates and tasks include:
- Populating Sales POCs in the header page via a dropdown.
- Saving/Updating Sales POCs with selected IDs.
- Mapping Sales POC Data to dropdown options based on the response.
- Modifying UI Elements: Renaming the Sales POC header to 'Project Manager' and removing the 'Moglix Sales POC' field from the PO details.

**Impact:**

- Dropdown Integration: Adds dynamic Sales POC and Project Manager dropdowns. Potential UI performance issues with large datasets.
- Header Label Change: Renaming "Sales POC" to "Project Manager" for clarity, with possible design inconsistencies across pages.
- Input Field Removal: Simplifies the UI by removing the "Moglix Sales POC" field, but may affect backend operations if not coordinated properly.

## Task 19: (MAAS-1266) Update API Documentation and Implement Changes for Sales POC in Project Header

**Summary:**

- Enhanced Filtering: Allows users to filter projects by rating, improving project search functionality. Potential performance impact with complex queries if multiple ratings are selected.
- UI Update: Dropdown for selecting ratings (0-5) will be added, ensuring users can filter by one or more ratings simultaneously. Testing needed to ensure proper interaction with other filters.
- Backend Modification: API update to include the new 'rating' property in the request body.

**Impact:**

- Enhanced Search: Adds rating filter (0-5) for better project filtering and discovery.
- API Update: /project/fetch-projects now supports 'rating' parameter.
- Minimal Performance Impact: Slight increase in processing time with multiple filters.
- Testing Needed: Ensure accurate filtering and UI responsiveness.

## Task 20: (MAAS-1288) Supplier RFQ Forms and Draft Mail Updates

**Summary:**

- Industrial Part Form: The "Process" field will no longer be mandatory, and the "Unit Price" field will be removed.
- Industrial Finishing Form: The "Unit Price" field will be removed.
- Industrial Additional Services Form: The "Unit Price" field will be removed.
- RFQ Draft Mail: Swap the roles of SPOCs between "CC" and "Reply To". For instance, Kaustav will be in "Reply To" and Mukul Tyagi in "CC."

**Impact:**

- Simplified Forms: Users no longer need to input "Unit Price" in the specified forms, reducing the complexity.
- Process Flexibility: Making the "Process" field non-mandatory allows more flexibility in form submission.
- Communication Alignment: Interchanging SPOCs in the RFQ email draft ensures better communication management by placing the relevant SPOC in "Reply To" for direct responses.

## Task 21: (MAAS-1310) Final Exposure Value Display and Formula Update

**Summary:**

- Exposure Value Display:
    - If the exposure value is negative, the font color will change to red.
    - If the exposure value is positive, the font color will change to green.
- Formula Update:
    - Project Exposure: Calculated as (Customer Exposure - Supplier Exposure).
    - Customer Exposure: Defined as (Net Invoice Value - Payment Received).
    - Supplier Exposure: Defined as ((Net Invoice Value - Payment Done) - Supplier CPO).

**Impact:**

- Visual Clarity: The color-coded exposure values will provide instant clarity on project status, allowing quick identification of financial health.
- Accurate Calculations: The updated formula ensures precise calculation of project exposure, leading to more informed decision-making for managing customer and supplier finances.

## Task 22: (MAAS-1318) UI Updates for CPO and SPO Accordion Details

**Description:**

- Font Size Adjustment for View Breakup Button:
    - Target the CSS selector .cpo-details button.viewbreakup.
    - Add the property: font-size: 11px; to improve text visibility on the "View Breakup" button.
- Creation of New CSS Class .po-subscript:
    - Define the class .po-subscript with the following styles:
    - {font-size: 10px; color: #818080; font-weight: 900; margin-top: 1px;}
- Add Subscript (Invoice Value - Credit Notes):
    - Customer Po: Add the new subscript under the "Net Invoice Value" in both the header and inside the accordion.
    - Supplier Po: Similarly, add the subscript below the "Net Invoice Value" in both the header and accordion sections.
- Add Subscript (Net Invoice Value - (Payment Received + Advance)):
    - Customer Po: Add this subscript below "Advance Receivable" in both the header and inside the accordion.
    - Supplier Po: Add this subscript below "Advance Payable" in both the header and inside the accordion.
- Accordion Width Adjustment:
    - Change the width of CPO and SPO accordions from 14.28% to 9.28% for better layout consistency.

**Impact:**

- Improved Readability: The reduced font size for view buttons and subscripts provides a cleaner, more consistent UI.
- Clarity in Financial Details: Subscripts under key financial fields (Net Invoice Value, Advance Receivable/Payable) offer additional financial insights at a glance.
- Layout Optimization: Adjusting accordion widths creates a more structured and aligned presentation of content.

## Task 23: (MAAS-1335) Formula Updates for Customer and Supplier Financial Calculations

**Description:**

- Customer Financial Calculations:
    - Net Invoice Value:
        - Formula: Net Invoice Value = Invoice Value - Credit Notes
    - Amount Receivables:
        - Formula: Amount Receivables = Net Invoice Value - (Payment Received + Advance)
- Supplier Financial Calculations:
    - Supplier PO:
        - Net Invoice Value:
            - Formula: Net Invoice Value = Invoice Value - Debit Notes
        - Amount Payable:
            - Formula: Amount Payable = Net Invoice Value - Payment Done
    Supplier CPO:
    - Rename: Change the label from Debit Notes to Credit Notes.
    - Net Invoice Value:
        - Formula: Net Invoice Value = Invoice Value - Credit Notes
    - Amount Receivables:
        - Formula: Amount Receivables = Net Invoice Value - Payment Received

**Impact:**

Accuracy in Financial Reporting: Updating these formulas ensures accurate calculations for receivables and payables, leading to more reliable financial data.
Clarity in Terminology: Renaming the "Debit Notes" to "Credit Notes" aligns the terminology with standard accounting practices, reducing potential confusion.
Improved User Understanding: Clear formulas for both customer and supplier sections enhance user comprehension of financial positions and obligations, facilitating better decision-making.

## Task 24: (MAAS-1349) Rearrangement of Project Financial Fields

**Description:** The project financial fields are to be rearranged in the following order based on the provided image:

- Row 1:
    - Project ID
    - Total CPO
    - Total SPO
    - GM* Planned
    - GM* Actual
    - LC, BG Charges
    - Net GM* Actual
- Row 2:
    - Project Start Date
    - End Date
    - Cash In
    - Cash Out
    - Amount Receivables
    - Amount Payable
    - Exposure
- Additionally, an information button is to be created for Net GM (Actual)* with the following labels:
    - Net GM: Value in Rs (In %)
    - Delay Interest Cost: Value in Rs (In %)
    - LC Charges: Value in Rs (In %)
    - BG Charges: Value in Rs (In %)

**Impact:**

- Enhanced User Interface: The rearrangement of fields will create a more organized and intuitive layout, improving user experience.
- Clearer Financial Overview: The information button provides users with quick access to important metrics related to the Net GM (Actual), facilitating better financial analysis and decision-making.
- Increased Accessibility: By grouping relevant financial metrics together, users can more easily navigate and understand the project's financial status.

## Task 24: (MAAS-1353) Main Menu Structure Update

**Description**

This update involves renaming the existing "Header List" to "Projects" and creating a new section in the main menu called "Reports." The "Reports" section will include the following sub-menus:
    - Exposure
    - Customer Dashboard
    - Supplier Dashboard
    - Sales Zones

The overall structure of the main menu will be as follows:

```
Projects
├── Project List
└── Unmapped PO List
Reports
├── Exposure
├── Customer Dashboard
├── Supplier Dashboard
└── Sales Zones
Master Data
├── BU Stage Mapping
└── Supplier Discovery
```

**Impact**

- User Experience: The changes will enhance user navigation by providing clearer categories and easy access to reports.
- Usability: Users will benefit from a more organized structure, making it easier to find relevant sections and sub-sections.
- Development: This change will require updates to the frontend code to reflect the new menu structure and may involve testing to ensure all links function correctly.
- Documentation: Any related user guides or documentation may need to be updated to reflect the new menu layout.

## Task 25: (MAAS-1375) Project List Update: Actual GM% Display

**Description**

This update involves modifying the pop-up in the "Project List" section to display both the Actual GM% and the Planned GM%. The following conditions will apply to the display:
Show Actual GM% alongside Planned GM% in the pop-up.
- If Actual GM% is less than Planned GM%, the font color for Actual GM% will be set to red.
- If Actual GM% is greater than or equal to Planned GM%, the font color for Actual GM% will be set to green.
- Additionally, ensure the alignment of the Sample Template button and Bulk Upload button matches the alignment of the Advance and PDC tabs.

**Impact**

- User Experience: This enhancement will provide users with a clearer understanding of their performance by visually indicating whether they are meeting, exceeding, or falling short of their planned gross margin.
- Visual Consistency: Aligning the buttons will ensure a uniform look and feel across the application, improving overall aesthetics and user navigation.
- Development: Frontend modifications will be required to implement the font color changes based on the conditions specified, as well as to align the buttons properly.
- Testing: Thorough testing will be necessary to ensure that the color changes work correctly and that button alignment is consistent across various screen sizes and resolutions.

## Task 26: (MAAS-1380) Project Exposure Value Coloring Update

**Description**

This update focuses on the visual representation of exposure values across projects, customers, and suppliers. The following changes will be implemented:
- Coloring Logic:
    - Exposure Values (for Project, Customer, Supplier) should be displayed in:
        - Red if the value is negative.
        - Green if the value is positive.
    - The use of a negative sign ( - ) will be removed for negative values; exposure values will be colored red without the sign.
- Example:
    - For Project 417, the supplier exposure was previously colored incorrectly and needs to be updated to reflect the correct color coding.
    - For Project 418, the negative sign was displayed where it should not be; ensure the exposure value is simply colored red.
- On-hover Popup Update:
    - Change the text in the on-hover popup to:
    - "Negative exposures are shown in Red, whereas Positive exposures are shown in Green."

**Impact**

- User Experience: This enhancement will improve clarity for users, allowing them to quickly identify negative and positive exposures based on color coding, enhancing decision-making.
- Data Accuracy: Removing the negative sign will streamline the presentation and reduce confusion, ensuring users focus on the color representation instead.
- Development: Adjustments will be required in the frontend code to implement the new color logic and to update the tooltip text for hover interactions.
- Testing: It will be essential to test the color-coding functionality to ensure that all exposure values are displayed correctly according to the specified logic, and that the tooltip displays the updated text as intended.

## Task 27: (MAAS-1388) Add "Revise GM Star" Button for Project Update

**Description**

This update involves adding a button to the project interface that allows users to update the GM star value for a project. The details of the implementation are as follows:
- Button Details:
    - Name: Revise GM Star
    - Placement: The button will be located near the Total Value column header in the project list.
- Functionality:
    - API Endpoint: http://localhost:7073/project/update-project-gm-star
    - HTTP Method: PUT
    - Behavior:
        - The button will be disabled during the API call to prevent multiple clicks.
        - The UI should not reload or refresh the page while the API request is in progress.
        - The button should re-enable once the API response is received.

**Impact**

- User Experience: This enhancement will allow users to update the GM star value conveniently, improving the overall usability of the project management interface.
- Data Integrity: Disabling the button during the API call will prevent accidental multiple submissions, ensuring data integrity and consistent updates.
- Development: Implementation will require updates to the frontend code to add the button and handle the API call with the specified behavior.
- Testing: It will be essential to test the button functionality to ensure it correctly interacts with the API and handles the enabling/disabling behavior as intended.

## Task 28: (MAAS-1406) Enhancements to Internal Customer Report (WSR)

**Description**

This update introduces several enhancements to the Customer WSR (Work in Progress Report) to improve usability and functionality:

1. Remarks Column:
    - New Column: Add a Remarks column against each stage in the customer report.
    - Dropdown Standardization: Remarks will be standardized through a dropdown menu for each stage.
    - Editability: Customer remarks can be edited from the Stage Tracker Page.
    - Editing Interface: Users can edit customer remarks from the Stage Popup in the Remarks Section.
    - Sorting: The dropdown will present an alphabetically sorted list of customer remarks.
    - Search and Select Options: Users can search for remarks and select multiple options.
    - Multi-Select: Selected remarks will be displayed as comma-separated values.
    - Custom Remark Option: Include an "Other" option allowing users to enter a single custom remark (32-character limit).
    - Saving: All inputs must be saved by clicking the Save button.
2. Draft Mail Provision:
    - Draft WSR Button: A new button to draft an email for sending customer reports from the portal.
    - Mail Draft Popup: Clicking on Draft WSR will open a separate popup for drafting the mail.
    - Mail Options: Users can add recipients, attachments, and edit the mail body content when drafting the customer report.
    - Default Attachment: The Customer Report.xls will be automatically attached to the draft mail.
    - Supported Formats: Other supported attachment formats include Doc, PDF, JPG, JPEG, PNG.
    - Add Attachment Button: An Add Attachment button will allow users to upload additional files. Clicking on any attached file will initiate a download.
3. Mail Content Structure:
    - Default Values:
        - Subject: "Work in Progress Report for Project [Project ID: Name]"
        - To: [Placeholder text: "Please enter Customer Email ID"]
        - CC: [Project Manager Email ID; Sourcer Email ID]
        - Attachments: [Customer Project Report.xls]
        - Body:
        ```tex
        Dear Sir/Madam,

        Greetings from Moglix!

        Please find the Work in Progress Report for the project [Project ID: Name] attached with this mail, along with other relevant attachments if any.

        Kindly contact the following in case of any queries:
        [Sourcer Name][Sourcer Email ID]
        ```

**Impact**

- User Experience: The addition of the remarks column and standardized dropdowns will enhance user interactions, making it easier to provide feedback on project stages.
- Efficiency: Drafting emails directly from the portal streamlines communication processes, saving time for users.
- Customization: The option to add custom remarks and additional attachments provides users with flexibility and caters to specific reporting needs.
- Development: The implementation will require updates to the frontend and backend to accommodate the new features and ensure seamless integration.
- Testing: Comprehensive testing will be necessary to validate all functionalities, including remark edits, email drafts, and attachment handling.

## Task 29: (MAAS-1424) Improvements to PDC Functionality

**Description**

This update includes several enhancements to the PDC functionality to improve user experience and ensure data integrity:

1. Table Header Improvements:
    - Z-Index Adjustment: Add a z-index to the table headers in both PDC and Advance sections to improve the visibility of headers during scrolling.
2. Field Modifications:
    - Date Field Update:
        - Rename Date to Transaction Date.
        - Change Transaction Date to a non-mandatory field.
    - UTR Number Change:
        - Rename UTR numbers to UTR Number.
        - Change the UTR number field from a numeric field to an alphanumeric field.
        - Ensure that no spaces are allowed in the UTR number.
        - Implement the same condition for the cheque number field.
3. Field Validations:
    - Disable Credited Option:
        - The Credited option should be disabled if the transaction number for that particular PDC is null.
    - Amount Validation:
        - Ensure that the Amount cannot be 0.
        - Make Cheque Number and Amount mandatory fields.
4. API Call Conditions:
    - Conditional Save API Call:
        - The Save API should only be called if Cheque Number and Amount are not null.
        - If either field is null, display an error message to the user.
5. Additional Improvements:
    - Remove Popup Button: Remove the popup button from *Net GM(Planned)**.
    - Multiple PO Addition: Fix the provision to allow the addition of multiple POs in the header.

**Impact**

- User Experience: Enhancements to the table header visibility and field modifications will streamline the user interface, making it more intuitive.
- Data Integrity: Implementing field validations will ensure that only valid data is submitted, reducing errors in processing.
- Functionality: Conditional API calls will prevent unnecessary interactions with the backend, enhancing performance and reducing load.
- Development: The implementation of these changes will require updates to the frontend validation logic, backend API handling, and user interface elements.
- Testing: Comprehensive testing will be necessary to ensure that all changes function as intended and do not introduce new issues.

## Task 30: (MAAS-1439) Display of Revised CPO Value in Project Header

**Description**

This update introduces a new feature to enhance the visibility of the Revised CPO (Contract Purchase Order) value in the project header.

**Key Changes:**

- Field Addition:
    - Location: In the Project Header under PO Details.
    - New Field: Add a non-editable field labeled Revised Value (Incl Tax) immediately after the Total Value field.
    - API Source: The value for this field will be retrieved from the API.
- Conditional Visibility:
    - The Revised Value field will only be displayed if the retrieved value is not null. If the value is null, this field will be hidden.
- Color Coding:
    - The field will be color-coded based on the comparison between the Revised Value and the Total Value:
    - Red: If the Revised Value is less than the Total Value.
    - Green: If the Revised Value is greater than the Total Value.

**Impact**

- Improved Clarity: Displaying the revised CPO value directly in the project header provides immediate visibility into any changes, helping users to make informed decisions.
- User Experience: The color-coding enhances the user interface by quickly conveying the status of the revised value compared to the total value, allowing for quicker assessments.
- Data Integrity: Ensuring that the revised value is only shown when available prevents confusion caused by displaying empty fields.
- Development: Implementation will require adjustments to the frontend to integrate the new field and its conditional logic.
- Testing: Comprehensive testing will be necessary to ensure the new field behaves as expected under various scenarios, including when the value is null.

## Task 31: (MAAS-1461) Implementation of PO Limit for Partial Payments in Project Financials

**Description**

This update introduces a maximum limit for partial payments within the Project Financials section to ensure better financial control.

- PO Limit Implementation:
    - In the Project Financials section, set the limit for the input amount field for partial payments to ₹100 Crore (100,000,000).
    - If the input exceeds this limit, the value should be capped, and an appropriate message should be displayed to inform the user.
- Maximum Limit Setting:
    - Define the maximum allowable input value for the partial payment as 1000000000 (equivalent to ₹100 Crore).
    - Ensure that the interface does not allow values exceeding this limit.

**Impact**

- Financial Control: Implementing a limit on partial payments helps maintain budgetary discipline and ensures that project financials remain within approved thresholds.
- User Experience: Capping the input amount and providing feedback on invalid entries will enhance the user experience by preventing confusion and ensuring compliance with financial limits.
- Data Integrity: Restricting input values helps avoid erroneous data entry, thus maintaining the integrity of financial records.
- Development: The implementation will require modifications to the input field validation logic within the Project Financials interface.
- Testing: Thorough testing will be necessary to verify that the input limits function correctly and that users receive appropriate feedback when attempting to exceed the limit.

## Task 32: (MAAS-1469) Enhancements in Project Header and Stage Tracker

**Description**

This update aims to improve the user interface and functionality of the Project Header and Stage Tracker sections by implementing several enhancements.

**Key Changes:**

- Reduce Padding in Project Header:
    - Minimize the padding in the project header section to reduce empty spaces, creating a more compact and user-friendly view.
- Delete PO Button Behavior:
    - If the Delete PO button is disabled (for cases where there is only a single PO), hide the button completely instead of leaving it disabled.
- Stage Tracker Placeholder Behavior:
    - In the Stage Tracker, if there is a date value present in either Forecasted Dates or Actual Dates, remove the placeholder text. Retain the placeholder text only if no dates are present.
- Hide 'Saved in' Section:
    - Remove the Saved in section from the Stage Pop-up: Remarks Section to streamline the interface.
- Remove Edit Title Feature:
    - Eliminate the Edit Title Feature and the Remaining Character Text. Remarks will now be named based on the creation date.
- Rename WSR Remarks:
    - Change the label WSR Remarks to Customer WPR Remarks for clarity.
- Fix Icon and Text Alignment:
    - Adjust the alignment of icons and text in the Payment Milestones section to ensure a consistent and professional appearance.
- Add Link to PO in EOC:
    - Integrate a link to the PO in the EOC from the Project Financials: CPO Accordion. Reference the EOC link for Project 509 CPO (Moglix - EOC).
- Remove Download Section:
    - Eliminate the Download Section from the Project Financials: CPO Accordion for a cleaner layout.
- Completion Percentage Calculation:
    - Review and correct the completion percentage calculation for Project 509 in the OPTCL stage, where it is currently displaying 319.61%.

**Impact**

- User Experience Improvement: Reducing padding and hiding unnecessary elements will create a more streamlined and user-friendly interface.
- Enhanced Functionality: Hiding the Delete PO button when not applicable and ensuring placeholder texts behave correctly will improve usability and clarity.
- Clarity in Communication: Renaming remarks and removing unnecessary features will lead to clearer communication of project statuses.
- Visual Consistency: Fixing alignment issues will enhance the overall visual appeal and professionalism of the application.
- Data Integrity: Reviewing completion percentage calculations will ensure accurate reporting and decision-making.

## Task 33: (MAAS-1399) Project List: Statistical Summary of Projects by Status

**Description**

This update introduces a statistical summary feature for the Project List, providing users with a quick overview of the status of projects displayed in the list. The statistics will dynamically update based on any applied search filters, ensuring accuracy in the counts presented.

**Statistics to be Displayed:**

- Total Projects:
    - Displays the total number of projects currently visible in the list, reflecting any filters or searches applied.
- Drafted:
    - Counts the number of projects in the Drafted status.
- Created:
    - Counts the number of projects that have been Created but are not yet in progress.
- In Progress:
    - Counts the number of projects that are currently In Progress.
- Completed:
    - Counts the number of projects that have been marked as Completed.
- Rework:
    - Counts the number of projects that are in the Rework stage.
- Canceled:
    - Counts the number of projects that have been Canceled.

**Impact**

- Enhanced User Insight: Providing a statistical summary will give users a quick overview of project statuses, helping them assess the overall health of projects at a glance.
- Improved Decision-Making: By displaying relevant statistics, users can make informed decisions regarding project management and resource allocation.
- Dynamic Interaction: The statistics will reflect any active filters or searches, ensuring that users have accurate and relevant information at all times.
- User Engagement: A clear and concise statistical summary can enhance user engagement with the project management system, as it simplifies the process of monitoring project statuses.

## Task 34: (MAAS-1059) Revenue Forecast Report

**Description**

The Revenue Forecast Report provides users with an overview of incoming revenues based on planned and forecasted dispatch quantities and dates for the current and upcoming months.

**Workflow Overview:**

- Duration Selection:
    - Users will select a duration from filters, ranging from the current date to the last date of the sixth month from the current month.
    - Initially, the report will show forecasts for the next 12 months, skipping the date range selector in the first iteration.
    - Example:
        - Start Date Minimum: 5/12/22
        - End Date Maximum: 30/06/23
        - Forecasting will cover up to two quarters.
- Accessing the Report:
    - The report will be available as a pop-up from the Project List under the Finance Report section.
- Revenue Report Structure:
    - Project Data: Includes Project ID + Name, Planned Duration, Delay/Ontime, CPO Value, Total Quantity.
    - Invoice Done: Displays the total invoices completed to date, shown in green font.
    - Pop-up for Invoice Breakdown:
        - Fields: Moglix PO No., Invoice No., Invoice Value, Invoice Date.
- Invoice To be Done (Planned):
    - Shows invoices to be done (CPO Value - Invoiced Amount), distributed across different months based on quantities left to be dispatched from each LOT.
    - Assumes invoicing occurs post-dispatch, ignoring existing payment terms.
    - Pop-up with breakup for different LOTS, displaying:
        - Lot No., Remaining Quantity, Invoice Amount, Invoice Date.
- Invoice To be Done (Forecasted):
    - Initially mirrors the Invoice To be Done (Planned) data but allows users to split dispatch quantities into sets with corresponding dispatch dates.
    - Validation messages to ensure data integrity during the splitting process:
        - Error Messages:
            - "Total remaining quantities should match."
            - "Please Enter Remaining Quantity."
            - "Please Enter Due Date."
    - The invoice amount will be calculated based on the ratio of split quantities.
- UI Features:
    - Separate tabs for Invoice To be Done (Planned) and Invoice To be Done (Forecasted).
    - Highlighting: The Invoice To be Done (Forecasted) section will be emphasized.
    - Each month will display the sum total of Invoice To be Done (Forecasted) for that month.

**Calculations:**

- Expected Invoice Amounts:
    - Spread across incomplete lots based on the remaining quantity of the last stage in each LOT.
- Expected Date of Invoice:
    - Calculation based on the completion rate of each stage and expected days to complete for each lot.
    - Formula:
        - Each Stage Completion Rate = ForecastedRange(ForecastedEnd−Start) / (Planned + Tolerance Quantity).
        - Expected Days to Complete = (RemainingQuantityofStage−RemainingQuantityofallPreviousStages) x Sum of (Completion Rate of the Stage + Completion Rate of All Succeeding Stages).
        - Expected Date of Invoice = Current Date + Expected Days to Complete Lot.

**Impact**

- Enhanced Revenue Visibility: The report provides a clear forecast of incoming revenues, allowing for better financial planning and resource allocation.
- User Empowerment: Users can manipulate data based on their needs, with immediate feedback through error messages to maintain data integrity.
- Improved Decision-Making: By forecasting invoices based on real data, users can make informed decisions regarding production and dispatch.
- User-Friendly Interface: A well-structured pop-up with intuitive navigation enhances user experience and facilitates quick access to relevant financial data.

## Task 35: (MAAS-1225) Exposure Dashboard

**Description**

The Exposure Dashboard provides a comprehensive view of Moglix's exposure to all customers and suppliers. It enables users to analyze project counts, total invoiced amounts, and overall exposure values. Users can filter and navigate through customer and supplier details to assess financial standings effectively.

**Key Features**

1. Overall Exposure Overview
    - Displays overall exposure for all customers and suppliers.
    - Key metrics include:
        - Project Count: Total number of projects associated with each customer/supplier.
        - Total Invoiced Amount: The cumulative amount invoiced to each customer/supplier.
        - Total Exposure: The overall exposure for each customer/supplier.
2. Filters
    - Search and Select Filter: Allows users to search for specific customers or suppliers by name.
    - Exposure Filter Options:
        - < 25% of Invoiced Amount
        - 25% - 50% of Invoiced Amount (≥25 and <50)
        - 50% - 75% of Invoiced Amount (≥50 and <75)
        - > 75% of Invoiced Amount (≥75)
3. Project Count Hover Pop-Up
    - Displays detailed information about all projects and their statuses for the selected customer/supplier.
4. Exposure Value Indicators
    - Positive exposure values are displayed in Green.
    - Negative exposure values are displayed in Red.
5. Exposure Info Button
    - On hover, shows the formulas used for calculating exposure values.
6. Exposure Click Pop-Up
    - Uses the existing exposure form from Project Financials, focusing on the Customer/Supplier tab.
    - Users can click on any customer/supplier to navigate to their respective pages.

**Customer Exposure Page**

- Navigation
    - Users can access this page by clicking on a specific customer entry from the Overall Exposure page.
- Key Metrics
    - Total Amount Receivables: Total amount due from the customer.
    - Total Payment Received: Total payments made by the customer.
    - Total Customer Exposure: Overall exposure for the selected customer.

**Project Details**

- Displays all projects associated with the selected customer, including:
    - Project ID - Name: Clickable link redirecting to the project header.
    - Status & Deviation: On hover, shows the same information as in the project list view.
    - Project Manager: Name of the project manager.
    - CPO Value: Includes a button to download the CPO PDF.
    - Total Invoiced Value: Displayed below the CPO value.
    - GM% (Actual) Value*: Includes a button to open the Actual GM*% calculation pop-up.
    - GM%(Planned) Value*: Displayed below the Actual Value.
    - Net GM% (Actual): Info hover shows Delay Interest Cost, Net GM%, and Net GM Absolute Value.
    - Exposure: Button to open the exposure pop-up, focused on the customer tab.
    - Forecasted Revenue: Displays the forecasted revenue amount and date for all pending lots.

**Supplier Dashboard Page**

- Navigation
    - Users can access this page by clicking on a specific supplier entry from the Overall Exposure page.
- Key Metrics
    - Total Amount Payable: Total amount due to the supplier.
    - Total Payment Done: Total payments made to the supplier.
    - Total Supplier CPO: Total CPO for the supplier.
    - Total Supplier Exposure: Overall exposure for the selected supplier.
- Project Details
    - Displays all projects associated with the selected supplier, including:
        - Project ID - Name: Clickable link redirecting to the project header.
        - Status & Deviation: On hover, shows the same information as in the project list view.
        - Project Manager: Name of the project manager.
        - SPO Value: Includes a button to download the SPO PDF.
        - Total Invoiced Value: Displayed below the SPO value.
        - Supplier CPO Value: Displayed for reference.
        - GM% (Planned) Value*: Displayed under the Actual Value.
        - GM% (Actual) Value*: Includes a button to open the Actual GM*% calculation pop-up.
        - Net GM% (Actual): Info hover shows Delay Interest Cost, Net GM%, and Net GM Absolute Value.
        - Exposure: Button to open the exposure pop-up, focused on the customer tab.

**Impact**

- Improved Financial Analysis: Provides a clear understanding of exposure levels to help make informed decisions.
- Enhanced Navigation: Easy access to customer and supplier details improves usability and efficiency.
- Better Project Tracking: Allows for monitoring of project statuses and financial standings in real-time.
- Data-Driven Insights: Users can leverage insights from the dashboard to optimize customer/supplier relationships and manage financial risks effectively.

## Task 36: (MAAS-1572) Update Rupees Number Format to Indian Format in Overall Application

**Description**

This update involves formatting currency values throughout the application to adhere to the Indian number format. The implementation will ensure that:

- Decimal Handling:
    - If the amount is a whole number, it will be displayed without decimals.
        - Example: 4562 will show as 4562.
    - If the amount has decimals, it will show up to two decimal places.
        - Example: 4562.345 will show as 4562.34.
- Currency Formatting:
    - All currency values will be prefixed with the Indian Rupee symbol (₹).
    - Values will be formatted according to the Indian numbering system, using commas for lakhs and crores.
        - Example: 4562383 will be formatted as ₹45,62,383.
- Implementation:
    - Update the existing currencyFormatter function to apply the new formatting rules.
    - Ensure that this formatter is utilized consistently in all areas of the application where monetary values are displayed.

**Affected Areas:**

- Planned Cash In/Cash Out (Header): Ensure that monetary values in this section adhere to the new formatting standards.
- Customer Advances and PDCs (Total Amount) - Advances Tab: Update the formatting for total amounts displayed in this tab.
- Customer Advances and PDCs (Total Amount and Total Credit Amount) - PDCs Tab: Ensure that both total amounts and total credit amounts are formatted correctly.
- Payment Percentage (PO Value) - Supplier Tab: Update the display of PO values to reflect the new currency format.

**Impact**

- Consistency Across the Application: Standardizing currency formatting will enhance the user experience by providing a familiar and easily readable format for users in India.
- Improved Readability: By adhering to the Indian numbering system and currency representation, users can quickly interpret financial information without confusion.
- User Confidence: Proper formatting will build user trust in the application, ensuring that financial data is presented accurately and professionally.
Ease of Maintenance: Centralizing the currency formatting logic in the currencyFormatter function will simplify future updates and maintenance.

## Task 37: (MAAS-1402) Documents Tab: Categorization and Tagging

**Description**

The objective is to establish a comprehensive knowledge repository for project-related documents, including attachments, progress reports, and financial reports. This feature will enhance document management and accessibility within the Knowledge Centre of the application.

**Key Components:**

- Project Documents Section:
    - A new section called Project Documents will be added, accessible from the Knowledge Centre main menu.
    - This section will display all documents associated with all MAAS projects.
    - Users will have the ability to search and filter documents efficiently.
- Individual Project Level Updates:
    - The existing More Details section of individual projects will be restructured into two distinct parts: Project Milestones and Project Documents.
    - By default, the Project Milestones section will be displayed first, with a link provided to access the Project Documents section.
- Attachment Management:
    - The current attachment section in More Details will be removed and replaced with a dedicated Project Documents section to display all attachments related to a specific project.
- Dropdown for Document Classification:
    - A dropdown menu will be introduced to classify the type of attachment with standard document names.
- Fields for Each Attachment:
    - The following fields will be added for each attachment:
        - Created Date: Timestamp indicating when the document was created.
        - Document Type: Dropdown for selecting the type of document, with options including:
            - Costing Sheet
            - PO Documents
            - Customer Documents
            - Supplier Documents
            - Stage Documents
            - Approvals
        - Tag: A custom tagging field (20-40 characters) allowing users to assign relevant tags for reference purposes.
        - Download: Existing functionality to download attachments.
        - Delete: Existing functionality to delete attachments.
        - Saved In: Existing field indicating where the document is stored.

**Impact**

- Enhanced Document Management: Creating a centralized repository for project documents will improve organization and accessibility, making it easier for users to locate necessary files.
- Increased Efficiency: The search and filter functionalities will allow users to find documents quickly, reducing time spent searching for project-related materials.
- Improved User Experience: By categorizing documents and providing tagging options, users can personalize their document organization, leading to a more intuitive navigation experience.
- Streamlined Project Tracking: The separation of Project Milestones and Project Documents will facilitate clearer tracking of project progress and documentation, aiding project managers in oversight and reporting.

## Task 38: (MAAS-1548) Project Stage Delay Accountability

**Description**

The Project Stage Delay Accountability feature aims to establish a systematic approach for identifying and documenting the reasons for delays in project stages. This accountability can fall on any of the stakeholders: the Customer, Supplier, or Moglix. By implementing this feature, the project management team can ensure clarity and responsibility for delays, facilitating better communication and resolution.

**Key Components:**

- Delay Accountability Tab:
    - A new tab titled Delay Accountability will be displayed in the Stage Tracker section for all stages that are delayed.
    - This tab will not be visible for stages that are on time or ahead of schedule.
- Delay Calculation:
    - The system will automatically calculate the total delay in days for the delayed stages.
    - A pop-up will allow users to assign delay accountability to different stakeholders (Customer, Supplier, Moglix) with the option to provide remarks explaining the reasons for the delay.
- Delay Assignment:
    - Users can assign the total delay either completely or partially among the stakeholders.
    - Remarks will be captured for each accountability assignment to provide context.
- Reporting:
    - The overall delay in the project, along with a detailed breakdown by stage or lot, will be available as an HTML/Excel report.
    - This report will include the delay summary, remarks, and accountability assignments.
- Project Dashboard Integration:
    - A summary of the delays will be prominently displayed on the Project Dashboard.
    - Users can access detailed information by clicking on the delay section.

**Impact**

- Clear Accountability: By defining and documenting who is responsible for project delays, the feature enhances accountability among stakeholders, fostering a culture of responsibility.
- Improved Communication: Capturing remarks and reasons for delays allows for transparent communication and helps in addressing issues proactively.
- Data-Driven Decisions: The availability of comprehensive reports will empower project managers to analyze delay patterns and make informed decisions to mitigate future risks.
- Enhanced Project Oversight: The integration of delay summaries into the Project Dashboard provides an at-a-glance overview of project health, enabling timely interventions where necessary.

## Task 38: (MAAS-1699) Add New Status: "Short Close" for Projects

**Description**

This feature introduces a new project status, "Short Close," which is applicable when the actual required quantity is less than the planned required quantity, and the business has successfully fulfilled the actual requirement. The Short Close status will carry all the attributes and implications of the Completed status but will require specific user input when applied.

**Key Components:**

- Status Addition:
    - The Short Close status will be added to the project management workflow.
    - Users can change the status using a dropdown menu, as shown in the reference image.
- Short Close Workflow:
    - Status Flow:
        - Drafted: Assigned upon project creation.
        - Created: Assigned when all project data is completed.
        - In Progress: Assigned when any project stage has actual dates or quantities filled.
    - Users can transition from In Progress to:
        - Completed
        - Short Close
        - Cancel
    - From Completed to Rework and from Short Close or Cancel to N/A.
- Mandatory Inputs:
    - When setting a project to Short Close, users must submit a remark and upload a supporting document.
    - Remarks Field:
        - Placeholder: "Reason for Short Close"
        - Alert Text: "Remarks Required"
        - Character Limit: 500 characters.
- Visibility:
    - After submitting remarks and attachments, the information will be displayed on the Summary page.
    - The attachment name will serve as a link to preview the document.
    - Remarks will also be visible in the project status pop-up on the project list page.
- Canceled Workflow:
    - Similar to the Short Close status, setting a project to Canceled will require a remark and a supporting document.
    - Remarks Field:
        - Placeholder: "Reason for Cancellation"
        - Alert Text: "Remarks Required"
        - Character Limit: 500 characters.
- Excluded from Release:
    - Completed Workflow:
        - An error will be thrown if the project is not 100% completed when attempting to set the status to Completed.
        - If 100% complete, the status will be updated to Completed.
    - Rework Workflow:
        - Users must select the lot/sublot/stage when setting a project to Short Close.
    - Status Filters:
        - The Short Close status will be added to the status filters in the project list view.

**Impact**

- Enhanced Project Management: Introducing the Short Close status allows for better tracking and management of project requirements, ensuring that all stakeholders are aware of the project's actual status.
- Accountability and Documentation: By mandating remarks and document submissions for Short Close and Canceled statuses, the process increases accountability and provides necessary documentation for project records.
- Improved User Experience: The clear workflows and mandatory inputs streamline the process, ensuring that users are guided through the necessary steps for status changes.
- Data Integrity: The validation checks during status transitions (e.g., ensuring 100% project completion) help maintain the integrity of project data, reducing potential errors and confusion.

## Task 39: (MAAS-144) Project Creation Tracker Percentage for Project List Page

**Description**

The purpose of this feature is to provide a visual representation of the data completion status for each project in the project list. This will enable users to quickly assess which projects require additional input to ensure all necessary fields are completed.

**Key Components:**

- Data Completion Calculation:
    - The percentage of data completion will be calculated using the formula:
    - Project Data% = (Total number of completed required fields / Total number of required fields) × 100
    - The following fields will be considered for the calculation:

        | Field                                                                 | Number of Fields           |
        | --------------------------------------------------------------------- | -------------------------- |
        | Project Manager and Sales SPOC                                        | 2 fields                   |
        | Planned Dates in Stages                                               | 2 fields × No. of Stages   |
        | Stage Weightage                                                       | 1 field × No. of Stages    |
        | Customer Payment Terms                                                | 1 field                    |
        | Supplier Payment Terms                                                | 1 field × No. of Suppliers |
        | Cash In                                                               | 1 field                    |
        | Cash Out                                                              | 1 field × No. of Suppliers |
        | LOT/Sublot Quantities, SP/Unit, UOM, Due Delivery Date, Mat Code, HSN | Ignored for now            |
    - Display on Project List Page:
        - The calculated Project Data% will be displayed under the Created On Date column for each project.
        - A visual indicator (such as an icon) will be shown alongside the percentage to indicate the completion status.
    - Pop-up for Missing Data:
        - When a user clicks on the completion percentage icon, a pop-up will appear displaying the details of the missing data fields.
        - The pop-up will list each field that is incomplete, allowing users to quickly identify what needs to be addressed.

**Impact**

- Improved Project Tracking: This feature enables project managers to monitor data completeness efficiently, helping them to take corrective actions as needed.
- Enhanced User Experience: The visual representation of completion status makes it easier for users to assess project health at a glance.
- Increased Accountability: By highlighting missing fields, team members are encouraged to provide necessary information, fostering a culture of accountability.
- Data Quality Assurance: Ensuring that all required fields are completed helps maintain the integrity of project data, leading to more accurate reporting and decision-making.

## Task 40: (MAAS-1762) Customer and Supplier Outstanding and Overdue in Project Financials Section

**Description**

This feature aims to enhance the visibility of outstanding (OS) and overdue (OD) financial values for both customers and suppliers within the Project Financials section. Currently, outstanding and overdue values are only displayed in payment terms. By integrating these values into the Project Financials, stakeholders can better assess financial health and manage cash flows.

**Key Components:**

- Display Locations:
    - Overall Customer Level:
        - Display the outstanding and overdue values at the overall customer level.
    - Overall Supplier Level:
        - Show the outstanding and overdue values at the overall supplier level.
    - Individual Supplier Level:
        - Provide outstanding and overdue values for individual suppliers.
- Calculation Changes:
    - Payment Terms 1 (Case 1): Applicable to the following stages: Advance, RM Inspection, Final Inspection, Against Dispatch, Installation, Hold Warranty, GRN.
        - OS=Total PO Value (Project value from finance)×Payment Term %×Stage Completion %
        - OD=OS
        - If the stage is not mapped, assume 100% stage completion
    - Payment Terms 2 (Case 2): Applicable to After Dispatch.
      - OS=Total Invoiced Amount (from financials)×Payment Term %
      - Overdue Invoiced Value=Sum of net invoices (whose (invoice_date + payment term days) ≥current_date)
      - OD=Overdue Invoiced Value×Payment Term %

**Impact**

- Enhanced Financial Monitoring: Providing visibility into outstanding and overdue amounts allows stakeholders to better manage cash flow and make informed financial decisions.
- Improved Decision-Making: With clearer insights into customer and supplier financials, project managers can take proactive measures to address outstanding and overdue accounts.
- Increased Accountability: By tracking outstanding and overdue amounts, teams are encouraged to follow up with customers and suppliers on pending payments.
- Streamlined Financial Management: Consolidating this information within the Project Financials section reduces the need to switch between different sections, improving efficiency.