![converted_optimized](https://github.com/user-attachments/assets/20478811-61e1-4f12-a283-b2a61e383fb9)

## Introduction

This interactive **U.S. Consumer Shopping Trends Dashboard** was developed to provide marketing stakeholders with actionable insights into key performance indicators (KPIs) and customer behavior patterns.

The dashboard highlights high-level metrics such as the **Top Product Category**, **Average Order Value**, and **Preferred Payment Method**, enabling quick strategic assessments.

In addition, stakeholders can explore **analytical visualizations** including:
- **Total Revenue Across Seasons by Demographic Segment**
- **Customer Review Ratings by Shipping Type**
- **Geographic Distribution of Revenue**
- **Impact of Subscription Status on Customer Loyalty**

The dataset includes detailed information on **revenue**, **customer reviews**, **geographic distribution**, and **subscription status**, all of which are visually represented in the dashboard.


### Dashboard File
My dashboard is in [Shopping_Trends_Project.xlsx](https://github.com/junseok-kim-ca/Customer-Shopping-Analysis/tree/main/1.%20Data%20Analysis)


### Excel Features Applied
- **PivotCharts & Slicers**: Enabled interactive filtering by gender, age, season, and category to let stakeholders easily explore customer trends across segments.

- **Navigation & Layout Enhancements**: Used **hyperlinked navigation, custom chart layouts, and Name Manager** to streamline usability and maintain consistent formatting.

### Dataset
This **[Kaggle](https://www.kaggle.com/datasets/iamsouravbanerjee/customer-shopping-trends-dataset/data)** dataset simulates U S. retail & fashion purchases, offering a snapshot of online‑and‑offline consumer habits for segmentation, marketing, and revenue analysis.

- Customer Demographics
- Shopping Behavior
- Transaction Details
- Delivery & Satisfaction
- Geographic Data

## Dashboard Build

### KPIs
![image](https://github.com/user-attachments/assets/e7634877-9647-4627-ab55-1c0b7d0dacca)

- Tools & Techniques Used: Utilized Excel’s **Name Manager** and KPI formatting to create a clean, dynamic layout that adapts based on slicer interactions.

- Visualization Strategy: Incorporated **relevant icons** and **shape formatting** to visually highlight key metrics, making the dashboard more intuitive and engaging.

- Key Business Takeaways: Clothing consistently ranks as the top product category, with PayPal as the preferred payment method. The average order value is $59.76, offering valuable insight for pricing and promotional strategies.


### Charts

#### Total Revenue Across Seasons by Demographic Segment - Stacked Bar Chart

![image](https://github.com/user-attachments/assets/92d2771a-6af5-47d4-bd5e-cb20dd44c5df)


- Tools & Techniques Used: Built a stacked‑bar PivotChart driven by an underlying PivotTable, so the chart auto‑refreshes and resizes whenever new data appears or slicer filters change

- Visualization Strategy: A stacked layout was chosen so every bar shows both total revenue and the seasonal mix for each demographic at a glance.
  
- Key Business Takeaways: Senior customers contribute the least (less than $20K total revenue). This under‑penetrated group could respond to age‑appropriate loyalty perks or simplified purchase flows.



#### Customer Review Rating Distribution by Shipping Type - Clustered Bar Chart 

![image](https://github.com/user-attachments/assets/4876f28f-b51b-428b-944b-a7f08dd1d4af)


- Tools & Techniques Used: Implemented a clustered-bar PivotChart to effectively display a side-by-side layout, allowing for quick sentiment comparisons across shipping methods, accommodating long labels, and highlighting subtle differences.

- Visualization Strategy: A clustered layout isolates each rating category (Very Satisfied → Satisfied → Acceptable → Dissatisfied) side‑by‑side, making it easy to compare sentiment across shipping methods while still seeing the internal mix within each cluster.
  
- Key Business Takeaways: Very‑Satisfied ratings are scarce (< 3 % across the board), indicating that while most customers deem the service "okay," very few are genuinely delighted. A "surprise‑and‑delight initiative" (e.g., proactive delivery updates or small unboxing perks) could move the needle.


#### Geographic Distribution of Revenue by Product Type - Map Chart 

![image](https://github.com/user-attachments/assets/e515f62d-d0de-49ca-b18b-9ab26b1a55e1)


- Tools & Techniques Used: 

- Visualization Strategy:
  
- Key Business Takeaways:


#### Impact of Subscription Status on Customer Loyalty by Purchase Frequency - Clustered Bar Chart

![image](https://github.com/user-attachments/assets/00e9f7ad-e867-4d69-acd6-724eb19ab147)


- Tools & Techniques Used: 

- Visualization Strategy:
  
- Key Business Takeaways:


### Slicers
![image](https://github.com/user-attachments/assets/2bf8c64b-d1c8-4725-8761-5ac24ea840be)

- Tools & Techniques Used: Used **Excel Slicers** to interactively filter Pivot Charts by:
  - Gender  
  - Age Group  
  - Season  
  - Item Category  
  
- Visualization Strategy: Created **dynamic Pivot Charts** linked to slicers for real-time filtering by demographics, seasons, and product categories. Helped visualize patterns like seasonal trends or demographic preferences
  
- Data Structuring Approach: Structured data in a **clean, tabular format** with consistent category labels to support seamless filtering and grouping in slicers and Pivot Tables
  - Instantly compare metrics (e.g., revenue or loyalty) by season, age group, or item type  
  - Identify target segments and product trends easily  
  - Enhances decision-making with interactive, filterable insights

