# Digital Business Management System

## 🚀 Project Overview

"Digital Inventory & Ledger App" is a comprehensive, custom-built Digital Business Management System designed and developed from the ground up for a specialized Retail & Wholesale Trading Business. This full-stack application was engineered to solve critical business challenges, moving the client from manual record-keeping to a robust, secure, and efficient digital ecosystem.

The system is not just a simple inventory tracker; it is a complete operational suite that handles everything from secure user authentication and vendor management to advanced invoice generation, accounts receivable tracking, and business intelligence analytics. The entire application was built with a focus on solving real-world business problems, such as processing sales returns, managing dynamic discounts, tracking overdue payments, and providing a clear, real-time overview of the company's financial health.

This project was a development effort, encompassing front-end UI/UX design, complex back-end business logic, database architecture, and the deployment of a secure, custom API and a public-facing payment portal.

---

## 🛠️ Technology Stack

This project was built using a modern, scalable, and secure technology stack:

*   **Front-End:** Vanilla JavaScript (ES6+ Modules), HTML5, CSS3
*   **Back-End (Database):** Google Firebase - Realtime Database & Authentication
*   **Back-End (Custom API):** Node.js & Express.js for secure, server-side logic
*   **Deployment:**
    *   **Main Application:** Firebase, GitHub actions
    *   **Custom API Server:** Railway
    *   **Customer Payment Portal:** Netlify
*   **Key Libraries:**
    *   **Chart.js:** For dynamic and interactive data visualization.
    *   **SweetAlert2:** For professional, modern user notifications and modals.
    *   **jsPDF & html2canvas:** For advanced, client-side PDF generation.
    *   **PrintJS:** For streamlined, cross-browser printing.
    *   **ExcelJS:** For powerful, custom Excel report generation.
    *   **Flatpickr:** For a consistent and professional date picker UI.
    *   **TailwindCSS:** For the modern UI of the analytics and tracking dashboards.

---

## ✨ Core Features & Application Modules

The application is comprised of distinct modules/pages, each designed to handle a specific aspect of the business workflow.

### 1. Login Page
The secure gateway to the application, ensuring only authorized personnel have access.
*   **Secure Authentication:** Utilizes Google Firebase Authentication for robust and reliable email/password verification.
*   **Minimalist Design:** The UI was intentionally designed to be clean and straightforward for a fast and efficient login experience.

<img width="1366" height="598" alt="image" src="https://github.com/user-attachments/assets/0b0f27d1-8de2-47fb-aa69-d644b7d3b019" />

### 2. Signup Page
A highly secure, custom-built user registration system designed to prevent unauthorized account creation.
*   **Custom Backend Security:** A separate Node.js/Express.js server, deployed on Railway, handles a secret "Passkey" validation. This architecture moves sensitive logic off the client-side, ensuring only individuals with the pre-shared secret key can create an account.
*   **Brute-Force Protection:** The system automatically locks out the registration form for 15 minutes after three consecutive incorrect passkey attempts, effectively mitigating automated attacks and unauthorized access attempts.

<img width="1366" height="596" alt="image" src="https://github.com/user-attachments/assets/452956c6-5efb-4a6d-b22e-8fec065d5bef" />

### 3. HomePage (Application Portal)
The central navigation hub of the application, completely redesigned from a basic list into a modern user portal.
*   **Modern UI/UX:** A responsive grid of interactive "Action Cards" with professional styling, multi-layer box shadows, hover/active state animations, and integrated Font Awesome icons.
*   **Account Management Hub:** A user dropdown menu provides access to "Change Password" and "Delete Account" workflows, both secured by password re-authentication and the custom passkey API.
*   **Notification System:** The homepage features on-demand notifications that alert the user to overdue invoices or a net loss in profit, providing immediate business insights upon login.
*   **Personalization:** The greeting message is personalized by fetching and displaying the user's saved `username` from the database.

| With Notifications |
|----------------|
| <img width="1366" height="596" alt="image" src="https://github.com/user-attachments/assets/aa063ef9-ded5-4af1-bebe-3a776d47a6d6" /> |<br>

