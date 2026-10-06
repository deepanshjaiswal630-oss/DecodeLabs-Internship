# 📊 E-Commerce Data Cleaning Project

> **Cleaning, validation, and preparation of raw e-commerce data for analysis**

---

## 📌 1. Project Overview

This project focuses on **cleaning, validating, and preparing an e-commerce dataset** for further analysis.

The raw dataset contains **1,200 order records** with information related to customers, products, pricing, payments, order status, coupons, referrals, tracking, and shipping.

### 🎯 Project Objective

The main objective is to convert the raw dataset into a **clean, consistent, accurate, and analysis-ready dataset** by identifying and correcting common data-quality issues.

---

## 📁 2. Project Files

| File                | Description                                |
| ------------------- | ------------------------------------------ |
| `Raw Data.xlsx`     | Original dataset before cleaning           |
| `Cleaned Data.xlsx` | Final cleaned and validated dataset        |
| `README.md`         | Documentation of the data-cleaning process |

### 📑 Cleaned Workbook

The cleaned workbook contains:

* **Main Data** — Final cleaned dataset
* **Cleaning Log** — Record of cleaning activities and validation checks

---

## 🗂️ 3. Dataset Overview

The dataset contains **1,200 records and 15 fields**.

### Key Information Available

| Category                  | Fields                        |
| ------------------------- | ----------------------------- |
| 🧾 Order Information      | Order ID, Order Date          |
| 👤 Customer Information   | Customer ID, Shipping Address |
| 🛍️ Product Information   | Product, Quantity, Unit Price |
| 💰 Sales Information      | Total Price                   |
| 💳 Payment Information    | Payment Method                |
| 📦 Order Information      | Order Status, Tracking Number |
| 🎟️ Marketing Information | Coupon Code, Referral Source  |
| 🛒 Customer Activity      | Items in Cart                 |

---

# 🧹 4. Data Cleaning Process

The following steps were performed to improve the quality and consistency of the raw dataset.

### 4.1 🔍 Duplicate Check

The dataset was checked for duplicate records and duplicate Order IDs.

**Result:**

* Total records: **1,200**
* Unique Order IDs: **1,200**
* Duplicate Order IDs: **0**

This ensures that each order can be uniquely identified.

---

### 4.2 ❓ Missing Value Handling

Missing values were identified in the **Coupon Code** field.

| Check                         |      Result |
| ----------------------------- | ----------: |
| Missing Coupon Code values    |         309 |
| Replacement value             | `No Coupon` |
| Missing values after cleaning |           0 |

Instead of keeping blank cells, missing coupon values were standardized as **`No Coupon`**.

This makes the dataset easier to filter, group, and analyze.

---

### 4.3 ✂️ Removing Unnecessary Spaces

Text fields were checked for unnecessary leading and trailing spaces.

This helps avoid inconsistencies during:

* Filtering
* Sorting
* Searching
* Grouping
* Pivot-table analysis

---

### 4.4 🏷️ Column Name Standardization

Column names were reviewed and standardized to improve readability.

Examples include:

| Data Field        | Cleaned Name       |
| ----------------- | ------------------ |
| `TotalPrice`      | `Total Price`      |
| `PaymentMethod`   | `Payment Method`   |
| `OrderStatus`     | `Order Status`     |
| `CouponCode`      | `Coupon Code`      |
| `ReferralSource`  | `Referral Source`  |
| `ItemsInCart`     | `Items In Cart`    |
| `TrackingNumber`  | `Tracking Number`  |
| `ShippingAddress` | `Shipping Address` |

---

### 4.5 🧮 Total Price Validation

The **Total Price** field was checked using the following business rule:

**Total Price = Quantity × Unit Price**

Every record was checked against this calculation.

| Validation        | Result |
| ----------------- | -----: |
| Records checked   |  1,200 |
| Records passed    |  1,200 |
| Records failed    |      0 |
| Validation status | ✅ PASS |

