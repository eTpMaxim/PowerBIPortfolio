
# Sales Insights Using PowerBI

Purpose

The purpose of this project is to decipher sales insights that were not visible before to assist the sales team make data drivien decisions and to automate the insights to reduce the time spent in manually gathering data.


Stakeholders

- Data & Analytics Team
- Sales Director
- Marketing Team
- Customer Service Team

These stakeholders are who will be affected by the data analysis we will be performing. The dashboard we will be creating is exclusively for their use to successfully achieve the project goals outlined above under Purpose.


Measures of Success

- Creating a dashboard that provides sales order insights with data gathered
- Sales team no longer manually gathering data and reallocating time to provide value in other areas
- Guide all stakeholders to make better data driven decisions to generate measurable improvements
## Data Analysis Using MySQL

- Gather data through basic queries
    - 150283 records in transactions table
    - 38 records in customers table
    - 279 records in products table
    - 17 records in markets table

Checking Data

- Combine transactions and date tables using the Join function 
    - Sorted by sales_amount and noticed a record for -1 (needs to be cleaned)
    - Ran query for any records not in INR (Indian Rupee currency)
        - Found 2 records in USD (needs to be cleaned)