| With Accounts Actions |
|----------------|
| <img width="1366" height="586" alt="image" src="https://github.com/user-attachments/assets/d692fc7e-ddc3-464d-8454-f351b108ae02" /> |<br>

| With Changing Passwords | 
|----------------|
| <img width="1366" height="590" alt="image" src="https://github.com/user-attachments/assets/39b639b5-7b64-491b-8487-a413bea3299c" /> |<br>

| With Account Deletion |
|----------------|
| <img width="1366" height="591" alt="image" src="https://github.com/user-attachments/assets/8a72e8c0-80ae-46d6-ad42-11bd58a0832f" /> |<br>

### 4. Add Purchase (Vendor Dashboard)
The main dashboard for viewing and managing all business vendors and their associated purchases.
*   **Vendor Dashboard UI:** A professional, scrollable list of vendor "cards," each displaying key information and a calculated financial summary.
*   **Live Vendor Search:** A real-time search engine allows for the instant filtering and discovery of any vendor by name.
*   **Financial Summary Calculation:** The backend logic automatically calculates and displays the "Total Purchasing from this Vendor" on each card by aggregating all historical purchase data.

<img width="1363" height="707" alt="image" src="https://github.com/user-attachments/assets/e0c4c8c1-c1ed-42cc-ab28-09206bc05b69" />

### 5. Add/Update Vendor Page
A dedicated workspace for creating new vendors or adding new purchases to existing vendors.
*   **Dynamic Purchase Forms:** A dedicated page allows for recording new purchases with a dynamic sub-form for adding an unlimited number of items to a single purchase order.
*   **Real-time Calculation Engine:** A JavaScript-based engine provides financial accuracy by instantly calculating the sub-total of purchased items, applying vendor discounts, and displaying a 100% accurate net total.
*   **Data Integrity:** The system includes robust validation to prevent the creation of duplicate vendors or products.
*   **Previous Purchase Locking:** When updating an existing vendor, all previously recorded purchase items are displayed in a "locked" (read-only) state to prevent accidental alteration of historical records, a key client requirement.

<img width="1361" height="671" alt="image" src="https://github.com/user-attachments/assets/b086f0d3-6408-47ac-bcef-1455803521d9" />

### 6. Customer Details Page
A central dashboard for viewing and managing all registered customers.
*   **Live Financial Summaries:** The dashboard displays a table of all registered customers, each with a real-time, calculated summary of their `Amount Spent` and `Amount Due`.
*   **"Invoices & Payments" Integration:** A dedicated button on each customer row provides a direct link to a detailed tracking page for that specific customer's entire invoice and payment history.
*   **Secure Deletion Workflow:** A multi-step confirmation process using SweetAlert2 prevents accidental deletion of customer records.
*   **Expanded Search:** The search functionality allows for finding customers by both `Name` and `Mobile Number`.

<img width="1366" height="595" alt="image" src="https://github.com/user-attachments/assets/adc7d16e-e460-43f6-8b20-adf48678bde0" />

### 7. Update Customer Details Page
A powerful workspace for creating new sales or editing the records of existing registered customers.
*   **Dual-Mode Architecture:** The page intelligently operates in two modes ("New Customer" vs. "Existing Customer"), dynamically changing its behavior to either present a blank form or pre-fill all data for an existing customer.
*   **Live Financial Dashboard:** A real-time dashboard at the bottom of the page calculates and displays `Previous Amount Spent`, the total of newly added items, the overall discount, and the final `Net Purchase Cost`.
*   **Advanced Item Filtering:** A sophisticated, collapsible filtering interface allows the user to instantly filter a customer's entire purchase history by `Date Range` and `Product Name`.
*   **Visual Data Separation:** The UI was engineered to create a clear visual distinction between previously purchased items and new items being added in the current session, using dynamic headers and separators.
*   **Dedicated "Update Details" Workflow:** A separate workflow allows for the modification of a customer's core information (Address, Contact, Email) with a "before and after" comparison modal for verification.

