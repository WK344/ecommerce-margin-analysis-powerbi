# ecommerce-margin-analysis-powerbi

# E-commerce Margin Analysis (Power BI)

A Power BI dashboard that answers one question: **sales look steady, so where is the profit margin going?**

![Dashboard](dashboard.png)

## Dataset

- **Source:** E-commerce Orders Dataset 2026 on Kaggle (MIT license). Add the Kaggle link here.
- **Size:** 30,000 orders, 41 columns (customers, products, pricing, discounts, shipping, payment, returns, profit)
- **Period:** January 2023 to December 2026
- **Note:** The dataset appears to be synthetic, so the findings describe this dataset, not a real company.

## Tools

- Power BI Desktop
- Power Query (data preparation)
- DAX (measures)

## What I built

A one-page dashboard with:

- Total sales and total profit per year
- Profit margin per year
- Profit margin by discount level
- Return rate per year and per product category
- Profit by product category
- Sales by country

### Key measures

```
Profit Margin % = DIVIDE(SUM(ecommerce_orders_dataset[Profit_Amount]), SUM(ecommerce_orders_dataset[Order_Amount]))
```

```
Return Rate % = DIVIDE(CALCULATE(COUNTROWS(ecommerce_orders_dataset), ecommerce_orders_dataset[Returned] = "Yes"), COUNTROWS(ecommerce_orders_dataset))
```

Margin is calculated as total profit divided by total sales, not by adding up the margin percentage column, because percentages cannot be added together.

## Key findings (in this dataset)

1. **Discounts reduce profit.** Margin falls from about 22% with no discount to about 13% at a 40% discount.
2. **Growth is flat.** Sales, profit, and margin (about 20%) are almost the same from 2023 to 2026.
3. **Electronics drives profit.** It earns nearly half of all profit, while Groceries, Toys, and Books add very little despite many orders.
4. **Returns are steady.** About 10% of orders are returned.

## Files

- `ecommerce-margin-analysis.pbix`: the Power BI report
- `dashboard.png`: screenshot of the dashboard

## How to open

Download the `.pbix` file and open it in Power BI Desktop (free for Windows).