A **`Total Check`** field was also added to clearly identify whether each record passed the validation.

---

### 4.6 📅 Data Type Validation

The dataset was checked to ensure that each field uses an appropriate data type.

| Data Type          | Examples                              |
| ------------------ | ------------------------------------- |
| Date               | Order Date                            |
| Numeric            | Quantity, Items in Cart               |
| Numeric / Currency | Unit Price, Total Price               |
| Text               | Product, Payment Method, Order Status |

Correct data types help prevent errors during calculations and analysis.

---

# 📊 5. Data Quality Summary

| Quality Check           |     Status     | Result            |
| ----------------------- | :------------: | ----------------- |
| Duplicate Order IDs     |     ✅ PASS     | 1,200 unique IDs  |
| Missing Coupon Values   |     ✅ FIXED    | 309 → `No Coupon` |
| Extra Spaces            |    ✅ CLEANED   | Standardized      |
| Total Price Calculation |     ✅ PASS     | 1,200 / 1,200     |
| Column Names            | ✅ STANDARDIZED | Completed         |
| Data Types              |    ✅ CHECKED   | Completed         |

---

# 📈 6. Final Dataset Snapshot

| Metric                        |      Final Result |
| ----------------------------- | ----------------: |
| **Total Records**             |         **1,200** |
| **Total Columns**             |            **15** |
| **Unique Order IDs**          |         **1,200** |
| **Missing Coupon Codes**      |             **0** |
| **Total Price Checks Passed** | **1,200 / 1,200** |
| **Duplicate Order IDs**       |             **0** |

### ✅ Final Status

**The dataset is cleaned, validated, and ready for further analysis.**

---

# 🔎 7. Recommended Analysis

The cleaned dataset can be used for:

* 📊 Sales and revenue analysis
* 🛍️ Product performance analysis
* 👥 Customer analysis
* 💳 Payment-method analysis
* 🎟️ Coupon effectiveness analysis
* 📣 Referral-source analysis
* 📦 Order-status analysis
* 🚚 Shipping and tracking analysis
* 📈 Business dashboards
* 🔍 Exploratory Data Analysis (EDA)

---

# ⚠️ 8. Recommended Final Validation

Before performing detailed record-level analysis, it is recommended to cross-check **Payment Method** and **Order Status** against **Order ID**.

This provides an additional check that each operational field is correctly associated with its respective order.

---

# 🔄 9. Data Cleaning Workflow

```text
┌─────────────────────┐
│      RAW DATA       │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│ Check Structure &   │
│ Data Types          │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│ Identify Missing    │
│ Values               │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│ Handle Missing      │
│ Coupon Values       │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│ Check Duplicate     │
│ Order IDs           │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│ Clean Extra Spaces  │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│ Standardize Column  │
│ Names               │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│ Validate Total      │
│ Price               │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│ Final Quality       │
│ Checks              │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│    CLEANED DATA     │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│  READY FOR ANALYSIS │
└─────────────────────┘
```

---

# 🏁 10. Conclusion

The raw e-commerce dataset was systematically cleaned and validated to improve its **accuracy, consistency, completeness, and usability**.

The final dataset contains **1,200 unique orders across 15 fields**. Missing coupon values were standardized, duplicate Order IDs were checked, unnecessary spaces were cleaned, column names were standardized, data types were reviewed, and Total Price was successfully validated for all records.

> **Final Result:** The dataset is structured, validated, and ready for **Exploratory Data Analysis (EDA), visualization, reporting, dashboards, and business analysis.**

---

## 👨‍💻 Project Status

| Project Detail  | Status                    |
| --------------- | ------------------------- |
| Dataset         | E-Commerce Order Data     |
| Records         | 1,200                     |
| Fields          | 15                        |
| Data Cleaning   | ✅ Completed               |
| Data Validation | ✅ Completed               |
| Output          | `Cleaned Data.xlsx`       |
| Overall Status  | 🟢 **READY FOR ANALYSIS** |

---
