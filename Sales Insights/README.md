
# Sales Insights Using PowerBI

Purpose

The purpose of this project is to decipher sales insights specifically in India that were not visible before to assist the sales team make data drivien decisions and to automate the insights to reduce the time spent in manually gathering data.


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
    - Sorted by sales_amount and found 1611 records for 0 or less (needs to be cleaned)
    - Ran query for any records not in INR (Indian Rupee currency)
        - Found 2 records in USD (needs to be cleaned)
    - Found two records in markets table that are not in India (outside of scope, needs to be cleaned)


## Data Visualization Using Power BI

Importing Data
- Ran into an error connecting MySQL to Power BI
- Downgraded MySQL Connector NET per Google search for help below:
https://community.fabric.microsoft.com/t5/Power-Query/Problem-connection-Power-BI-to-MySQL-data-source/m-p/669533#M22729

Data Cleaning/Transformation
- Established data modeling connections between tables where columns were not perfect name matches
    - markets.markets_code connect transactions.market_code
    - date.date connect transactions.order_date
- Used PowerQuery to clean up previous inconsistent data from SQL queries
    - Filter out the 2 non-India records from markets table
    - Filter out all sales_amount that are for 0 INR or less from transactions table
    - Created new column convert_sales_amount with if/else to convert USD if necessary to Indian Rupee
        - Note: I used current exchange rate 82.5 (will update with pull of conversion table)

- New Data Problem Found
    - Checking both Power BI and MySQL, there are two DISTINCT INR and two DISTINCT USD currencies under the transactions.currency column
    - I am making the conclusion that these are duplicates based on the USD output of 4 records where 2 look identical to the other 2
    - Solution: Filter out duplicates
    - Return to PowerQuery
    - Filter out duplicate currencies

Power BI Visualization
 - Created 4 bar charts
    - Revenue by Customer
    - Sales QTY by Customer
    - Revenue by Region
    - Top 5 Products
 - Added Month slicer buttons on Top

