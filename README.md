# Overview 
Welcome to my analysis of customer shopping trends in the U.S. retail and fashion industry. This project uncovers key patterns in consumer behavior, revenue generation, and demographic preferences by analyzing rich transactional data using **Excel Power Query**, **PivotTables/Charts**, and **Slicers**. 

By exploring metrics such as item popularity, average purchase amounts, regional sales trends, seasonal revenue shifts, and the impact of shipping methods and subscription status, this analysis provides actionable insights to drive targeted marketing, inventory planning, and customer experience improvements.

🔍 Want to see my full data analysis process using Excel? Check it out here: [Customer Shopping Excel Project](https://github.com/junseok-kim-ca/Customer-Shopping-Analysis/blob/main/1.%20Data%20Analysis/1.%20Shopping%20Trends%20Project.xlsx)

# Customer Shopping Trends Dataset

The dataset used for this project is sourced from **[Kaggle](https://www.kaggle.com/datasets/iamsouravbanerjee/customer-shopping-trends-dataset/data)** and simulates real-world customer purchasing behavior in the U.S. retail and fashion industry. It offers a rich view into online and offline shopping habits, making it a valuable resource for analyzing consumer preferences, marketing effectiveness, and revenue optimization strategies.

It includes detailed information on:

- Customer Demographics 
Age, gender, and subscription status, allowing for segmentation and analysis of purchasing patterns across different consumer groups.

- Shopping Behavior 
Data on item categories (e.g., Clothing, Accessories, Footwear), purchase frequency, previous purchases, and shipping types—essential for uncovering loyalty patterns and product preferences.

- Transaction Details 
Purchase amounts in USD, payment options used (e.g., PayPal, Debit, Credit), and seasonal indicators to support revenue analysis, AOV trends, and campaign planning.

- Delivery & Satisfaction 
Shipping methods and review ratings help explore the relationship between delivery performance and customer satisfaction.

- Location Data 
U.S. state information to conduct geographic revenue analysis and identify region-specific trends.

# Tools & Skills   
To ensure effective and insightful analysis, I utilized the following tools alongside key data analysis skills:

1. **Excel 365**: Served as the primary platform for data handling, analysis, and visualization.
2. **Power Query**: Used for performing the ETL process—importing, cleaning, and transforming raw data into an analysis-ready format.
3. **PivotTables & PivotCharts**: Enabled dynamic summarization and visualization of key trends across customer behavior and sales performance.
4. **Slicers**: Provided interactive filtering for deeper exploration of data by dimensions such as Season, Age Group, and Subscription Status.

# Questions To Analyze

### Target Audience  
These questions are tailored for **marketing professionals, business analysts, and e-commerce strategists**, especially those working in the retail and fashion industries in the United States.

By addressing these questions, businesses can build a data-driven strategy that not only enhances marketing tactics but also improves the overall customer experience.

1. What is the most popular Item Category purchased by customers?
2. What is the average Purchase Amount (USD)?
3. Which payment option do customers prefer the most?
4. What is the total revenue segmented by customer demographics and season?
5. Which states contribute the highest total revenue, and how do these trends vary by item category?
6. Do different Shipping Types influence the review ratings? What can this reveal about delivery performance and customer satisfaction?
7. Does Subscription Status influence customers' purchasing behavior and loyalty patterns?

# ETL Process 
The ETL (Extract, Transform, Load) process is a structured approach used in data integration to ensure that data is clean, consistent, and ready for analysis. Using Power Query, I performed the following steps:

## 1. Extract
The first step involved extracting data from `customer_shopping_trends.xlsx` into Power Query. This allowed me to create a query that pulls raw data directly from the source, ensuring accessibility for further transformations.

![image](https://github.com/user-attachments/assets/7c5dbfd0-2cf7-4a5e-b4fe-84f3269ccf24)


## 2. Transform  
Once the data was extracted, I applied multiple transformations in Power Query to clean, standardize, and enhance the dataset, ensuring data accuracy and usability. 

### Data Cleaning and Standardization  
- Checked and updated **data types** for all columns to ensure correctness.  
- Removed **duplicate records** to maintain data integrity.  
- Renamed columns for better clarity:
  - `Location` → **`State (U.S.)`** (to explicitly indicate it represents U.S. states).  
  - `Category` → **`Item Category`** (to specify that it refers to product classifications).  

### Enhancing Data for Analysis  
To improve data insights and usability, I added three new columns in Power Query using the **"Add Column"** feature:  

#### 1. Age Group  
This column segments customers into age brackets to analyze **purchasing trends** across different demographics. It helps in identifying consumer behavior patterns based on age.  

##### M Language Formula:  
```M
= if [Age] >= 0 and [Age] <= 12 then "Child"
  else if [Age] >= 13 and [Age] <= 17 then "Teenager"
  else if [Age] >= 18 and [Age] <= 30 then "Young Adult"
  else if [Age] >= 31 and [Age] <= 45 then "Adult"
  else if [Age] >= 46 and [Age] <= 64 then "Middle Aged"
  else "Senior"
```  

#### 2. Review Rating Category  
This column categorizes **customer review ratings** into five levels: **Very Dissatisfied, Dissatisfied, Acceptable, Satisfied, and Very Satisfied**. This classification simplifies **customer sentiment analysis** and helps in evaluating product/service performance.  

##### M Language Formula:  
```M
if [Review Rating] >= 1 and [Review Rating] < 2 then "Very Dissatisfied"
else if [Review Rating] >= 2 and [Review Rating] < 3 then "Dissatisfied"
else if [Review Rating] >= 3 and [Review Rating] < 4 then "Acceptable"
else if [Review Rating] >= 4 and [Review Rating] < 5 then "Satisfied"
else "Very Satisfied"
```  

#### 3. State Code  
This column converts **full state names** into their respective **two-letter abbreviations** (e.g., *California → CA*). This transformation ensures **data consistency, simplifies geographic analysis**, and makes the dataset compatible with external reporting tools.  

##### M Language Formula:  
```M
= if [#"State (U.S.)"] = null then "Unknown"
  else if [#"State (U.S.)"] = "Alabama" then "AL"
  else if [#"State (U.S.)"] = "Alaska" then "AK"
  else if [#"State (U.S.)"] = "Arizona" then "AZ"
  else if [#"State (U.S.)"] = "Arkansas" then "AR"
  else if [#"State (U.S.)"] = "California" then "CA"
  ...
  else if [#"State (U.S.)"] = "Wyoming" then "WY"
  else "Unknown"
```
#### Applied Steps in Power Query
Throughout the transformation process, multiple steps were applied in Power Query, including data type modifications, column additions, renaming, and reordering for better organization.

![image](https://github.com/user-attachments/assets/be0e20aa-61a8-4187-9f5c-d4a646f17277)



### 3. Load
Once all transformations were completed, I loaded the cleaned and structured query into the Excel workbook. This finalized dataset serves as the foundation for further analysis, allowing for data visualization, reporting, and insights generation.

![image](https://github.com/user-attachments/assets/01314675-d48b-4609-8d35-cbc76d89e12f)


# Analysis
For this project, I crafted each PivotTable and PivotChart to address distinct aspects of Customer Shopping Trends. Here's the approach I took for addressing each question:

### 1. What is the most popular Item Category purchased by customers?
To determine the most popular item category, I used a **PivotTable** and **PivotChart** to summarize the number of purchases by each category. This provided a clear snapshot of customer preferences across all product types.


***PivotTable***


![image](https://github.com/user-attachments/assets/026f9359-ad81-4225-8e95-9931822d3d4e)


***PivotChart***


![image](https://github.com/user-attachments/assets/dc8fbafa-e188-480f-92bc-f3a08ef8f5de)




***Key Findings***
1. **Clothing** leads the market with a **45% share** (about 2,000 purchases), indicating it’s the top-selling category.

2. The significant gap between **Clothing (45%)** and the lower categories such as **Footwear (15%)** and **Outerwear (8%)** suggests a strong consumer preference for apparel. 


***Insights***
1. **Implement Resource Allocation Strategy**: The strong consumer preference for **Clothing** may justify increased inventory and promotional efforts in this category, while also exploring **cross-selling opportunities** with lower-performing segments.


### 2. What is the average Purchase Amount (USD)?
To calculate the average amount customers spend per purchase, I used a **PivotTable** to find the mean of the Purchase Amount (USD) field. This provided a quick overview of typical transaction values.

***PivotTable***

![image](https://github.com/user-attachments/assets/1fa8d6b9-1abe-4e8e-af92-b7abccc7bea3)


***Key Findings***
1. At **$59.76** per purchase, customers typically spend around $60 each time they buy.

***Insights***
1. Compared to the US benchmark from [CEIC Data](https://www.ceicdata.com/en/united-states/ecommerce-transactions-by-category/ecommerce-transactions-average-order-value-aov)
where the average order value is around $159 (March 2025) our AOV of $59 is significantly lower. This indicates an opportunity to boost order values through strategies like **upselling, cross-selling, or bundling products**.


### 3. Which payment option do customers prefer the most?
To identify the most popular payment method, I used a **PivotTable** and **PivotChart** to aggregate transaction counts by payment option. This allowed me to quickly see which payment methods are most frequently used by customers.

***PivotTable***

![image](https://github.com/user-attachments/assets/3f9d0f4d-5953-46e8-8df7-3fa9beea5c19)


***PivotChart***

![image](https://github.com/user-attachments/assets/4a6d1566-105e-42c2-acd7-b8a99780b744)




***Key Findings***
1. **PayPal** is the most popular payment method with 677 transactions, indicating its strong presence in the shopping behavior.
2. The proportions of transactions are relatively similar, suggesting **no overwhelming customer preference** for any single alternative.
      

***Insights***
1. Since no method overwhelmingly dominates, there’s a chance to **enhance user experience** across all payment types by simplifying checkout processes, introducing **loyalty programs**, or **reducing fees** could further boost overall adoption.


### 4. What is the total revenue segmented by customer demographics, and season?
Customer demographics serve as essential classifications for targeted marketing and product development. In this analysis, I segmented total revenue by `Age Group` and `Gender`, and further broke it down by `Season` to understand how purchasing patterns vary over time.

***PivotTable***

![image](https://github.com/user-attachments/assets/59f52969-a12b-4d00-89ee-26187c56fbe9)


***PivotChart***

![image](https://github.com/user-attachments/assets/03a8bac2-42c1-4121-8caa-fe92f491f573)



***Slicer***

![image](https://github.com/user-attachments/assets/384ad965-0dbc-488d-9f39-dfdbef8adeb3)




***Key Findings***
1. **Middle-aged customers** generate the **highest total revenue ($85,381)**, well above other age groups.  

2. In every age group, **males** consistently outspend females by **roughly 2x or more** 

3. **Fall** shows the **highest overall revenue ($60,018)**, with Spring ($58,679) and Winter ($58,607) close behind. **Summer** is slightly **lower at $55,777**.

4. Age-Specific Seasonal Peaks:  
   - ***Young Adult & Adult***: **Winter** is the highest-grossing season.  
   - ***Middle Aged***: **Fall** slightly leads Summer and Spring.  
   - ***Senior***: **Spring** is the top season, though total revenue remains relatively low compared to other groups.
      

***Insights***
1. **Middle-Aged Males as a Core Revenue Driver**:
With the highest spending ($57,726) within the most profitable age group, **Middle-Aged Males** stand out as a crucial demographic. **Tailored product lines** or **targeted marketing** could further boost revenue from this segment.

2. **Seasonal Variations Demand Tailored Promotions**:
Each age group peaks in a different season (e.g., Young Adult in Winter, Senior in Spring), suggesting that **season-specific promotions** or **campaigns** might be more effective than a one-size-fits-all approach.

3. **Opportunities to Engage Female Customers**:
Males outspend females across all age groups. Investigating **female spending is lower**, whether due to product offerings, marketing messages, or other factors—could reveal potential strategies to increase sales.



### 5. Which states contribute the highest total revenue, and how do these trends vary by item category?
Understanding regional performance is vital for tailoring marketing strategies and optimizing product distribution. In this analysis, I segmented total revenue by `State` and further broke it down by `Item Category` to uncover **geographic trends** and **consumer preferences**.

***Table (From PivotTable)***

![image](https://github.com/user-attachments/assets/77f8ed3d-deb3-43a0-b5dc-2bea41e7b0e1)


***Map Chart***

![image](https://github.com/user-attachments/assets/e211906b-7e43-469a-9fd4-92d3156b88c0)


***Slicer***

![image](https://github.com/user-attachments/assets/d17b8cfc-7d25-4b1a-9a63-49ece40baf1c)


***Key Findings***
1. **Overall Revenue (All categories):**
- ***Top States***: Montana (MT), Illinois (IL), California (CA), Idaho (ID), and Nevada (NV) contribute the highest total revenues, each above **2.3%** of overall revenue.
- ***Lowest Revenue State***: Kansas (KS) generates the least revenue, contributing just **1.47%** of total.

2. **Accessories:**
- ***Top States***: Nebraska (NE), Nevada (NV), Mississippi (MS), West Virginia (WV), and Kentucky (KY) have the highest revenue percentages, indicating these states prefer accessory products significantly.
- ***Lowest State***: Maine (ME) has the lowest accessory revenue contribution (**1.25%**).

3. **Clothing:**
- ***Top States***: Montana (MT) and California (CA) generate the highest revenue percentages, indicating a strong preference for clothing items.
- ***Lowest State***: New Jersey (NJ) has the lowest clothing revenue share (**1.25%**).

4. **Footwear:**
- ***Strongest Preference***: Ohio (OH) leads significantly in footwear (**3.66%**), highlighting a strong local demand.
- ***Least Interest***: Kentucky (KY) shows minimal interest (**0.62%**), the lowest footwear contribution.

5. **Outerwear:**
- ***Top Performer***: North Dakota (ND) generates the highest outerwear revenue share (**4.90%**), which might indicate high seasonal demand due to climate.
- ***Lowest Contributor***: Georgia (GA) has the lowest outerwear share (**0.50%**), implying limited local interest or need.



***Insights***
1. **Climate Drives Outerwear Revenue**:  
With **North Dakota (4.90%)** significantly leading outerwear sales, regional climates clearly influence purchasing behavior. Tailoring outerwear collections and promotional campaigns specifically for colder states could maximize sales and customer satisfaction.

2. **Localized Footwear Preferences Present Opportunities**:  
**Ohio (3.66%)** shows a strong preference for footwear, whereas **Kentucky (0.62%)** remains notably low. Investigating local style preferences, competition, and introducing targeted footwear lines could boost performance in underperforming states.

3. **Accessories as Key Cross-Selling Opportunities**:  
States such as **Nebraska (2.89%) and Nevada (2.87%)** lead accessory sales, signaling their potential as impulse or complementary purchases. Leveraging bundled deals or strategic in-store and online placements can enhance average order value.

4. **Clothing Demand Varies by Region, Necessitating Targeted Strategies**:  
Strong clothing sales in **Montana (2.65%) and California (2.63%)** contrast sharply with **New Jersey’s low performance (1.25%)**. Understanding regional fashion preferences and implementing tailored marketing and merchandising strategies could optimize apparel revenue across diverse markets.



### 6. Do different Shipping Types influence the review ratings? What can this reveal about delivery performance and customer satisfaction?

To explore the impact of delivery methods on customer satisfaction, I grouped review ratings by Shipping Type. This approach enabled me to calculate the percentage distribution of each review category for every shipping option, providing insights into how delivery performance correlates with customer sentiment.

***PivotTable***

![image](https://github.com/user-attachments/assets/e5ea2c1a-ff3a-4386-bcbf-0982b103071a)


***PivotChart***

![image](https://github.com/user-attachments/assets/4cf82d73-7d79-46d5-ae4e-995916c0a6fb)


***Key Findings***
1. Standard Shipping achieves the highest percentage of Satisfied customers (45.41%) and also has the lowest level of Dissatisfaction (15.60%).

2. Store Pickup has notably the highest percentage of Dissatisfied customers (21.23%), significantly above all other shipping methods.

3. While premium services like Express (40.71% satisfied) and Next Day Air (40.12% satisfied) show relatively balanced performance, their percentage of Very Satisfied customers remains low (under 2%).

4. Free Shipping has the highest percentage of Acceptable ratings (43.85%), suggesting customers often have neutral or average experiences.


***Insights***

1. **Promoting Reliable Standard Shipping Could Boost Brand Reputation**:  
Given its proven reliability, actively highlighting Standard Shipping in promotional campaigns and customer communications could strengthen overall brand image and attract more customers.

2. **Improving Store Pickup Experience Could Increase Customer Retention**:  
Enhancing the store pickup process such as reducing wait times, better stock management, or improving customer service can directly address high dissatisfaction rates and build customer loyalty.

3. **Elevating Free Shipping Experiences Presents Competitive Advantage**:  
Since Free Shipping currently delivers mostly average satisfaction, introducing minor enhancements like improved tracking, clearer communication, or slightly faster service could significantly differentiate the company from competitors.

4. **Premium Delivery Enhancements Offer Upsell Opportunities**:  
There are still unexplored benefits in offering premium shipping options. Providing additional value—like personalized delivery notifications, priority handling, or superior packaging—could elevate satisfaction, justify higher fees, and encourage customers to upgrade shipping services.



### 7. Does Subscription Status influence customers' purchasing behavior and loyalty patterns?

To understand customer purchasing and loyalty patterns, I analyzed the data using the columns `Previous Purchases` and `Frequency of Purchases`. This approach allowed me to compare how subscribers and non-subscribers differ in their repeat buying behavior across various purchase frequencies.

***PivotTable***

![image](https://github.com/user-attachments/assets/0ac55412-7b7d-4a88-93e3-ecd7c66d2c9c)


***PivotChart***

![image](https://github.com/user-attachments/assets/f510cda8-5743-41eb-a364-863bb621ba88)



***Key Findings***

1. **Subscribers consistently show higher customer loyalty**, with a higher overall average of previous purchases (**26.1**) compared to non-subscribers (**25.1**).

2. **Bi-Weekly purchasers who subscribe are the most loyal**, showing the highest average previous purchases (**27.1**) among all groups.

3. **Subscribers outperform non-subscribers across nearly every frequency**, especially in **Every 3 Months** (26.7 vs. 24.3) and **Bi-Weekly** (27.1 vs. 24.0), highlighting stronger retention among regular subscribers.

4. **Non-subscribers only surpass subscribers in one frequency, **Quarterly purchases** with a slightly higher loyalty average (**27.2** vs. 25.7), which may indicate that occasional buyers don’t see value in subscribing.
      

***Insights***

1. **Subscription Programs Foster Higher Customer Loyalty Across Most Frequencies**:  
Since subscribers consistently show higher average previous purchases, reinforcing subscription benefits—like exclusive deals or early access—could further drive repeat buying and deepen customer engagement.

2. **Bi-Weekly Subscribers Show the Strongest Loyalty**:  
With the highest average previous purchases (27.1), this segment represents a high-value, active customer group. Consider targeted loyalty rewards or personalized offers to increase retention and reward consistent behavior.

3. **Quarterly Buyers May Favor a Non-Commitment Shopping Style**:  
Since non-subscribers in the quarterly group show higher loyalty, it indicates a preference for flexibility over long-term commitments. Providing occasional benefits—like limited-time offers or optional loyalty perks—without requiring full subscription enrollment could better align with their shopping behavior.

# Dashboard

![converted_optimized](https://github.com/user-attachments/assets/20478811-61e1-4f12-a283-b2a61e383fb9)




# What I learned

1. **ETL Workflow: Data Extraction, Transformation & Loading**:
I streamlined raw Excel data in Power Query by removing duplicates, fixing data types, and adding fields like Age Group, Review Rating Category, and State Code. This improved segmentation and ensured high-quality insights. 

2. **Insight-Driven Analysis Unlocks Business Value**: 
Using PivotTables, PivotCharts, and Slicers, I visualized key patterns in customer behavior, regional trends, and operational performance. These visual tools made complex data easier to interpret and revealed insights that informed product strategies, targeted marketing, and service improvements.

3. **Strategic Questioning Enhances Analytical Impact**:
Starting with clear, business-focused questions ensured that the analysis stayed aligned with organizational goals. This approach helped uncover actionable insights that support better decision-making and strategic planning.


# Conclusion 
This project provided a comprehensive, data-driven exploration of customer shopping trends in the U.S. retail and fashion sectors. By applying a structured ETL process via leveraging Power Query, I was able to clean, transform, and enrich the dataset to prepare it for deeper analysis.

Through visual analytics using PivotTables, PivotCharts, and Slicers, I uncovered meaningful insights into customer preferences, regional sales patterns, shipping satisfaction, and subscriber loyalty behaviors.

Most importantly, this experience reinforced the importance of starting with clear, business-aligned questions. Doing so ensured that the analysis stayed focused, relevant, and delivered strategic value—empowering better decision-making and actionable outcomes.

