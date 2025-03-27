# Overview

https://www.kaggle.com/datasets/iamsouravbanerjee/customer-shopping-trends-dataset/data

# Questions 

1. What is the most popular Item Category purchased by customers?
2. What is the average Purchase Amount (USD)?
3. Which payment option do customers prefer the most?


* KPI
4. What is the total revenue segmented by customer demographics, and season?
5. Which item category drives the most revenue in each State?
  

* Correlation Question & Hard Questions 
6. How do customer demographics influence payment preferences and buying frequency?
7. Which subscription status group yields the highest purchase amount, and do they exhibit different frequency of purchases or previous purchases patterns compared to non-subscribers?
8. Which states produce the highest total purchase amount and best review ratings?

  


# ETL Process 
The ETL (Extract, Transform, Load) process is a structured approach used in data integration to ensure that data is clean, consistent, and ready for analysis. Using Power Query, I performed the following steps:

## 1. Extract
The first step involved extracting data from `customer_shopping_trends.xlsx` into Power Query. This allowed me to create a query that pulls raw data directly from the source, ensuring accessibility for further transformations.

![image](https://github.com/user-attachments/assets/7c5dbfd0-2cf7-4a5e-b4fe-84f3269ccf24)


---

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
...

### 1. What is the most popular Item Category purchased by customers?

To understand overall purchase behavior, I followed these steps:
- Data Organization:  
  - Used a **PivotTable** to group purchases by Item category, calculating raw counts and percentages.

- Visualization:  
  - Created a combo PivotChart with clustered columns for purchase counts on the primary axis and a line with markers for percentages on the secondary axis.

- Customization:  
  - Titled the chart “Product Purchase Frequency,” labeled the axes, removed gridlines, and changed the markers to diamonds.


![image](https://github.com/user-attachments/assets/62bd6c2d-ff22-46fa-9ed2-c33d2577850b)


***Key Findings***
1. Clothing leads the market with a 45% share (about 2,000 purchases), indicating it’s the top-selling category.

2. The significant gap between Clothing (45%) and the lower categories such as Footwear (15%) and Outerwear (8%) suggests a strong consumer preference for apparel. 


***Insights***
1. **Implement Resource Allocation Strategy**: The strong consumer preference for Clothing may justify increased inventory and promotional efforts in this category, while also exploring cross-selling opportunities with lower-performing segments.


### 2. What is the average Purchase Amount (USD)?
I implemented PivotTable in order to find the averae purchase amount of shopping items. I put Purchase Amount (USD) column into Values and change average in the value filed setting. 

![image](https://github.com/user-attachments/assets/56d58e97-e311-4834-9000-d27aa3e648e4)

***Key Findings***
1. At $59.76 per purchase, customers typically spend around $60 each time they buy.

***Insights***
1. Compared to the US benchmark from [CEIC Data](https://www.ceicdata.com/en/united-states/ecommerce-transactions-by-category/ecommerce-transactions-average-order-value-aov)
—where the average order value is around $159 (March 2025)—our AOV of $59 is significantly lower. This indicates an opportunity to boost order values through strategies like upselling, cross-selling, or bundling products.

### 3. Which payment option do customers prefer the most?

To assess the distribution of payment methods, I followed these steps:
- Data Organization:  
  Grouped transactions by Payment Method using a PivotTable to compute total counts and percentages.

- Visualization:  
  Created a combo PivotChart with clustered columns for Payment Count on the primary axis and a line with markers for % of Payment on the secondary axis.

- Customization:  
  Named the chart “Frequency of Payment,” added axis labels, removed gridlines, and changed markers to diamonds.

![image](https://github.com/user-attachments/assets/030a7314-a196-41e4-a6a1-ecbf1ac0e79f)



***Key Findings***
1. PayPal is the most popular payment method with 677 transactions, indicating its strong presence in the shopping behavior.
2. The proportions of transactions are relatively similar, suggesting no overwhelming customer preference for any single alternative.
      

***Insights***
1. Since no method overwhelmingly dominates, there’s a chance to enhance user experience across all payment types by simplifying checkout processes, introducing loyalty programs, or reducing fees could further boost overall adoption.


### 4. What is the total revenue segmented by customer demographics, and season?

Customer demographics refer to classifications of consumer groups that businesses use for strategic purposes, such as targeted marketing and product development. In this dataset, the primary demographic variables are `Age Group` and `Gender`.

### 5. Which states contribute the highest total revenue, and how do these trends vary by item category?

### 6. Do different Shipping Types influence the review ratings? What can this reveal about delivery performance and customer satisfaction?

### 7. Which subscription status group yields the highest purchase amount, and do they exhibit different frequency of purchases or previous purchases patterns compared to non-subscribers?

