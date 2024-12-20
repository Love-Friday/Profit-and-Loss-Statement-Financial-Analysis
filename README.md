# Profit-and-Loss-Statement-Financial-Analysis

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
1. ﻿﻿﻿Date: The date of the financial transaction.
2. Branch: The name of the branch where the transaction occurred.
3. Account Category: The category of the account (e.g., Revenue, Expense).
4. Account Name: The specific account associated with the transaction (e.g., Salaries, Loan Income).
5. Amount (NGN): The monetary amount of the transaction, in Nigerian Naira.
   ![Screenshot 2024-12-17 125316](https://github.com/user-attachments/assets/0f16e917-93f2-4a89-ad75-abb229cb4a59)
   
##Data Transformation Processes:
1. I familiarized myself with the dataset by reviewing it to understand its structure and the various types of financial data available.
2. In a new column called "Transaction Types", I use Excel's nestd IF functions to catgeorize the transactions from the "Account Category" column as either "Revenue" or "Expenses". 
   
       =IF(C2="Other Expenses","Expenses",IF(C2="Other Income","Revenue",IF(C2="Revenue","Revenue",IF(C2="Cost of Goods Sold","Expenses",IF(C2="Depreciation and 
        Amortization","Expenses",IF(C2="Operating Expenses","Expenses",0))))))
   
   ![Screenshot 2024-12-17 124612](https://github.com/user-attachments/assets/ce759677-22d3-4b2c-95e8-9cc854dc82c1)

4. Imported the dataset into Power BI for further transformation and analysis to meet specific requirements.

 ### Creating a Time Intelliegnce Calendar 
4. From the date column, I created a calendar table to enable me
   ![Screenshot 2024-12-17 123321](https://github.com/user-attachments/assets/e6a90e1f-98fa-40ba-85e9-5aac9c68247f)

### Using DAX Formula to Calculate Total Revenue, Total Expenses & Net Profit. 

5. To calculate the Total Revenue using DAX Functions; I used the tranaction type column(which consist of Revenue and Expenses) and amount column directly.

Total Revenue;

       =CALCULATE ( SUM ( 'p and l'[Amount]), 'p and l'[Transaction Type] = "Revenue")

       
This means sum the amount column where the transaxction type is "REVENUE" only.
![Screenshot 2024-12-20 100014](https://github.com/user-attachments/assets/d2508db1-150d-4314-94d5-142c04a3078e)

6. Total Expenses


Result:
Revenue = ₦8,945,729,507.00
Other Income = ₦337,198,885.00
TOTAL REVENUE = ₦9,282,928,392.00; approximately ₦9.28b. 

6. Total Expenses
   To calculate the Total Expenses using DAX Functions; I used the tranaction type column(which consist of Revenue and Expenses) and amount column directly.

   Total Expenses;

       =CALCULATE ( SUM ( 'p and l'[Amount] ), 'p and l'[Transaction Type] = "Expenses")

   This means sum the amount column where the transaxction type is "EXPENSES" only.
   ![Screenshot 2024-12-20 101758](https://github.com/user-attachments/assets/135a21a4-46d5-4da6-bb80-99e2b14d5b6c)

8. Net Profit
   To calculate Net Profit = Total Revenue - Total Expenses
   Using Tables
   ![Screenshot 2024-12-20 103519](https://github.com/user-attachments/assets/1e004a0c-2471-4875-a0f3-7e1ffd463404)
   Approximately:
   


   
   


   

   

      
        

   

   
 


rewrite in a way it wont sound co nfusing to my viewers, based on the columns we have. in a new column named transaction types, based on account category column, i  categorize the transactions into revenues and expenses using the nested if functions in ms excel. 

- First, I ensured the dataset was properly organized, with columns for Date, Branch, Account Category, Account Name, and Amount.
- I extracted additional columns like Year and Month from the Date column to facilitate time-based analysis.

 ## Data Cleaning
As part of the data preparation process, I performed thorough data cleaning to ensure the dataset's accuracy and reliability. One of the key steps involved identifying and handling duplicate entries, which could lead to skewed results if left unchecked.
Steps Taken in Data Cleaning:
1. Data Inspection and Preparation: inspected the dataset to identify any inconsistencies, such as missing values or erroneous entries.
2. Searched for Duplicates: I used Excel’s built-in Duplicate Removal and Conditional Formatting features to identify duplicates. After applying the duplicate search, I discovered a total of 9 duplicate entries within the dataset.
    - Handling Duplicates: removed them from the dataset to ensure that each financial record was unique and accurately represented.
3.  Re-validation and Final Review
    - After removing the duplicates, I re-checked the dataset for any additional anomalies and ensured that no important data was lost during the cleaning process.
    - The cleaned dataset was then ready for further analysis using Pivot Tables and other methods to extract meaningful financial insights.

## Using Pivot Tables for Data Summarization and Financial Analysis
In this project, I applied Pivot Tables to efficiently summarize and analyze the financial dataset. The dataset contained various financial metrics, including revenue, expenses, income, and amortization, spread across multiple rows and categories. By using Pivot Tables, I was able to quickly aggregate and summarize key financial figures, enabling me to calculate essential performance indicators.

### Pivot Table Creation:
- I created a Pivot Table to summarize the financial data across different dimensions such as Revenue, Cost of Goods Sold (COGS), Operating Expenses, and Other Income/Expenses.
- I placed Account Category in the Rows section of the Pivot Table to group data by categories (e.g., Revenue, COGS, Depreciation and Amortization, Operating Expenses, Other Income, etc.).
- I placed Amount in the Values section to calculate the totals for each account category. This allowed me to calculate the total values for each category such as Revenue, Other Income, Operating Expenses, and COGS.

### Calculation of Key Financial Figures:
1. Gross Profit: I calculated Gross Profit by subtracting COGS from Revenue.
2. Operating Profit (EBIT): I calculated Operating Profit by subtracting Operating Expenses and Depreciation & Amortization from the Gross Profit.
3. Net Profit: I calculated Net Profit by adding Other Income and subtracting Other Expenses from Operating Profit.


Revenue                      ₦8,945,729,507.00  Other Income                 ₦337,198,885.00     
 Other Expenses               -₦169,499,424.00    
 Depreciation & Amortization   -₦183,157,267.00   Operating Expenses            -₦699,197,468.00   
 Cost of Goods Sold            -₦3,712,506,264.00 



### To Calculate Gross Profit 
- Gross Profit Formula is
- Gross Profit = Revenue − Cost of Goods Sold (COGS)
    - ₦8,945,729,507.00 - (-₦3,712,506,264.00
- (Note: This is negative, so when subtracted, it will effectively add to the Revenue).
- Gross Profit =  ₦8,945,729,507.00 + ₦3,712,506,264.00
- Gross Profit= ₦12,658,235,771.00
  
### To Calculate Operating Profit Formula (EBIT)
- Operating Profit (EBIT) = Gross Profit − Operating Expenses − Depreciation and Amortization
  - Steps taken;
- Start with Gross Profit ₦12,658,235,771.00
- Subtract Operating Expenses -₦699,197,468.00
- Gross Profit − Operating Expenses =  ₦12,658,235,771.00 - (-₦699,197,468.00) =  ₦13,357,433,239.00
- Subtract Depreciation and Amortization FROM  ₦13,357,433,239.00
- ₦13,357,433,239.00 −(−₦183,157,267.00) = 13,357,433,239.00+183,157,267.00= 13,540,590,506.00
- Operating Profit = ₦13,540,590,506.00

  ### To Calculate Net profit
  - Net Profit:
  - Formula: Net Profit = Operating Profit - Other Expenses + Other Income
      - Steps
- Start with operating Profit ₦13,540,590,506.00
- Add Other Income(e.g. Dividend Income, Exchange Loss/Gain, Interest Income, Gain/Loss on Sales of Asset)  ₦337,198,885.00
- Therefore; Operating Profit + Other Income=13,540,590,506.00+337,198,885.00=13,877,789,391.00
- Subtract Other Expenses(e.g. Interest Expense, Taxation) -₦169,499,424.00
- Net Profit=13,877,789,391.00−(−₦169,499,424.00)=13,877,789,391.00 + 169,499,424.00
- Final Net Profit = ₦14,047,288,815.00

 ### To Calculate Operating Margin
 - Operating Margin is a profitability ratio that measures the percentage of revenue that remains after covering operating expenses, excluding interest and taxes
 - Formula: Operating Margin = Operating Profit(EBIT) /Revenue * 100
 - Operating Marin = ₦13,540,590,506.00 / ₦8,945,729,507.00 = 1.513
 - Multiplied by 100
     - = 1.513 * 100
 - Operating Margin= 1.513 × 100= 151.3%

  ### Analyzing Financial Ratios:
  I used the summarized data to calculate key financial ratios such as Gross Profit Margin, Operating Margin, and Net Profit Margin:
  - Gross Profit Margin:

   
#### Interpretation of Operating Margin:
An operating margin of 151.3% indicates that the Operating Profit (EBIT) is more than one and a half times the Revenue, which seems very high and might be an unusual figure. This could suggest that the operating costs (such as COGS, depreciation, or operating expenses) are very low compared to revenue, or that there might be some other specific factors affecting the calculation.
    
 ### To Calculate Net Profit Margin
 - Net Profit Margin is a profitability ratio that shows what percentage of revenue remains after all expenses (including operating expenses, interest, taxes, and other expenses) have 
 been deducted. It is calculated by dividing Net Profit by Revenue.
 - Formula: Net Profit Margin = Net Profit/ Revenue * 100
 - ₦14,047,288,815.00/ ₦8,945,729,507.00 = 1.571
 - Net Profit Margin= 1.571 × 100 = 157.1%
 - Therefore, Net Profit Margin: 157.1%

Interpretation:
A Net Profit Margin of 157.1% suggests that your Net Profit is more than one and a half times your Revenue, which is highly unusual. This indicates that the company's expenses (including operating expenses, interest, taxes, etc.) are extremely low relative to the revenue, or there might be other extraordinary income or factors influencing this figure.

### To Calculate Cost of Goods Sold Ratio(COGS) 
- Cost of Goods Sold (COGS) Ratio measures the proportion of a company's revenue that goes toward covering the cost of producing or acquiring the goods it sells. It is calculated by dividing COGS by Revenue.
- Formula: COGS Ratio = Cost of Goods Sold(COGS)/ Revenue * 100
   - Steps
- COGS: -₦3,712,506,264.00 (negative because it's an expense).
- Revenue: ₦8,945,729,507.00.
- COGS Ratio = −₦3,712,506,264.00 / ₦8,945,729,507.00 = −0.414
- COGS Ratio= −0.414 × 100 = −41.4%

Interpretation:
A COGS Ratio of -41.4% means that 41.4% of the revenue goes towards the cost of producing or acquiring the goods sold by the company. Since it's a negative number, this suggests that COGS is being subtracted as an expense, which is normal, but it’s presented this way because of the negative sign used in accounting for costs.

In simpler terms, 41.4% of every ₦1 in revenue is spent on the cost of goods sold, which is a standard way to interpret how much the company is spending on production or procurement of the products it sells.

Dynamic Analysis:

The Pivot Table allowed for easy filtering and slicing of data by Month, Year, or Account Category, giving flexibility to analyze financial performance across different time periods or categories.
I also made use of Pivot Table features such as Grouping and Summarizing to further segment and analyze the data by specific criteria (e.g., monthly or yearly performance).

Conclusion:
By leveraging the power of Pivot Tables, I was able to streamline the process of summarizing and analyzing complex financial data. The insights gained from this analysis, including key profit calculations and financial ratios, provided a clear understanding of the company's financial performance and enabled more informed decision-making.


 Summary and Insights:
The company demonstrates exceptionally high profitability across all metrics, with Net Profit, Operating Profit, and Gross Profit margins all significantly surpassing 100%. These figures suggest a highly efficient business model with very low costs relative to revenue, or potentially extraordinary one-time income.

Cost management is clearly a strong point, with Operating Expenses and Depreciation/Amortization being relatively small compared to the overall revenue, resulting in a large Operating Profit.

The COGS figure indicates that 41.4% of the revenue is spent on production, which is quite reasonable for many types of businesses.

However, the margins are much higher than typical industry standards, suggesting that this business is either highly specialized, very efficient, or possibly benefiting from non-recurring gains.

The next steps could involve investigating whether these high margins are sustainable or if any unusual events have inflated the figures (e.g., one-time gains or tax benefits).

Conclusion:
The financial performance of the company, as shown by these key ratios and figures, is remarkably strong. The high Net Profit Margin, Operating Margin, and Gross Profit Margin indicate that the company is very profitable, with low costs relative to revenue. These results suggest a very efficient operation, although further investigation into any unusual or non-recurring factors would be prudent to confirm the sustainability of this performance.

If you need further analysis or additional insights, feel free to reach out!

















