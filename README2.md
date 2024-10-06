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

## Task 23: (EOC-3145) Introduce New CPO Source & New CPO Item Type


































# DIGIMRO
# Credlix (Nuphi and Exim)
# MaaS