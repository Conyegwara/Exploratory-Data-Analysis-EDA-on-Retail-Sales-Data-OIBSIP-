# Exploratory-Data-Analysis-EDA-on-Retail-Sales-Data-OIBSIP-
### Description
In this project, I will work with a dataset containing information about retail sales. The goal is to Gain hands-on experience in data cleaning, develop skills in interpreting descriptive statistics and time series analysis and data visualization for effective communication of insights to uncover patterns, trends, and insights that can help the retail business make informed decisions.

### Executive Summary
This report analyzes retail sales trends, customer behavior, and product performance to provide actionable insights for optimizing marketing, inventory management, and customer engagement.
#### Key Findings
- **Sales Trends**:
1. Peak sales in May 2023 ($53,150) suggest seasonal demand, while September 2023 ($23,620) saw the lowest sales—indicating a slow period or supply issues.
2. A major drop in January 2024 ($1,530) may indicate incomplete data or seasonal decline.
- **Descriptive Statistics:**
1. Average transaction value: $456, with a median of $135, indicating a right-skewed distribution.
2. Mode: $50, showing frequent small-value transactions.
3. High variability (Standard deviation: $560) suggests diverse customer spending habits.
- **Customer & Product Analysis:**
1. 25-54 age group drives the highest revenue (~$97K per segment).
2. Zero purchases from the 65+ age group, presenting an untapped market.
3. Female customers spend slightly more than males ($232K vs. $223K).
4. Electronics ($156,905) & Clothing ($155,580) are top-selling categories, followed by Beauty products ($143,515).
- Recommendations
1. Boost sales during slow months (March, September) through targeted promotions and discounts.
2. Focus marketing on the 25-54 age group & develop senior-friendly offers.
3. Prioritize Electronics & Clothing while expanding premium Beauty products.

### Project Obejective
The purpose of this report is to understand sales trends, customer purchasing behavior, and product performance as it is crucial for making informed business decisions. It also presents an in-depth analysis of the sales dataset covering key insights into sales trends, customer demographics, product sales performance, statistical summaries and provide recommendation for improving revenue, customer engagement and improved inventory efficiency.
##### Project key concepts
- Time Series Analysis (Sales Trends Over Time)
- Customer Demographics & Purchasing Behavior
- Product Performance Analysis
- Descriptive Statistics (Mean, Median, Mode, Standard Deviation, etc.)
- Actionable Recommendations
##### project challenges/problems
- Calculate basic Descriptive statistics (mean, media, mode, standard deviation).
- How do monthly sales trends fluctuate throughout the year?
- Do sales tend to increase on specific days of the week (e.g., weekends vs. weekdays)?
- Is there a general upward or downward trend in sales over time?
- Are there spikes or dips in sales that correlate with promotions or external events?
- Which gender contributes the most to total sales?
- What age group spends the most money?
- Are there certain customer groups that should be targeted more with promotions?
- What is the top-selling product categories?
- Which products generate the highest total revenue?
- Do certain products sell better in specific months (seasonality analysis)?

### Data Overview
This dataset is a snapshot of a fictional retail landscape, capturing essential attributes that drive retail operations and customer interactions. It includes key details such as Transaction ID, Date, Customer ID, Gender, Age, Product Category, Quantity, Price per Unit, and Total Amount. These attributes enable a multifaceted exploration of sales trends, demographic influences, and purchasing behaviors.
#### Data source & cleaning
######  Data source
[Kaggle retail sales dataset ](https://www.kaggle.com/datasets/mohammadtalib786/retail-sales-dataset)

- Data cleaning: Excel worksheet was used to clean the data, remove duplicate transactions, handled missing values, standardized date formats.
- Segmentation: sales analyzed by product categories, age group, sales trend over time, gender and Date
- The date column was converted to proper datetime format.
- New columns of Day, Month and year was created to achieve accurate insight on the trend of sales over time. Using the formular below:
      `       =TEXT(B2,"dddd"), =TEXT(B2,"mmmm"), =TEXT(B2,"yyyy")