<img width="1366" height="595" alt="image" src="https://github.com/user-attachments/assets/3730606c-f436-492a-a6d6-579c69865613" />

### 8. Generate Invoice Page (for Registered Customers)
A sophisticated, purpose-built engine for creating new, professional invoices for registered customers.
*   **Professional Document Design:** Invoices are generated with a branded header, a clean two-column layout for customer and invoice information, and a pixel-perfect financial summary.
*   **Real-Time Calculation Engine:** All financial fields (subtotals, discounts, totals, balances, grand total) are calculated instantly as the user types.
*   **PDF & Print Generation:** An advanced engine using jsPDF, html2canvas, and PrintJS creates professional PDF downloads and printouts. It includes **dynamic table sizing logic** to ensure invoices with up to 20 items fit perfectly on a single A4 page.
*   **Robust Data Validation:** A comprehensive validation engine prevents the creation of invoices with duplicate IDs, duplicate product codes, or logical financial errors.
*   **Version Control:** Upon saving, the system creates the first version of the invoice in a dedicated history log, providing a complete audit trail from the moment of creation.
*   **Session Locking:** Once an invoice is generated, the UI becomes "read-only" for that session to prevent accidental changes.

<img width="1352" height="1287" alt="11 Generate Invoice - Registered" src="https://github.com/user-attachments/assets/68052e6d-937a-4d2f-b441-f76184de8a0e" />

Generated Invoice - Downloaded PDF Result
<img width="408" height="578" alt="12 Generated Invoice - Registered" src="https://github.com/user-attachments/assets/b746f44a-c662-4844-b9d1-75b09e76aed0" />

