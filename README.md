# DecodeLabs Internship – Data Analytics

Workspace for assignments and projects completed during the Data Analytics Internship at Decode Labs.

## Projects

| # | Project | Files |
|---|---------|-------|
| 1 | Data Cleaning & Preparation – E-Commerce Orders | `Project-1.xlsx`, `Project1_Change_Log_Report.docx` |

---

## Project 1: Data Cleaning & Preparation

### Description

This project audits and cleans a raw sales-orders dataset (**1,200 rows × 14 columns**, January 2023 – June 2025) to make it reliable for analysis. The work follows the three Project 1 requirements: **identify missing values, remove duplicates, and correct data formats**, and ends with a verification gate.

### Key Results

| Quality indicator | Before | After |
|-------------------|--------|-------|
| Total records | 1,200 | 1,200 |
| Missing values (null cells) | 309 | 0 |
| Duplicate Order IDs | 0 | 0 |
| Duplicate Tracking Numbers | 0 | 0 |
| Incorrectly formatted dates | 0 | 0 |
| `TotalPrice` ≠ `Quantity` × `UnitPrice` | 0 | 0 |

- **Missing values:** the only defect was 309 blank cells in `CouponCode` (25.75% of rows). They represent orders placed without a coupon, so they were labelled **"No Coupon"** instead of deleting the rows.
- **Duplicates:** none found in `OrderID`, `TrackingNumber`, or full rows. Repeated `CustomerID` values are legitimate repeat customers.
- **Formats:** dates validated as true dates (ISO 8601), text trimmed and standardized, and 29 floating-point artifacts in `TotalPrice` rounded to two decimals.
- **Business rules:** all `TotalPrice`, range, and ID-pattern checks passed with 0 violations.
- **Verification Gate:** **PASSED** (0% error rate on unique IDs and date formats, 0 remaining nulls).

### Repository Files

| File | Purpose |
|------|---------|
| `Project-1.xlsx` | The workbook with three sheets: `RAW` (original data), `Data_Dictionary` (column profiling: count, nulls, unique values, min, max, average), and `Clean_Data` (cleaned dataset with a validation column). |
| `Project1_Change_Log_Report.docx` | Full report: methodology, findings per phase, change log (CR001–CR007), and the verification gate. |

### Dataset Overview

- **Products (7):** Chair, Desk, Laptop, Monitor, Phone, Printer, Tablet
- **Order statuses (5):** Cancelled, Delivered, Pending, Returned, Shipped
- **Payment methods (5):** Cash, Credit Card, Debit Card, Gift Card, Online
- **Referral sources (5):** Email, Facebook, Google, Instagram, Referral
- **Coupon codes:** FREESHIP, SAVE10, WINTER15, No Coupon

**Columns:** `OrderID`, `Date`, `CustomerID`, `Product`, `Quantity`, `UnitPrice`, `ShippingAddress`, `PaymentMethod`, `OrderStatus`, `TrackingNumber`, `ItemsInCart`, `CouponCode`, `ReferralSource`, `TotalPrice`

### Methodology

1. **Strategic imputation:** detect nulls and hidden placeholders and handle them without unnecessary deletion.
2. **Integrity audit:** verify "one truth, one record" on `OrderID`, `TrackingNumber`, and complete rows.
3. **Format standardization:** ISO 8601 dates, trimmed text, numerics at two decimals.
4. **Validation and gate:** business-rule checks and final zero-error verification.

### How to Run

This is an Excel project, so there is nothing to install or compile.

1. **Clone the repository**
   ```bash
   git clone https://github.com/amlabdelaziz-hub/DecodeLabs-Internship.git
   cd DecodeLabs-Internship
   ```
2. **Open the workbook** in Microsoft Excel (2016 or later), LibreOffice Calc, or Google Sheets:
   ```bash
   # Windows
   start Project-1.xlsx

   # macOS
   open Project-1.xlsx

   # Linux
   xdg-open Project-1.xlsx
   ```
3. **Explore the sheets** in this order: `RAW` → `Data_Dictionary` → `Clean_Data`.
4. **Read the report** (`Project1_Change_Log_Report.docx`) to see what was changed and why.

> **Note:** If the `Date` column appears as a number, format the column as *Date*.

### Tools Used

- Microsoft Excel (advanced Excel features)
- Microsoft Word (change log report)

---

## Author

**Aml Abdelaziz Ahmed** – [GitHub](https://github.com/amlabdelaziz-hub)
