# Retail Analytics – Where Is Profit Leaking?

**Team project | Python | Exploratory Data Analysis (EDA) | Statistical Analysis**

## 1. Project overview

This project investigates sales and profitability patterns in a retail/e-commerce business. It aims to identify areas associated with lower profit and develop practical, evidence-based business recommendations.

**Main research question:** Where is profit leaking in the retail business, and which factors are associated with reduced profitability?

### Supporting questions

1. Which sales channels, customer segments, countries/regions and products have the highest and lowest sales and profit?
2. How are discounts, returns, delivery performance and marketing channels associated with profit?
3. What practical actions could improve profitability?

## 2. Project objectives

- Load, inspect and document the supplied datasets.
- Check missing values, duplicates, data types and relationships between tables.
- Analyse sales, profit, products, customers, channels, discounts, returns and delivery.
- Apply suitable statistical tests and explain their limitations.
- Identify negative-profit orders and product lines.
- Present findings through clear tables and visualisations.
- Develop recommendations supported by the analysis.

## 3. Dataset description

The project uses five CSV files:

| Dataset | Rows in notebook preview | Purpose |
|---|---:|---|
| `customer_master.csv` | 25,000 | Customer attributes and acquisition information |
| `dataset_statistics.csv` | 1 | Supplied high-level dataset summary |
| `ecommerce_sales_customer_analytics_150k.csv` | 138,116 | Order-level sales, customer, currency, status, channel and delivery information |
| `order_items.csv` | 397,569 | Product-line quantities, discounts, sales, costs and profit |
| `product_catalog.csv` | 1,175 | Product, category, brand, supplier and product-cost information |

The supplied summary reports a date range of **1 January 2021 to 31 December 2025**. The notebook should be treated as the source of the detailed analysis; figures should be refreshed if the data or notebook changes.

## 4. Project structure

```text
Retail_Analytics/
├── Data/
│   └── archive_extracted/
│       ├── customer_master.csv
│       ├── dataset_statistics.csv
│       ├── ecommerce_sales_customer_analytics_150k.csv
│       ├── order_items.csv
│       └── product_catalog.csv
├── outputs/
├── README.md
├── PROJECT_PLAN.md
└── Retail_Analytics_Updated_Full_Notebook.ipynb
```

Keep the original CSV files unchanged. Save any exported charts, tables and reports in `outputs/`.

## 5. Tools and libraries

- Python
- Jupyter Notebook
- pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy
- Git and GitHub for version control and team collaboration

Install the main libraries, if required:

```bash
python -m pip install pandas numpy matplotlib seaborn scipy jupyter
```

## 6. How to run the project

1. Clone or open the team's GitHub repository.
2. Open the `Retail_Analytics` project folder in Visual Studio Code.
3. Confirm that the five CSV files are available in `Data/archive_extracted/`.
4. Open `Retail_Analytics_Updated_Full_Notebook.ipynb`.
5. Select the Python kernel installed on your computer.
6. Run the notebook from the first cell to the last cell.
7. Review the generated tables, charts and statistical results.
8. Save final charts and reports in `outputs/`.

If the notebook cannot locate the CSV files, check the `candidate_dirs` list in the data-loading cell and update it to match the local folder structure.

## 7. Analytical approach

The notebook follows this workflow:

1. Import libraries and load the five datasets.
2. Review dataset dimensions, column names and data types.
3. Check missing values, duplicates and identifier relationships.
4. Parse dates and create calendar features.
5. Inspect currencies and financial consistency.
6. Validate joins and avoid row multiplication.
7. Build order-level and item-level working tables.
8. Conduct exploratory analysis of order status, sales channel, customer segment, geography, monthly trends and products.
9. Analyse discounts, returns, cancellations and delivery.
10. Analyse customers and marketing channels.
11. Conduct correlation analysis and selected statistical tests.
12. Build a profit-leakage investigation table.
13. Formulate recommendations and document limitations.

## 8. Five evidence-based recommendations

The recommendations below are based on the results currently displayed in the notebook. Correlation and group comparisons are not proof of causation.

### Recommendation 1 — Introduce discount approval limits and margin checks

**Evidence:** Item-level discount percentage had a negative Pearson correlation with profit in every currency, ranging from **-0.17 to -0.24**. The notebook's discount bands also show that average item profit was negative for the **above-50% discount band in six of the seven currencies**; GBP was the exception, with a small positive average.

**Action:** Introduce approval requirements for high discounts, especially discounts above 30% and 50%. Before a promotion is approved, calculate the expected contribution after discount, product cost and fulfilment costs. Run controlled promotion tests and monitor profit per item, not sales volume alone.