### 9. Invoice & Payment Tracking Page (for Specific Customers)
A dedicated dashboard that provides a complete financial overview of a single registered customer.
*   *(This description is based on the features of the `Invoice&Payment.html` file when filtered for one customer, as it's a dedicated view accessed from the Customer Details page).*
*   **Customer-Specific KPIs:** The page displays dynamic summary cards for the selected customer's `Total Amount`, `Amount Received`, `Pending`, `Overdue`, and `Total Invoices`.
*   **Intelligent Invoice Table:** The dashboard lists all invoices for that customer, with color-coded rows for immediate visual feedback on the status of each invoice.
*   **Complete Action Suite:** Provides a full set of actions for each invoice, including `View`, `Download`, `Update`, `Notes`, `History`, and `Delete`.

<img width="1357" height="868" alt="13 Invoice Payment Tracing - Resgistered" src="https://github.com/user-attachments/assets/791b1d50-91cf-48e6-875c-d603a4592a15" />

### 10. Track Payment Breakdown & Invoice Scheduling
A powerful slide-out panel that serves as a sub-application for managing the payment schedule of a single invoice.
*   **Payment Scheduling System:** Allows the user to add and manage multiple payment "schedules" (installments) in addition to the final deadline.
*   **Payment Breakdown Feature:** For each schedule, the user can record multiple partial payments, complete with the date, amount, and a description for each transaction.
*   **Real-Time Calculations & Statuses:** The panel includes its own calculation engine that instantly updates summary cards and assigns a visual status (`Pending`, `Completed`, `Overdue`) to each schedule.
*   **Urgency-Based Sorting:** The schedules are automatically sorted to display the most urgent (e.g., Overdue Deadlines) at the top.

<img width="1366" height="607" alt="14 Payment Breakdown - Side Panel" src="https://github.com/user-attachments/assets/c150e6eb-8874-436e-a34e-c39dbb5d0b30" />

### 11. Update Invoice Page (for Registered Customers)
A dedicated, secure workspace for processing revisions to existing invoices, such as sales returns or discount adjustments.
*   **Secure "Update > Edit > Save" Workflow:** The page loads in a "read-only" state. An "Update" button must be clicked to fetch the latest data and unlock the fields, preventing accidental edits.
*   **Sales Return & Financial Adjustment Logic:** The interface allows for the deletion of items (sales returns) and the modification of financial fields like `Discount`. The system then recalculates all totals.
*   **Version Control on Save:** Upon saving, the system creates a **new, timestamped version** in the invoice's history log, providing a complete audit trail of every change.
*   **Atomic Database Updates:** The save process atomically updates the invoice history, the root invoice object, the customer's master purchase list, and then re-syncs all global financial summaries to ensure data integrity across the entire application.

<img width="1354" height="1308" alt="15 Update Invoice - Registered" src="https://github.com/user-attachments/assets/f1b2161c-9f5f-4c1c-9d64-64c605fa364b" />

### 12. Generate Walk-in Customer Invoice Page
A specialized, streamlined Point-of-Sale (POS) system built from scratch for non-registered, cash-and-carry customers.
*   **POS Financial Model:** The financial summary was re-engineered for cash sales, removing "Previous Dues," adding an "Extra" charges field, and automatically setting `Amount Paid` equal to the `Invoice Total`.
*   **Automatic Invoice ID Generation:** A custom function generates a unique, sequential Invoice ID with a `W-` prefix and a date stamp, creating a trackable numbering scheme distinct from registered customer invoices.
*   **Local Storage Persistence:** The system uses browser `localStorage` to automatically save the user's work, preventing data loss on accidental page refreshes.
*   **Dedicated Backend Integration:** Finalized walk-in invoices are saved to a separate, dedicated path in the Firebase database for clean data separation.

<img width="1353" height="1343" alt="16 Generate Invoice - Walk-in" src="https://github.com/user-attachments/assets/e04f5e07-1499-4a1f-8807-fc9dcc0ef8d8" />

Generated Invoice - Downloaded PDF Result
<img width="414" height="582" alt="17 Generated Invoice - Walk-in" src="https://github.com/user-attachments/assets/2b9898aa-4ff6-47fe-8d29-88923c4eeb11" />

### 13. All Invoices Dashboard (Global Command Center)
The primary command center of the application, consolidating data from both `Registered` and `Walk-in` customers into a single, unified view.
*   **Data Aggregation Engine:** The backend fetches, combines, and processes invoice data from two separate database locations.
*   **Advanced Multi-Filtering:** Features over a dozen filtering and sorting options, including a unique multi-select customer name filter that allows for creating reports on custom groups of clients.
*   **Client Notification System (Urgency Sort):** Solved a direct client request for an overdue notification system. The default sorting algorithm automatically floats the most urgent invoices (e.g., `Final Overdue`) to the top, with color-coded rows providing an immediate visual alert system.
*   **Custom Excel Export Engine:** A powerful export feature generates a multi-sheet Excel file with a dedicated summary page (listing all active filters) and a data page that exactly matches the user's filtered view.

<img width="1359" height="1120" alt="18 All Invoice Page" src="https://github.com/user-attachments/assets/c2fed996-6842-4068-ae22-93a8ac5112b8" />

### 14. Sales Return on Invoices Page (for Walk-in Customers)
A dedicated page to handle the specific business need for processing sales returns or making adjustments to finalized walk-in customer invoices.
*   **Secure Edit Workflow:** The page loads in a "read-only" state. The user must click an "Update" button to unlock the fields, ensuring all changes are intentional.
*   **Sales Return Logic:** The unlocked interface allows for the deletion of items from the original invoice, with the system automatically recalculating all financial totals to reflect the returned goods.
*   **Session Storage Caching:** The system uses `sessionStorage` to cache all unsaved work during an editing session, preventing data loss on accidental page refreshes.
*   **Atomic "Save Changes" Engine:** A backend process uses a `set` command to completely overwrite the old walk-in invoice record with the new, updated data, ensuring the database always reflects the latest state.

<img width="1356" height="1279" alt="19 Sales Return - Walk-in Customer" src="https://github.com/user-attachments/assets/976d61df-81e9-4d1a-816f-8aa0689d2840" />

### 15. Manage Inventory Page
A centralized module for viewing and managing all product stock.
*   **Automatic Population:** The inventory is automatically populated in real-time as new purchases are recorded from any vendor.
*   **High-Performance Search:** An efficient search algorithm allows for the instant filtering of the entire inventory list by product name.
*   **Independent Product Addition:** A pop-up modal allows for the quick addition of new products directly to the inventory without requiring a formal vendor purchase.
*   **Data Export:** The entire inventory can be exported to a formatted Excel file with a single click.

<img width="1366" height="594" alt="20 Manage Inventory" src="https://github.com/user-attachments/assets/f39ef5d1-2303-4d57-9ffd-40d8ebe49e46" />

### 17. Ledger Page
A flexible and powerful tool for manual financial record-keeping, completely re-architected based on client feedback.
*   **Optimized Manual Entry:** A user-friendly interface designed for quick and easy manual entry of debit (expenses) and credit (investments).
*   **Advanced Filtering & Search:** A comprehensive search engine to query all ledger entries by `Date Range`, `Entry Type`, `Amount Range`, or a text search of the `Narration` field.
*   **Data Export:** The filtered ledger view can be exported to both PDF and Excel formats for offline analysis.
*   **Financial Summaries:** The page includes dynamic summary cards for `Total Expenses`, `Total Investments`, and `Total Entries` that update in real-time with the filters.

<img width="1364" height="1308" alt="21 Ledger" src="https://github.com/user-attachments/assets/720689ab-98c9-42dd-9202-9cec7af945c4" />

### 16. Sales & Business Intelligence Analytics Dashboard
The capstone of the project, this dashboard transforms raw data into actionable business intelligence.
*   **Centralized Data Aggregation:** An engine fetches and consolidates data from four different database locations (Registered Invoices, Walk-in Invoices, Vendor Purchases, and Ledger Expenses) to power all calculations and visualizations.
*   **12 Real-Time KPIs:** The dashboard displays 12 critical, real-time Key Performance Indicators, including `Total Revenue`, `Gross Profit`, `Net Profit/Loss`, and `Pending Receivables`.
*   **Interactive Charts & Graphs:** The dashboard features multiple dynamic charts built with Chart.js, including a pie chart for revenue breakdown, a doughnut chart for financial health, and horizontally scrollable bar charts for monthly performance and expense categorization.
*   **Dual-Filter System:** The dashboard has a main filter for the KPIs and a separate, independent filter for the time-series charts, providing granular control over data analysis.

<img width="1352" height="2280" alt="22 Sales   Analytics" src="https://github.com/user-attachments/assets/01d56d17-83fb-422a-a670-1e0b4b56b948" />

---

## 🌐 External Branding & Payment Portal

In addition to the core application, a suite of features was developed to enhance the client's brand and streamline their customer payment process.

*   **Custom Logo Design:** Brand logo was designed from scratch and integrated throughout the application and all client-facing documents.
*   **Deployed Customer Payment Portal:** A separate, public-facing website was developed and deployed to Netlify. This professional, mobile-responsive page is linked via QR codes on all invoices and provides customers with an easy way to find the company's bank and Easypaisa details.
*   **"Tap to Copy" Functionality:** The payment portal includes interactive buttons that allow customers to copy payment information to their clipboard with a single click, reducing errors and improving user experience.
*   **Application Branding:** The core application was equipped with a full set of favicons and a web app manifest file, allowing it to be professionally branded in browser tabs and saved to a mobile device's home screen.

[The screenshot of the Payment Portal cannot be displayed in order to maintain the client’s confidentiality]

---

## 📬 Contact

*   **Developed by:** Muhammad Ashir (with co-contributions by [Ibtesam Hussain](https://github.com/ibtesam-hussain/))
*   **LinkedIn:** [linkedin.com/in/Ashir-Qayyum](https://www.linkedin.com/in/ashir-qayyum/)]
*   **Email:** [muhammadashir2004@gmail.com](mailto:muhammadashir2004@gmail.com)

---

© 2025 Muhammad Ashir — All Rights Reserved
