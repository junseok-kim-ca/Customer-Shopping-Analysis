# Customer-Shopping-Analysis

https://www.kaggle.com/datasets/iamsouravbanerjee/customer-shopping-trends-dataset/data

# ETL Process 


## 1. Extract
First of all, I used Power Query to extract data from `customer_shopping_trends.xlsx` and create a query

![image](https://github.com/user-attachments/assets/7c5dbfd0-2cf7-4a5e-b4fe-84f3269ccf24)

Here’s a refined and well-structured version of your **Power Query Project – Transform Section** with improved readability and clarity:  

---

## 2. Transform  

As part of the data transformation process, I performed several key steps to ensure data accuracy, consistency, and enhanced analytical capabilities.  

### Data Cleaning and Standardization  
- Checked and updated **data types** for all columns to ensure correctness.  
- Removed **duplicate records** to maintain data integrity.  
- Renamed columns for better clarity:
  - `Location` → **`State (U.S.)`** (to explicitly indicate it represents U.S. states).  
  - `Category` → **`Item Category`** (to specify that it refers to product classifications).  

### Enhancing Data for Analysis  
To improve data insights and usability, I added three new columns in Power Query using the **"Add Column"** feature:  

#### **1. Age Group**  
This column segments customers into age brackets to analyze **purchasing trends** across different demographics. It helps in identifying consumer behavior patterns based on age.  

##### **M Language Formula:**  
```M
= if [Age] >= 0 and [Age] <= 12 then "Child"
  else if [Age] >= 13 and [Age] <= 18 then "Teenager"
  else if [Age] >= 19 and [Age] <= 30 then "Young Adult"
  else if [Age] >= 31 and [Age] <= 45 then "Adult"
  else if [Age] >= 46 and [Age] <= 64 then "Middle Aged"
  else "Senior"
```  

#### **2. Review Rating Category**  
This column categorizes **customer review ratings** into five levels: **Very Dissatisfied, Dissatisfied, Acceptable, Satisfied, and Very Satisfied**. This classification simplifies **customer sentiment analysis** and helps in evaluating product/service performance.  

##### **M Language Formula:**  
```M
if [Review Rating] >= 1 and [Review Rating] < 2 then "Very Dissatisfied"
else if [Review Rating] >= 2 and [Review Rating] < 3 then "Dissatisfied"
else if [Review Rating] >= 3 and [Review Rating] < 4 then "Acceptable"
else if [Review Rating] >= 4 and [Review Rating] < 5 then "Satisfied"
else "Very Satisfied"
```  

#### **3. State Code**  
This column converts **full state names** into their respective **two-letter abbreviations** (e.g., *California → CA*). This transformation ensures **data consistency, simplifies geographic analysis**, and makes the dataset compatible with external reporting tools.  

##### **M Language Formula:**  
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

### 3. Load


## Transform


## Load





