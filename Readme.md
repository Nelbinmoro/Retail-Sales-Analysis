# Retail Sales Data Analysis | Python

An end-to-end exploratory data analysis project that investigates retail sales performance, product profitability, customer purchasing behavior, seasonal trends, and store performance using Python.

## Project Overview

This project analyzes four interconnected retail datasets — Customers, Products, Sales, and Stores — to uncover patterns in revenue, profit, product performance, customer contribution, and sales channels.

The goal is to transform raw retail data into actionable business insights and recommendations that can support better commercial decisions.

**Key focus areas:**
- Sales and profit trends over time
- Product and category profitability
- Customer purchasing behavior and revenue concentration
- Online versus physical-store performance
- Store size and revenue relationships
- Delivery performance and seasonality

## Business Problem

Retail businesses need to understand what drives revenue and profitability, which products and categories perform best, how customers contribute to sales, and how store and online channels compare.

This project addresses these questions through data cleaning, feature engineering, exploratory analysis, statistical relationships, and data visualization.

## Tools and Technologies

| Tool | Purpose |
|---|---|
| Python | Data analysis and calculations |
| Pandas | Data cleaning, transformation, grouping, and merging |
| NumPy | Numerical operations |
| Matplotlib | Data visualization |
| Seaborn | Statistical visualization |
| Jupyter Notebook | Analysis workflow and documentation |

## Dataset

The project uses four related datasets:

| Dataset | Description | Rows |
|---|---|---:|
| Customers | Customer demographics and location | 15,266 |
| Products | Product details, categories, brands, costs, and prices | 2,517 |
| Sales | Order line items, dates, quantities, and relationships | 62,884 |
| Stores | Store locations, floor area, and opening dates | 67 |

**Data period:** 2016–2021, with 2021 containing only a partial period.

The datasets are connected using customer keys, product keys, and store keys.

## Project Workflow

1. **Data understanding:** Examined dataset structure, data types, descriptive statistics, and missing values.
2. **Data cleaning:** Addressed missing values, converted numeric fields, and preserved valid sales transactions.
3. **Data integration:** Combined sales data with customer, product, and store information for analysis.
4. **Feature engineering:** Created revenue, profit, age, date-based features, and delivery duration.
5. **Exploratory data analysis:** Investigated trends, comparisons, distributions, and relationships using visualizations.
6. **Statistical analysis:** Used correlation and ranking techniques to examine relationships and performance patterns.
7. **Business interpretation:** Translated findings into insights and recommendations.

Missing delivery dates were retained in the main sales dataset. Delivery performance was analyzed only for transactions with available delivery dates. The online store record was excluded from physical-store size analysis because it has no physical floor area.

## Key Business Questions

The analysis investigates 12 questions:

- How did revenue and profit change over time?
- What seasonal and weekday patterns exist?
- Which categories drive profit, and how do their margins compare?
- Which brands generate high sales but weaker margins?
- Is product price associated with quantity sold?
- Which products generate the highest and lowest profit per unit?
- How concentrated is revenue among customers?
- Which customer segments contribute most to revenue?
- How do online and physical-store revenues compare?
- Is store size related to store revenue?
- How fast is online delivery?
- Which numerical variables are related?

## Key Findings

### 1. Revenue Growth and Decline
- Revenue increased from approximately **$6.9 million in 2016** to a peak of **$18.3 million in 2019**.
- Revenue declined by approximately **49% in 2020**.
- Profit margins remained relatively stable at around **58%–59%**, suggesting that changes in sales volume were more closely associated with revenue fluctuations than changes in overall margin.

### 2. Seasonal Sales Patterns
- December and February were the strongest months, at approximately **1.64× and 1.60× the average monthly revenue**, respectively.
- April was consistently the weakest month, with revenue around **0.13× the average month**.
- Saturday contributed approximately **23.7% of revenue**, while Sunday contributed around **1.6%**.

### 3. Product Category Profitability
- Computers and Home Appliances together contributed approximately **53.8% of total profit**.
- Computers alone contributed approximately **34.5% of total profit**.
- Category margins varied within a relatively narrow range, showing why total profit and profit margin should be evaluated together.

### 4. Brand Performance
- Adventure Works was the leading brand by revenue, generating approximately **$11.85 million** with a profit margin of about **58.5%**.
- The Phone Company ranked fifth by revenue among the leading brands, but had the lowest margin among the top five at approximately **56.8%**.

