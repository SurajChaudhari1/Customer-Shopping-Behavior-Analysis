# Customer Shopping Behavior Analysis
> End-to-end data analytics project using Python, SQL, and Power BI

## What This Project Does
This project analyzes shopping behavior of 5,000 customers to find what drives revenue, who the best customers are, and how to grow the business. The full pipeline goes from raw data → cleaning → SQL analysis → interactive dashboard.

## Tools Used
| Tool | Purpose |
|------|---------|
| Python (Pandas) | Data cleaning and EDA |
| PostgreSQL | Business problem solving with SQL |
| Power BI | Interactive dashboard |
| Jupyter Notebook | Development environment |

## Project Structure
```
├── notebooks/
│   └── eda_cleaning.ipynb       # Python EDA and data cleaning
├── sql/
│   └── business_queries.sql     # 12 SQL business questions
├── dashboard/
│   └── shopping_dashboard.pbix  # Power BI dashboard file
├── data/
│   └── customer_clean.csv       # Cleaned dataset (5,000 rows)
└── README.md
```

## Phase 1 — Python EDA
**Dataset:** 5,050 rows × 17 columns → cleaned to 5,000 rows × 17 columns

What was fixed:
- Removed 50 duplicate customer records
- Filled 2,075 null values using group means and logical defaults
- Fixed wrong product-category mappings using a correction dictionary
- Standardized all column names to snake_case
- Exported clean data to PostgreSQL using SQLAlchemy

## Phase 2 — SQL Analysis (12 Business Questions)
| # | Question | Key Finding |
|---|---------|------------|
| Q1 | Top revenue category? | Electronics — $486K (48% of total) |
| Q2 | Do discounts increase spend? | Yes — avg +$37 with discount |
| Q3 | Revenue by gender? | Male > Female > Other |
| Q4 | Who are high-value discount users? | Top 10 identified for VIP targeting |
| Q5 | Best and worst rated products? | Gloves highest; Phone lowest (2.94) |
| Q6 | Which shipping makes most money? | Express — $429K total, avg $358/order |
| Q7 | Subscribers vs non-subscribers? | Subscribers spend 63% more |
| Q8 | Which products get most discounts? | Laptop (51.7%), Phone (51.5%) |
| Q9 | Customer segmentation? | 61% loyal, 27% returning |
| Q10 | Top 3 products per category? | Shirts (315), Shoes (303) lead |
| Q11 | Repeat buyers who subscribed? | Only 30% — big upsell opportunity |
| Q12 | Revenue by age group? | 51+ = $399K (highest) |

## Phase 3 — Power BI Dashboard
The dashboard lets non-technical users explore the data using slicers and charts.

Charts included:
- KPI cards (Total Revenue, Avg Purchase, Total Customers, Avg Rating)
- Revenue by Product Category (bar chart)
- Revenue by Gender (donut chart — Male 39.4%, Female 35.5%, Other 25.3%)
- Revenue by Age Group (column chart — 51+ leads at $399K)
- Revenue by Shipping Type (stacked bar — Express vs Standard vs Free)
- Subscription vs Avg Purchase Amount (clustered bar)

Slicers: Category, Gender, Discount Applied, Season, Subscription Status

## Key Business Insights
1. **Electronics dominates** — 48% of revenue. Prioritize stock and promotions here.
2. **Discounts work** — customers with discounts spend $37 more on average.
3. **Subscribers are gold** — they spend 63% more. Grow this segment.
4. **51+ age group is the top spender** — target them in campaigns.
5. **Low subscription conversion** — only 30% of loyal buyers subscribe. Launch a loyalty-to-subscription campaign.

## How to Run
1. Clone this repo
2. Run `eda_cleaning.ipynb` in Jupyter to clean the data
3. Load `customer_clean.csv` into PostgreSQL
4. Run queries in `business_queries.sql`
5. Open `shopping_dashboard.pbix` in Power BI Desktop

## Dataset
- 5,000 records, 17 columns
- Columns include: customer_id, age, gender, item_purchased, category, purchase_amount, review_rating, subscription_status, shipping_type, discount_applied, previous_purchases, and more.
