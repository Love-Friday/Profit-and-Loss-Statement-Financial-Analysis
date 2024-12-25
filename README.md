# Profit-and-Loss-Statement-Financial-Analysis

 Table of Contents
1. [Introduction](#introduction)
2. [Project Overview](#project-overview)
3. [Objective](#objective)
4. [Data Structure](#data-structure)
5. [Data Transformation Process](#data-transformation-process)
6. [Objective](#objective)
7. [Insights](#insights)
8. [Summary of Key Findings](#summary-of-key-findings)
9. [Recommendations](#recommendations)


## Introduction
Client: 67Capital Ltd

A company has reached out to me to analyze their financial data, specifically focusing on their Profit and Loss (P&L) statements. The dataset, which spans across six branches in South-South Nigeria from 2020 to 2023, requires a detailed financial analysis to provide insights into the company's revenue, expenses, and overall financial performance.

## Project Overview
As part of our ongoing efforts to enhance our financial oversight and performance evaluation, we are initiating a project focused on analyzing the Profit and Loss (P&L) statements across our six branches, in South-South Nigeria, over the four-year period from 2020 to 2023.
This analysis will provide valuable insights into our financial activities and help inform strategic decisions moving forward.

## Objective
I analyzed the P&L data to understand revenue, expenses, and overall profitability across branches. By the end of this project, we expect to have a clear picture of each branch's financial health and actionable insights to improve performance.

## Dataset Structure
The dataset is a CSV file containing 40,000 rows and 5 columns. The columns are as follows:
1. **﻿﻿﻿Date:** The date of the financial transaction.
2. **Branch:** The name of the branch where the transaction occurred.
3. **Account Category:** The category of the account (e.g., Revenue, Expense).
4. **Account Name:** The specific account associated with the transaction (e.g., Salaries, Loan Income).
5. **Amount (NGN):** The monetary amount of the transaction, in Nigerian Naira.
   ![Screenshot 2024-12-17 125316](https://github.com/user-attachments/assets/0f16e917-93f2-4a89-ad75-abb229cb4a59)
   
## Data Transformation Processes:
1. I familiarized myself with the dataset by reviewing it to understand its structure and the various types of financial data available.
2. In a newly created column titled "Transaction Types," I employ nested IF functions in Excel to classify the entries from the "Account Category" column into two distinct categories: "Revenue" or "Expenses."
   
       =IF(C2="Other Expenses","Expenses",IF(C2="Other Income","Revenue",IF(C2="Revenue","Revenue",IF(C2="Cost of Goods Sold","Expenses",IF(C2="Depreciation and 
        Amortization","Expenses",IF(C2="Operating Expenses","Expenses",0))))))
   
   ![Screenshot 2024-12-17 124612](https://github.com/user-attachments/assets/ce759677-22d3-4b2c-95e8-9cc854dc82c1)

3. Imported the dataset into Power BI for further transformation and analysis to meet specific requirements.

 ### Creating a Time Intelliegnce Calendar
 4. To enhance data analysis, I utilized time intelligence to create a new “Calendar” Table, which includes key time dimensions: year, month, and quarter. This
    structure enables deeper insights by simplifying time-based aggregations  and calculations.
    
5. I modeled the calendar table alongside the financial dataset, establishing a one-to-many relationship between the two. This setup provided a robust foundation for the subsequent data visualization process, enabling more efficient exploration and interpretation of time- based trends. 

   ![Screenshot 2024-12-17 123321](https://github.com/user-attachments/assets/e6a90e1f-98fa-40ba-85e9-5aac9c68247f)

### Using DAX Formula to Calculate Total Revenue, Total Expenses & Net Profit. 

6. To calculate the Total Revenue using DAX Functions; I used the tranaction type column(which consist of Revenue and Expenses) and amount column directly.

Total Revenue;

       =CALCULATE ( SUM ( 'p and l'[Amount]), 'p and l'[Transaction Type] = "Revenue")

       
This means sum the amount column where the transaxction type is "REVENUE" only.
![Screenshot 2024-12-20 100014](https://github.com/user-attachments/assets/d2508db1-150d-4314-94d5-142c04a3078e)

7. Total Expenses
   To calculate the Total Expenses using DAX Functions; I used the transaction type column(which consist of Revenue and Expenses) and amount column directly.

   Total Expenses;

       =CALCULATE ( SUM ( 'p and l'[Amount] ), 'p and l'[Transaction Type] = "Expenses")

   This means sum the amount column where the transaxction type is "EXPENSES" only.
   ![Screenshot 2024-12-20 101758](https://github.com/user-attachments/assets/135a21a4-46d5-4da6-bb80-99e2b14d5b6c)

8. Net Profit
   To calculate Net Profit = Total Revenue - Total Expenses
   
   Using Tables
   ![Screenshot 2024-12-20 103519](https://github.com/user-attachments/assets/1e004a0c-2471-4875-a0f3-7e1ffd463404)
   
   Approximately:
   ![Screenshot 2024-12-20 103816](https://github.com/user-attachments/assets/c910eda3-2176-4697-aefe-0da08bd370e9)

9. Profit Margin: is a financial metric that shows the percentage of revenue a company retains as profit after accounting for all its expenses. It is a measure of a company’s profitability and efficiency in managing its costs.

The formula for profit margin is:

Profit Margin = ( Net Profit/ Revenue) × 100
DAX fORMULA=
  
            = DIVIDE([Net Profit], [Total Revenue], 0)

![Screenshot 2024-12-25 010558](https://github.com/user-attachments/assets/d15c646e-bbae-4b1e-a91e-0d8104362786)

## Insights
The south-south branches of 67 Capital Ltd generated 9.28bn NGN in revenue and utilized 4.77bn NGN in expenses, with a Net Profit of 4.52bn NGN which is a 48.67% profit margin in the space of 4 years, indicating a healthy market/business for the company in the region. 

The Akwa Ibom branch generated the most revenue for the company, followed by Rivers with the least being Delta. 

Delta also had the highest Expenditure within the region.

![Screenshot 2024-12-25 011136](https://github.com/user-attachments/assets/471b5963-0216-459a-a4c5-783f843142e4)

#### Insights on Akwa Ibom Analysis
Akwa Ibom had their best year in 2021 generating over 470M NGN in revenue and utilizing below 200M NGN in expenditure with a profit margin of 53.01%.
They experienced a sharp decline in revenue in the following years which raises concern. 
The main source of revenue was Sales as it is with other branches while majority of the expenditures were on Cost of Sales i.e. cost of producing the goods sold. 

![Screenshot 2024-12-25 012341](https://github.com/user-attachments/assets/0027d064-e9ec-4340-9c79-6bf271699eca)

#### Insights on Delta Analysis
Delta experienced an increase in revenue in 2023 after a long decline in revenue over the years. 
Also, their profit margin moved from 39.26% in 2022 to 47.21% indicating a good growth in revenue. 

![Screenshot 2024-12-25 012047](https://github.com/user-attachments/assets/005fae3c-4050-4626-a403-91d04e768963)

## Summary of Key Findings 
The South-South region has been a good market for the company for the past 4 years, generating over 9bn NGN in revenue and a Net Profit of 4.52bn NGN indicating a 48.67% in Profit Margin. 

Akwa Ibom generated the highest revenue of about 1.67bn NGN in the 4-year period but experienced a decline in revenue from 2022 to 2023. 
Delta generated the least revenue and had the highest expenditure in the 4-year period amounting to 844.50M NGN. Despite the decline, in 2023 they experienced an increase in revenue and a decrease in expenditure. 

## Recommendations
1. Given that Akwa Ibom generated the highest revenue over the 4-year period, but saw a decline from 2022 to 2023, the company should investigate the cause of the revenue drop. This could include market conditions, competition, or operational inefficiencies. It is recommended to strengthen the sales and marketing strategy in this region, perhaps by introducing new products or promotional activities tailored to local demand, to reignite growth and maintain Akwa Ibom's revenue leadership in the South-South region.

2. The management should conduct a comprehensive audit of the company's operations in the high-expense states to identify areas of inefficiency or waste.

3. To increase sales across all states, the company should expand product availability through multiple channels, particularly in regions where sales are underperforming. Additionally, enhancing customer retention and driving repeat purchases can be achieved by launching or refining loyalty programs in these areas. It is also crucial to gain a deep understanding of each state’s unique market needs, preferences, and demographics to tailor strategies effectively.









            

   


   
   


   

   

      
        

   

   
 



   
