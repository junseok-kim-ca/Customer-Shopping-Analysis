# Customer-Shopping-Analysis

https://www.kaggle.com/datasets/iamsouravbanerjee/customer-shopping-trends-dataset/data

# Questions 

1. What is the most common item purchased?
2. What is the most common payment method used by customers?
3. What is the most common season for purchases?

* KPI
4. What is our total revenue segmented by customer demographics, and season?
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
  else if [Age] >= 13 and [Age] <= 18 then "Teenager"
  else if [Age] >= 19 and [Age] <= 30 then "Young Adult"
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