### 5. Pricing and Sales Volume
- Product price had a weak negative relationship with quantity sold.
- Pearson correlation was approximately **-0.13**, while Spearman correlation was approximately **-0.15**.
- Price alone was not a reliable predictor of product demand.

### 6. Customer Revenue Concentration
- The top 10 customers contributed only approximately **0.76% of total revenue**.
- The top 20% of customers generated around **55.3% of revenue**.
- Approximately **61.2% of customers** placed more than one order.

### 7. Online vs Physical Stores
- Physical stores generated approximately **79.5% of total revenue**, or **$44.35 million**.
- Online sales contributed approximately **20.5%**, or **$11.40 million**.
- Online and physical-store profit margins were similar, at approximately **58.5% and 58.6%**, respectively.
- Online revenue share increased from **16.8% in 2016** to **22.3% in 2020**.

### 8. Store Size and Revenue
- Among 57 physical stores with recorded sales, store size had a moderate positive association with revenue.
- Pearson correlation was approximately **0.60**, while Spearman correlation was approximately **0.53**.
- Store age had a much weaker relationship with revenue, with a correlation of approximately **0.05**.
- Nine physical stores had no recorded sales and were flagged for further investigation.

### 9. Online Delivery Performance
- Online orders took approximately **4.5 days on average** to arrive, with a median of **4 days**.
- Approximately 75% of orders with available delivery dates arrived within 6 days.
- Average delivery time improved from approximately **7.3 days in 2016** to **4.0 days in 2020**.

## Business Recommendations

Based on the findings, the project proposes the following actions:

- **Plan for seasonal demand:** Prepare inventory, staffing, and promotions ahead of the December–February peak and investigate the recurring April decline.
- **Protect high-profit categories:** Prioritize availability and pricing strategies for Computers and Home Appliances.
- **Review weaker margins:** Investigate costs and profitability for lower-margin brands and categories.
- **Continue online-channel investment:** Online sales have growing revenue share, comparable margins, and improving delivery times.
- **Investigate inactive stores:** Verify the nine physical stores with no recorded sales and review the weakest-performing locations.
- **Strengthen customer retention:** Develop retention strategies for repeat customers and high-value customer groups.
- **Investigate weekday patterns:** Examine the low Sunday revenue contribution to determine whether it reflects store closures, customer behavior, or data limitations.

## Project Structure

```text
Retail-Sales/
│
├── data/
│   ├── raw/
│   │   ├── Customers.csv
│   │   ├── Products.csv
│   │   ├── Sales.csv
│   │   └── Stores.csv
│   │
│   └── processed/
│
├── notebooks/
│   └── retail-sales-analysis.ipynb
│
├── outputs/
│   └── charts/
│
├── README.md
└── requirements.txt
```

## How to Run

**1. Clone the repository**

```bash
git clone <your-repository-url>
cd Retail-Sales
```

**2. Install dependencies**

```bash
pip install -r requirements.txt
```

**3. Open Jupyter Notebook**

```bash
jupyter notebook
```

**4. Run the analysis**

Open the notebook in the `notebooks` folder and execute the cells in order.

Ensure the four CSV files are placed in `data/raw/` and that the notebook uses the appropriate relative paths.

## Limitations

- The 2021 data covers only a partial period and should not be compared directly with complete years.
- Correlation indicates association, not causation.
- Customer age is approximated using the order year and birth year.
- Missing delivery dates limit the number of transactions available for delivery analysis.
- The available data does not provide discount and return information for evaluating their impact on profitability.
- Store size and revenue may be influenced by other factors, such as location, demand, product mix, and store operations.

## Conclusion

This project demonstrates how Python-based data analysis can turn raw retail data into meaningful business insights.

The analysis identifies key revenue and profit drivers, seasonal patterns, customer contribution, channel performance, and store-level relationships. It also highlights areas that require further investigation, such as the sharp revenue decline in 2020, recurring low April and Sunday sales, and physical stores with no recorded sales.

The central takeaway is that retail performance should be evaluated using multiple measures — including revenue, profit, profit margin, sales volume, customer contribution, and operational performance — rather than relying on a single metric.

---

**Author:** Nelbin Nelson
**Role:** Aspiring Data Analyst  
**Skills demonstrated:** Python, Pandas, NumPy, Matplotlib, Seaborn, Data Cleaning, Exploratory Data Analysis, Statistical Analysis, Business Insights

**Portfolio:** nelbin-portfolio.vercel.app 
**LinkedIn:** https://in.linkedin.com/in/nelbin-nelson 
**GitHub:** https://github.com/Nelbinmoro
