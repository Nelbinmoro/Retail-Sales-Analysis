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

- **Improve seasonal planning.** Build inventory, staffing and promotions ahead of the December to February peak, and test a targeted March and April campaign, since March and April is weak every year.
- **Protect profitable categories.**  Maintain appropriate product availability for major profit contributors such as Computers and Home Appliances while reviewing the performance of lower-profit categories..
- **Review lower-margin lines.** Negotiate costs on The Phone Company and Cell phones (56.6% margin) and review Games and Toys and Tailspin Toys (lowest margins and small sales).
- **Develop the online channel.** Assess opportunities to grow online sales while maintaining delivery performance and monitoring fulfilment costs.It matches store margins, grows its share every year and delivers faster than before.
- **Investigate store performance** Review the nine physical stores without recorded sales and examine the factors associated with differences in revenue across stores.
- **Use customer behavior carefully.** Build retention offers for repeat buyers and the top 20% of customers, and design for the 60+ segment, the largest age group.
- **Test Sunday trading.** Sunday carries 1.6% of revenue; find out whether stores close and what the opportunity is.
- **Validate unusual patterns.** Check for incomplete records, operational closures, or data-quality issues that could explain unusually low monthly or weekday sales.

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

This project conducted an end-to-end analysis of retail sales data using Python, Pandas, NumPy, Matplotlib, and Seaborn. By integrating the Customers, Products, Sales, and Stores datasets, the analysis examined sales performance, product profitability, customer purchasing behavior, pricing relationships, seasonal trends, sales channels, and physical-store performance. The objective was to identify meaningful patterns in the data and translate them into insights that could support business decision-making.

- **Revenue and Profitability Performance**

    The annual analysis showed that revenue increased from approximately $6.9 million in 2016 to a peak of $18.3 million in 2019. Revenue grew by 72.4% in 2018 and 42.7% in 2019, before declining by 49.1% to approximately $9.3 million in 2020. During this period, profit margins remained relatively stable at around 58%–59%. The revenue decline coincided with a reduction in order volume, suggesting that changes in sales activity contributed to the observed performance fluctuations. However, the available figures do not establish the precise causes of these changes. The 2021 data covers
    only approximately seven weeks, so it should not be compared directly with complete years.

- **Product and Category Profitability**

    The analysis identified Computers as the leading product category by total profit, generating approximately $11.2 million, followed by Home Appliances at approximately $6.2 million. Games and Toys contributed substantially less total profit, at approximately $0.35 million. The analysis also showed that the category generating the highest revenue does not necessarily have the highest profit margin. This demonstrates the importance of evaluating revenue, total profit, and profit margin together when assessing category performance.

    At the individual product level, profitability varied considerably. Refrigerator models from Fabrikam and Litware were among the highest-profit products per unit, while several cable products generated very low profit per unit. These findings suggest that product decisions should consider both sales volume and unit profitability rather than relying exclusively on total sales.

- **Brand Performance**

    Adventure Works was the strongest brand among those analyzed, generating approximately $11.8 million in sales and $7.0 million in profit. Contoso and Wide World Importers also made substantial contributions to overall sales and profitability. Although brands with higher sales generally contributed more total profit, total profit alone does not indicate which brands have the strongest margins. Comparing sales, profit, and margin together provides a more complete view of brand performance.

- **Pricing and Quantity Sold**

    The product-level analysis examined the relationship between unit price and quantity sold across 2,492 products. Pearson correlation was approximately -0.129, while Spearman correlation was approximately -0.148. Both values indicate a weak negative association between price and quantity sold. Although higher-priced products tended to sell slightly fewer units, the relationship was weak, and the scatter plot showed considerable variation in sales volume across price levels.

    Therefore, price alone is not a reliable predictor of product demand. Product category, brand, customer preferences, competition, and promotional activity may also influence sales volume, although their individual effects were not established by this analysis. Pricing decisions should consequently consider demand and profitability together rather than assuming that reducing prices will automatically increase sales.

