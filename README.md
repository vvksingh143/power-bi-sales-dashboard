# Build the Power BI Sales Dashboard

## 1. Import data
Open Power BI Desktop → **Get data → Text/CSV** → select `data/sales_data.csv` → Load.
Set `Order_Date` to Date; `Quantity` to Whole number; `Unit_Price_INR` and `Sales_INR` to Whole number or Currency.

## 2. Create these DAX measures
Select the imported `sales_data` table → **New measure**. Create each measure separately:

```DAX
Total Sales = SUM(sales_data[Sales_INR])
```

```DAX
Total Orders = DISTINCTCOUNT(sales_data[Order_ID])
```

```DAX
Units Sold = SUM(sales_data[Quantity])
```

```DAX
Average Order Value = DIVIDE([Total Sales], [Total Orders], 0)
```

## 3. Add visuals
- Four Card visuals: `Total Sales`, `Total Orders`, `Units Sold`, `Average Order Value`
- Line chart: `Month` on X-axis; `Total Sales` on Y-axis
- Bar chart: `Category` and `Total Sales`
- Bar chart: `City` and `Total Sales`
- Donut chart: `Payment_Mode` as Legend and `Total Sales` as Values
- Slicers: `Region`, `Category`, `Payment_Mode`

## 4. Format and check
- Report title: **Sales Performance Dashboard**
- Format sales as INR currency.
- Ensure month order is chronological (not alphabetical).
- Test that slicers filter all relevant charts.

## 5. Save your report
Save as `Sales_Analytics_Dashboard.pbix`.

**Note:** This repository contains the dataset and build guide, not a prebuilt `.pbix` file. Only claim the Power BI dashboard as completed after creating and testing it in Power BI Desktop. The sample data is fictional.