**Measure:** Average profit per item, profit margin, share of items sold at discounts above 30%, and number/value of negative-profit items.

### Recommendation 2 — Investigate and resolve negative-profit orders

**Evidence:** The notebook identified **1,296 order-level rows with negative profit**, representing approximately **0.94%** of the sales rows, and **5,426 negative-profit item rows**. The USD group had the largest number of negative-profit orders (**938**), while AED had the highest negative-profit order rate (**1.44%**).

**Action:** Create a recurring exception report for orders and product lines where recorded profit is below zero. Review discounts, product cost, shipping cost, tax, returns and data-entry issues for each exception. Prioritise both high-volume currencies and currencies with higher negative-profit rates.

**Measure:** Number and value of negative-profit orders, negative-profit rate by currency, and the proportion of exceptions resolved.

### Recommendation 3 — Improve return-status and return-reason data completeness

**Evidence:** The `return_status` field was missing for **128,654 of 138,116 sales rows**; 9,462 rows were marked `Returned`. The notebook therefore cannot safely treat missing return status as “not returned.”

**Action:** Make return status a required field in the order-management workflow. Use consistent status values and require a return reason when an order is returned. Reconcile return records with order status and refund records before drawing conclusions about the financial impact of returns.

**Measure:** Percentage of orders with a populated return status, percentage of returned orders with a reason, and reconciliation rate between returns and refunds.

### Recommendation 4 — Evaluate marketing channels using profit and campaign cost, not sales alone

**Evidence:** Organic Search recorded the highest total profit among the listed marketing channels within each currency in the notebook's marketing summary. However, the notebook does not establish channel profitability after marketing spend, so this is not proof that Organic Search has the highest return on investment.

**Action:** Preserve Organic Search as a channel to investigate further, while collecting campaign spend, customer acquisition cost and attributed conversion data for every channel. Compare contribution profit after marketing cost and use small controlled budget tests before reallocating spend.

**Measure:** Contribution profit after campaign spend, customer acquisition cost, conversion rate and return on marketing spend, calculated separately by currency.

### Recommendation 5 — Investigate delayed deliveries and standardise fulfilment reporting

**Evidence:** The delivery-status summary contains **16,886 Delayed** orders and **86,916 On Time** orders. The notebook also reports 24,557 rows labelled `Cancelled` in the delivery-status field, so delivery and order-status definitions should be checked for consistency before interpreting their financial effects.

**Action:** Review delayed and cancelled delivery records by carrier, region, order value and shipping cost. Standardise the definitions of order status and delivery status, and record the actual delivery date and reason for delay. Use the results to identify operational bottlenecks rather than assuming delays caused lower profit.

**Measure:** On-time delivery rate, delayed-order rate, cancellation rate, average shipping cost and customer complaints, reported by region and currency where relevant.

## 9. Important data and interpretation rules

- **Do not add different currencies together.** Analyse financial values separately by currency unless a verified exchange-rate source and conversion date are available.
- The order-items dataset contains multiple rows per order. Do not directly join it to order-level sales and sum order-level values without checking for duplication.
- Attach currency to item-level rows through a verified `order_id` relationship before currency-specific item analysis.
- Investigate differences between sales-level and item-level financial totals before deciding which figure is authoritative.
- Missing return status is unknown; it must not be recoded as “not returned” without evidence.
- Correlation does not establish causation.
- Statistical significance does not automatically indicate business importance. Report test assumptions, group sizes and practical context.
- Do not publish customer names, postal codes or other personally identifying information in reports or presentations.

## 10. Current analytical limitations

- Some return-status values are missing, limiting return analysis.
- Financial values are recorded in multiple currencies and cannot be combined directly.
- Sales-level and item-level profit figures require reconciliation before they are treated as interchangeable.
- Marketing channel totals do not by themselves show campaign return on investment; campaign-cost data is required.
- Delivery-status categories need consistent definitions and validation.
- Findings should be updated after the team completes final validation and reruns the notebook from beginning to end.

## 11. Team workflow

The shared `main` branch contains the integrated project. Team members should work on their own branches, commit changes, push their branches and submit pull requests for review before merging into `main`.

See [`PROJECT_PLAN.md`](PROJECT_PLAN.md) for the sprint goal, project plan, Kanban board, task owners, risks and retrospective template.

## 12. Expected deliverables

- Completed and reproducible Jupyter Notebook.
- Clean, documented project repository.
- Five evidence-based business recommendations.
- Supporting tables and visualisations in `outputs/`.
- README and Agile project plan.
- Final project report/presentation, if required by the course.
- Sprint retrospective completed after the project work is finished.
