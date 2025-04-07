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
##### Key Questions
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
###### Data used
- <a href="https://github.com/Conyegwara/Exploratory-Data-Analysis-EDA-on-Retail-Sales-Data-OIBSIP-/blob/main/Retail%20sales%20dataset.xlsx">Dataset</a>
  
- Data cleaning: Excel worksheet was used to clean the data, remove duplicate transactions, handled missing values, standardized date formats.
- Segmentation: sales analyzed by product categories, age group, sales trend over time, gender and Date
- The date column was converted to proper datetime format.
- New columns of Day, Month and year was created to achieve accurate insight on the trend of sales over time. Using the formular below:
  $=TEXT(B2,"dddd"), =TEXT(B2,"mmmm"), =TEXT(B2,"yyyy")$
  
#### Analytical tools & Techniques
1. Data cleaning: Microsoft Excel and Power query(power BI)
2. Data modelling: power BI, data model and DAX measures.
    - Define relationship between date table
    - Create calculated column for key metrics and sub categories(age group, descriptive calculation, total sales, customer, amount and average spending)
3. Dashboard and data visualization: Power bi and visualization features.
4. Method used in this analysis was (descriptive statistics, trend analysis, time series analysis, customer & product analysis)

### Data Analysis & Key Insight
The data was imported into power BI for further refinement, in-depth analysis and visualization to extract meaningful insights.
- Power BI Visual Used:Card KPI

KPI cards total was created using the following DAX measures below:
- Total Customers (Total_Customers = $DISTINCTCOUNT('sales report'[Customer ID]$)
- Total Quantity (Total_Quantity = $SUM('sales report'[Quantity]$)
- Total Sales (Total_Sales = $SUM('sales report'[Total Amount]$)
- Average spending (Avg_Spending = $AVERAGE('sales report'[Total Amount]$)
  
#### Time series Analysis: sales trend over time
- Aggregate monthly sales 
   - Sales data was grouped by month and moving average 7 days.
   -  Slicers for Year, Quarterly & Month were added for deeper analysis.
   -  A 7-day Moving Average was applied to smooth fluctuations
   -  The Dax measure utilized to calculate the 7-day  moving average was:
   -  Moving_Avg_7Days =  $CALCULATE(AVERAGE('sales report'[Total Amount]),DATESINPERIOD('sales report'[Date ], MAX('sales report'[Date ]), -7, DAY)  )$

- key Insight 
  - January & February had strong sales, followed by a drop in March.
  - Sales peaked in May, possibly due to seasonal demand or promotions. 
  - Weekends drive higher sales, as indicated by the Day-wise Analysis.
  - Seasonal patterns are visible, requiring optimized stock and marketing plans

- power BI visual used: line chart was used to visualize sales trends over time. Where date(months) was in the x axis and sum of total amount was in the y axis with moving average 7 days in the secondary y-axis
- Slicer – months, year, quarter, gender, day, product category and customer ID
    
#### Customer and Product Analysis
- Customer Demographics Analysis
  - Sales were analyzed based on Gender and the top 10 customers by revenue.
- key Insight 
  - Females contributed slightly more sales revenue than males.
  
- Power BI Visual Used: Stacked bar chart and Donut chart

#### Product Analysis with Age-Based Analysis (Best-Selling Products & Categories)
- Sales was analyzed based on age group and product category to know the purchasing power of each age group and their preferred product.
- DAX Formula for Age Grouping:
- DAX
Age_Group = 
    $IF(
        'sales report'[Age] < 25, "Under 25",
        IF('sales report'[Age] < 40, "25-39",
        IF('sales report'[Age] < 60, "40-59", "60+"))
    )$

- Key Insights:
  - Electronics and Clothing categories contribute the highest revenue.
  - Beauty products have lower revenue but a high transaction count.
  - Customers aged 25-39 are the most active buyers.
  - Younger customers tend to buy lower-priced products.
  - Older customers purchase premium-priced products more frequently.
  - The 65+ age group had no recorded sales, indicating a potential untapped market

-  Power BI Visual Used: Tree map

#### Product Sales Over Time
sales was analyzed using the product catogories over time.    
- Key Insights:
  - Seasonal demand affects product sales.
  - Stock levels should be optimized based on sales seasonality.

- Power BI Visual Used: Stacked Area Chart

### Descriptive Statistics(summary of sales data)
To understand the dataset better, the following key statistics were calculated:
- Mean:  (Average Sales per Transaction) (Mean_Total_Sales = $AVERAGE ('sales report'[Total Amount])$
- Median (Middle Value of Sales) (Median_Total_Sales = $MEDIAN ('sales report'[Total Amount])$
- Mode (Most Frequently Occurring Sales Value)( Mode_Total_Sales = VAR ModeValue SELECTCOLUMNS(TOPN(1, SUMMARIZE('sales report', 'sales report'[Total Amount], "Count", COUNT('sales report'[Total Amount])),   [Count], DESC  ), "MostCommon", 'sales report'[Total Amount]) RETURN MAXX(ModeValue, [MostCommon]$)
- Standard Deviation (Variability in Sales Amounts): Std_Dev_Total_Sales = $STDEV.P('sales report'[Total Amount])

- Key Insights:
  - The mean ($456) is significantly higher than the median ($135), indicating right-skewed data (some large purchases raise the average).
  - Mode is just $50, meaning many small transactions occur.
  - High standard deviation ($560) suggests a wide range of transaction values.
  - Wide variation in sales amounts suggests different customer spending patterns
  - Identifying the mode helps find common transaction values

- Power BI Visual Used: Table visual

### Actionable Recommendations
Based on the EDA, the following business recommendations are suggested:
- Increase High-Value Customer Engagement
  - Insight: High-spending customers contribute significantly to revenue.
  - Recommendation: Offer loyalty programs & personalized discounts.
  
- Sales Growth Strategies
  - Seasonal Promotions: Address low sales periods (e.g., March) with special offers.
  - Capitalize on Peak Months: Leverage May’s strong sales trend with marketing campaigns.
  - Insight: Certain weekdays show lower sales activity.
  - Recommendation: Offer weekday-exclusive promotions to boost transactions.

- Customer Engagement & Retention
  - Focus on 25-54 Age Group: This group drives the majority of sales.
  - Expand 65+ Market: Develop senior-friendly products and targeted promotions.
  - Increase Female-Focused Campaigns: Since women contribute more to sales, consider gender-based promotions.

- Product & Inventory Optimization
  - Prioritize Electronics & Clothing: Ensure enough stock to meet demand.
  - Expand Beauty Product Line: Explore premium beauty products or introduce bundles.

- Improve Marketing Strategy Using Customer Demographics
  - Insight: Certain age groups and genders prefer specific products.
  - Recommendation: Target ads & promotions based on customer segment insights.

### Conclusion 
This analysis provided key insights into sales trends, customer demographics, and product performance. The findings highlight opportunities for targeted marketing, inventory planning, and customer engagement strategies. By implementing these recommendations, businesses can increase revenue, enhance customer engagement, and improve inventory efficiency, leading to sustained growth and profitability.






