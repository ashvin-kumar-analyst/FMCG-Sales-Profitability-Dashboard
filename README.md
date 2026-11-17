# FMCG Sales & Profitability Dashboard
An interactive Excel dashboard that analyses sales, profit, margin, discounting and channel performance for an FMCG business across 2024 and 2025.

![FMCG Dashboard Preview](dashboard%20preview.png)

## Objective
Give a sales manager a single page that answers:
- How much did we sell, how much did we earn, and what is the profit margin?
- Which categories and products drive profit, not just sales?
- Which regions and channels perform best or worst?
- How do discounts affect profitability?
- How do sales trend month by month and year over year?

## Dataset
Practice dataset of FMCG orders from January 2024 to December 2025.
| Item | Detail |
|---|---|
| Raw records | 5,010 rows, 14 columns |
| Clean records | 5,000 orders |
| Categories | 6 (Beverages, Edible Oil, Home Care, Packaged Food, Personal Care, Staples) |
| Regions | 4 (East, North, South, West) |
| Sales channels | 4 (E-commerce, General Trade, Modern Trade, Wholesale) |

**Columns:** Order_ID, Order_Date, Product_ID, Product_Name, Category, Region, State, City, Quantity, Unit_Price_INR, Unit_Cost_INR, Discount_Rate, Sales_Channel, Payment_Mode.

## Data Cleaning
- Removed 10 duplicate orders (5,010 to 5,000 rows)
- Standardised inconsistent category text (for example `edible oil` to `Edible Oil`)
- Checked for blanks (15 missing city values, which do not affect the analysis)
- Verified data types for dates, quantities and prices
- Converted the data range into an Excel Table so pivots stay in sync

## Calculated Columns
| Column | Formula |
|---|---|
| Gross Sales | `Quantity × Unit Price` |
| Discount Amount | `Gross Sales × Discount Rate` |
| Net Sales | `Gross Sales − Discount Amount` |
| Total Cost | `Quantity × Unit Cost` |
| Profit | `Net Sales − Total Cost` |
| Profit Margin | `Profit ÷ Net Sales` |
| Year, Month No, Month, Quarter | Derived from Order Date |

All profit and margin figures are calculated on **net sales (after discount)**.

## Dashboard Components
- **4 KPI cards:** Net Sales, Total Profit, Profit Margin, Total Orders
- **Monthly trend:** Net sales by month, 2024 vs 2025
- **Category:** Net sales vs profit
- **Region:** Net sales by region
- **Channel mix:** Share of net sales by sales channel
- **Top 10 products:** Ranked by profit
- **Discount vs margin:** Net sales and margin at each discount level
- **4 slicers:** Year, Region, Category, Sales Channel
- **Key insights panel**

## Key Results (All Data)
| Metric | Value |
|---|---|
| Net Sales | ₹39,71,563 |
| Total Profit | ₹8,02,330 |
| Profit Margin | 20.2% |
| Total Orders | 5,000 |

## Key Insights

### 1. Sales leader is not the margin leader
| Category | Net Sales (₹) | Profit (₹) | Margin |
|---|---|---|---|
| Staples | 13,99,007 | 2,22,112 | 15.9% |
| Personal Care | 7,08,533 | 1,91,221 | 27.0% |
| Beverages | 6,29,939 | 1,41,352 | 22.4% |
| Home Care | 5,43,186 | 1,17,066 | 21.6% |
| Edible Oil | 4,80,984 | 74,608 | 15.5% |
| Packaged Food | 2,09,913 | 55,970 | 26.7% |

Staples brings 35.2% of net sales but only 27.7% of profit. Personal Care brings 17.8% of sales but 23.8% of profit. Edible Oil has the lowest margin (15.5%).

### 2. Discounts erode margin
| Discount | Net Sales (₹) | Margin |
|---|---|---|
| 0% | 12,67,061 | 24.0% |
| 2% | 4,27,451 | 22.2% |
| 5% | 10,20,856 | 20.2% |
| 8% | 5,33,455 | 17.4% |
| 10% | 5,79,542 | 15.5% |
| 15% | 1,43,200 | 10.8% |

Margin falls by about 13 percentage points between no discount and a 15% discount, while the 15% band contributes only about 3.6% of net sales.

### 3. Channels and regions are fairly balanced
- Wholesale is the largest channel (27.3%), followed by Modern Trade (24.8%), General Trade (24.3%) and E-commerce (23.7%).
- West (₹10.20 lakh) leads and South (₹9.57 lakh) trails, a gap of only 6.6%.

### 4. Growth and seasonality
- Net sales grew 5.8%, from ₹19.30 lakh in 2024 to ₹20.42 lakh in 2025.
- Monthly peak: April 2025 (about ₹2.08 lakh). Monthly low in 2025: June (about ₹1.39 lakh).

### 5. Product concentration
Basmati Rice 5kg is the top product by profit and contributes about 16.8% of total profit.

## Recommendations
- Review discounts of 10% and above, because they cut margin sharply for a small share of sales.
- Review pricing and costs for Staples and Edible Oil, which have large volumes but the lowest margins.
- Promote Personal Care and Packaged Food, which have the highest margins.
- E-commerce has the smallest share, so it is the clearest room for channel growth.

## Tools and Skills Demonstrated
Microsoft Excel: Tables, calculated columns, Pivot Tables, Pivot Charts, Slicers, GETPIVOTDATA, data cleaning, dashboard design and KPI storytelling.

## How I Built It
1. Cleaned the raw data (duplicates, text case, blanks) and converted it into an Excel Table
2. Added calculated columns for sales, cost, profit and margin
3. Built pivot tables for trend, category, region, channel, products and discount impact
4. Created pivot charts and arranged them on a single dashboard sheet
5. Added slicers (Year, Region, Category, Channel) and connected them to the pivots
6. Linked the KPI cards to a pivot so they respond to the slicers
7. Wrote the key insights panel from the findings

## Repository Contents
| File | Description |
|---|---|
| `FMCG_Sales_Analysis_dashboard.xlsx` | Final Excel workbook with data, pivots and dashboard |
| `dashboard preview.png` | Screenshot of the dashboard |
| `README.md` | Project documentation |

## How to Use
1. Download `FMCG_Sales_Analysis_dashboard.xlsx`
2. Open it in desktop Microsoft Excel
3. Go to the **Dashboard** sheet
4. Click the slicers on the right to filter the charts and KPI cards
5. Clear a filter using the funnel icon in the slicer header

Slicers and pivot tables do not run in the GitHub preview, so please download the file to use the interactive version.

## Limitations
- This is a practice dataset, so the findings illustrate the analysis method and should not be read as real company results.
- The analysis is descriptive. It shows what happened, not why it happened.
- Key insight text on the dashboard is static and does not change with slicers.

## Author
**Ashvin Kumar**
GitHub: [ashvin-kumar-analyst](https://github.com/ashvin-kumar-analyst)
