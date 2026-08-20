# Customer-Shopping-Behavior-Analysis
Customer Shopping Behavior Analysis

An end-to-end data analytics project that explores 3,900 retail transactions to uncover customer spending patterns, product trends, and loyalty drivers — and turns those findings into a business-ready dashboard and report.

Overview

A retail company wanted to understand what drives customer purchasing decisions and repeat business — factors like discounts, reviews, seasonality, and payment preferences — in order to improve sales, engagement, and long-term loyalty.

This project answers that question end to end:

Python for data cleaning, transformation, and feature engineering
SQL (PostgreSQL) for structured business-question analysis
Power BI for an interactive dashboard
Gamma for the stakeholder presentation
A written report summarizing findings and recommendations
Dataset
Size: 3,900 customer transactions, 18 columns
Fields: customer demographics (age, gender, location, subscription status), purchase details (item, category, amount, season, size, color), and shopping behavior (discount applied, previous purchases, purchase frequency, review rating, shipping type, payment method)
Data quality: 37 missing values in Review Rating, imputed using the median rating per product category
Tools & Technologies
Category	Tools
Data Cleaning & EDA	Python (pandas)
Database / Querying	PostgreSQL (also compatible with MySQL / SQL Server)
Visualization	Power BI
Presentation	Gamma
Report	Word / PDF
Project Steps
Data Loading — Imported the raw dataset into a pandas DataFrame.
Exploratory Data Analysis — Used df.info() and df.describe() to understand structure, types, and distributions.
Data Cleaning
Checked for and imputed missing values (Review Rating filled with category-level median).
Standardized column names to snake_case.
Feature Engineering
Created age_group by binning customer ages into quartile-based groups (Young Adult, Adult, Middle-aged, Senior).
Created purchase_frequency_days by mapping purchase frequency labels (e.g., Weekly, Monthly) to numeric day values.
Checked discount_applied against promo_code_used for redundancy and dropped the duplicate column.
Database Integration — Loaded the cleaned dataset into PostgreSQL using SQLAlchemy for structured querying.
SQL Analysis — Wrote 10 business-focused queries covering revenue by gender, discount behavior, top-rated and top-selling products, shipping comparisons, subscriber value, customer segmentation, repeat-buyer trends, and revenue by age group.
Dashboard Design — Built an interactive Power BI dashboard with filters for subscription status, gender, category, and shipping type.
Reporting & Presentation — Summarized findings in a written report and built a stakeholder-facing slide deck in Gamma.
Dashboard

The Power BI dashboard (customer_behavior_dashboard.pbix) includes:

Key metrics: number of customers, average purchase amount, average review rating
Subscriber vs. non-subscriber breakdown
Revenue and sales by product category
Revenue and sales by age group
Interactive filters: subscription status, gender, category, shipping type
Key Results
Revenue by gender: Male customers generated significantly higher total revenue than female customers.
Discount behavior: 839 customers used a discount while still spending above the average purchase amount.
Top-rated products: Gloves, Sandals, Boots, Hats, and Skirts had the highest average review ratings.
Shipping: Express shipping customers spent slightly more on average ($60.48) than Standard shipping customers ($58.46).
Subscribers vs. non-subscribers: Non-subscribers generated more total revenue overall, but subscribers were a smaller, high-value segment worth nurturing.
Discount-dependent products: Hats, Sneakers, Coats, Sweaters, and Pants had the highest share of discounted purchases.
Customer segments: 3,116 Loyal, 701 Returning, and 83 New customers — showing a strong existing base but a need for new-customer acquisition.
Repeat buyers: Customers with more than 5 previous purchases were not strongly more likely to subscribe, suggesting subscription and loyalty are currently disconnected.
Revenue by age group: Young Adults contributed the most revenue, followed closely by Middle-aged, Adult, and Senior groups.
Business Recommendations
Promote subscription benefits to convert high-frequency shoppers into subscribers.
Launch loyalty programs to move Returning customers into the Loyal segment.
Reassess discount policy on high-discount-dependency products to protect margins.
Feature top-rated and best-selling products more prominently in marketing.
Target campaigns toward high-revenue age groups and Express-shipping users.
How to Run
1. Clone the repository
bash
git clone <your-repo-url>
cd customer-shopping-behavior-analysis
2. Set up Python environment
bash
pip install pandas sqlalchemy psycopg2-binary
3. Run the data cleaning notebook

Open data_analysis_project.ipynb in Jupyter and run all cells to load, clean, and export the dataset.

4. Load data into your SQL database

Update the database credentials in the notebook's SQLAlchemy connection step, then run it to push the cleaned data into PostgreSQL (or adapt the connection string for MySQL / SQL Server).

5. Run the SQL analysis

Execute the queries in customer_behavior_end_to_end_Data_Analysis_PostgreSQL_project.sql against your database to reproduce the business insights.

6. Open the dashboard

Open customer_behavior_dashboard.pbix in Power BI Desktop and refresh the data connection to your database (or use the saved dataset as-is).

7. View the report and presentation
Report: Customer_Shopping_Behavior_Analysis.pdf
Presentation: Customer-Shopping-Behavior-Analysis.pptx (built with Gamma)
Repository Structure
├── data_analysis_project.ipynb                                  # Python: cleaning & EDA
├── customer_behavior_end_to_end_Data_Analysis_PostgreSQL_project.sql   # SQL: business queries
├── customer_behavior_dashboard.pbix                              # Power BI dashboard
├── Customer_Shopping_Behavior_Analysis.pdf                        # Project report
├── Customer-Shopping-Behavior-Analysis.pptx                       # Stakeholder presentation
└── README.md                                                      # Project documentation
Content
data analysis project.ipynb

IPYNB

customer_behavior_dashboard.pbix

PBIX

Customer-Shopping-Behavior-Analysis.pptx

PPTX

PDF

PDF

customer_behavior_end_to_end_Data_Analysis_PostgreSQL_project.sql

89 lines

SQL