- **Customer Purchasing Behavior**

    The customer analysis showed that revenue was distributed across multiple high-value customers rather than being dominated by a single customer. The highest-revenue customer generated approximately $61,000, while several other leading customers generated around $36,000–$42,000 each. Male customers contributed slightly higher revenue, profit, and quantity sold than female customers, but the differences were relatively small.

    The analysis also examined customer groups and the relationship between customer age and financial performance. Customer age showed essentially no linear relationship with the main financial variables. This suggests that age alone may not be useful for explaining differences in revenue or profit within the analyzed data. Customer segmentation and retention strategies should therefore consider purchasing history and revenue contribution alongside demographic characteristics.

- **Seasonal and Monthly Sales Patterns**

    Monthly analysis revealed considerable variation in sales and profit throughout the year. February recorded the highest monthly sales at approximately $7.9 million, followed by December at approximately $7.5 million. Profit also peaked in February at approximately $4.6 million, with December contributing approximately $4.4 million. March and April showed substantial declines, with April recording particularly low sales and profit.

    These patterns indicate that performance varied across months and that certain periods contributed disproportionately to annual results. Businesses can use such patterns to inform inventory planning, staffing, and promotional schedules. However, unusually low results should be investigated to determine whether they reflect genuine demand patterns, incomplete data, or operational factors before decisions are made.

- **Online and Physical-Store Performance**

    Physical stores contributed approximately 79.5% of total revenue, equivalent to $44.35 million, while online sales contributed approximately 20.5%, or $11.40 million. This shows that physical stores represented the larger revenue channel in the analyzed period. At the same time, the online revenue share increased from 16.8% in 2016 to 22.3% in 2020, indicating a growing contribution from online sales.

    Online and physical-store profit margins were similar, at approximately 58.5% and 58.6%, respectively. Online delivery analysis also showed an average delivery time of approximately 4.5 days, with a median of 4 days. The results suggest that the online channel is a meaningful part of the business and may offer opportunities for further development. Future investment decisions should consider growth potential, customer demand, fulfilment costs, and operational capacity.

- **Physical-Store Size and Performance**

    The store-level analysis examined 57 physical stores with recorded sales. Store size showed a moderate positive association with total revenue, with a Pearson correlation of approximately 0.60 and a Spearman correlation of approximately 0.53. This indicates that larger stores generally tended to generate higher revenue within the analyzed group. However, the relationship does not prove that increasing store size will cause revenue to increase. Location, customer demand, product mix, and store operations may also influence performance.

    Nine physical stores had no recorded sales transactions. These stores should be investigated to determine whether the absence of sales reflects inactive operations, missing records, or another explanation. Store size should be treated as one factor in performance evaluation rather than as the sole measure of store effectiveness.

Overall, this project demonstrates how data cleaning, dataset integration, feature engineering, exploratory data analysis, statistical analysis, and visualization can be used to investigate retail business performance. The analysis identified Computers as a major contributor to profit, highlighted substantial variation in sales across months and years, showed that physical stores generated the majority of revenue, and found a moderate positive association between physical-store size and revenue. It also established that the relationship between product price and quantity sold was weak, illustrating the limitations of using a single variable to explain customer demand.

The key takeaway is that retail performance cannot be understood through revenue alone. A more complete evaluation requires considering revenue, profit, profit margin, sales volume, customer contribution, seasonal variation, channel performance, and store-level factors together. By combining these measures and validating unusual patterns before acting on them, businesses can make more informed decisions about product strategy, inventory planning, customer retention, channel development, and store operations.

---

**Author:** Nelbin Nelson
**Role:** Aspiring Data Analyst  
**Skills demonstrated:** Python, Pandas, NumPy, Matplotlib, Seaborn, Data Cleaning, Exploratory Data Analysis, Statistical Analysis, Business Insights

**Portfolio:** nelbin-portfolio.vercel.app 
**LinkedIn:** https://in.linkedin.com/in/nelbin-nelson 
**GitHub:** https://github.com/Nelbinmoro
