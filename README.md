# Customer-Shopping-Analysis

https://www.kaggle.com/datasets/iamsouravbanerjee/customer-shopping-trends-dataset/data

## ETL Process 


### 1. Extract
First of all, I used Power Query to extract data from `customer_shopping_trends.xlsx` and create a query

![image](https://github.com/user-attachments/assets/7c5dbfd0-2cf7-4a5e-b4fe-84f3269ccf24)

### 2. Transform

I checked and changed data types of each columns and I removed duplicates. Also, I rename the columns: Location to State (U.S.) and Category to Item Category in order to ...

To enhance data analysis, I added 3 new columns in Power Query: `Age Group`, `Review Rating Category`, and `State Code` in Power Query using the "Add Column" feature. These new columns will improve data clarity, enable targeted insights, and enhance compatibility with external tools.

1. The Age Group column segments customers into different age brackets to identify purchasing trends.

`Age Group` Formula
```Excel
= if [Age] >= 0 and [Age] <= 12 then "Child"
  else if [Age] >= 13 and [Age] <= 18 then "Teenager"
  else if [Age] >= 19 and [Age] <= 30 then "Young Adult"
  else if [Age] >= 31 and [Age] <= 45 then "Adult"
  else if [Age] >= 46 and [Age] <= 64 then "Middle Aged"
  else "Senior"
```


2. The Review Rating Category groups ratings into Very Dissatisfied, Dissatisfied, Acceptable, Satisfied, and Very Satisfied, simplifying customer satisfaction analysis.

`Review Rating Category` Formula
```Excel
if [Review Rating] >= 1 and [Review Rating] < 2 then "Very Dissatisfied"
else if [Review Rating] >= 2 and [Review Rating] < 3 then "Dissatisfied"
else if [Review Rating] >= 3 and [Review Rating] < 4 then "Acceptable"
else if [Review Rating] >= 4 and [Review Rating] < 5 then "Satisfied"
else "Very Satisfied"
```

3. The State Code converts full state names into abbreviations for consistency and easier geographic analysis.

`State Code` Formula
```Excel
= if [#"States (U.S)"] = null then "Unknown"
  else if [#"States (U.S)"] = "Alabama" then "AL"
  else if [#"States (U.S)"] = "Alaska" then "AK"
  else if [#"States (U.S)"] = "Arizona" then "AZ"
  else if [#"States (U.S)"] = "Arkansas" then "AR"
  else if [#"States (U.S)"] = "California" then "CA"
  else if [#"States (U.S)"] = "Colorado" then "CO"
  else if [#"States (U.S)"] = "Connecticut" then "CT"
  else if [#"States (U.S)"] = "Delaware" then "DE"
  else if [#"States (U.S)"] = "Florida" then "FL"
  else if [#"States (U.S)"] = "Georgia" then "GA"
  else if [#"States (U.S)"] = "Hawaii" then "HI"
  else if [#"States (U.S)"] = "Idaho" then "ID"
  else if [#"States (U.S)"] = "Illinois" then "IL"
  else if [#"States (U.S)"] = "Indiana" then "IN"
  else if [#"States (U.S)"] = "Iowa" then "IA"
  else if [#"States (U.S)"] = "Kansas" then "KS"
  else if [#"States (U.S)"] = "Kentucky" then "KY"
  else if [#"States (U.S)"] = "Louisiana" then "LA"
  else if [#"States (U.S)"] = "Maine" then "ME"
  else if [#"States (U.S)"] = "Maryland" then "MD"
  else if [#"States (U.S)"] = "Massachusetts" then "MA"
  else if [#"States (U.S)"] = "Michigan" then "MI"
  else if [#"States (U.S)"] = "Minnesota" then "MN"
  else if [#"States (U.S)"] = "Mississippi" then "MS"
  else if [#"States (U.S)"] = "Missouri" then "MO"
  else if [#"States (U.S)"] = "Montana" then "MT"
  else if [#"States (U.S)"] = "Nebraska" then "NE"
  else if [#"States (U.S)"] = "Nevada" then "NV"
  else if [#"States (U.S)"] = "New Hampshire" then "NH"
  else if [#"States (U.S)"] = "New Jersey" then "NJ"
  else if [#"States (U.S)"] = "New Mexico" then "NM"
  else if [#"States (U.S)"] = "New York" then "NY"
  else if [#"States (U.S)"] = "North Carolina" then "NC"
  else if [#"States (U.S)"] = "North Dakota" then "ND"
  else if [#"States (U.S)"] = "Ohio" then "OH"
  else if [#"States (U.S)"] = "Oklahoma" then "OK"
  else if [#"States (U.S)"] = "Oregon" then "OR"
  else if [#"States (U.S)"] = "Pennsylvania" then "PA"
  else if [#"States (U.S)"] = "Rhode Island" then "RI"
  else if [#"States (U.S)"] = "South Carolina" then "SC"
  else if [#"States (U.S)"] = "South Dakota" then "SD"
  else if [#"States (U.S)"] = "Tennessee" then "TN"
  else if [#"States (U.S)"] = "Texas" then "TX"
  else if [#"States (U.S)"] = "Utah" then "UT"
  else if [#"States (U.S)"] = "Vermont" then "VT"
  else if [#"States (U.S)"] = "Virginia" then "VA"
  else if [#"States (U.S)"] = "Washington" then "WA"
  else if [#"States (U.S)"] = "West Virginia" then "WV"
  else if [#"States (U.S)"] = "Wisconsin" then "WI"
  else if [#"States (U.S)"] = "Wyoming" then "WY"
  else "Unknown"
```

### 3. Load


## Transform


## Load





