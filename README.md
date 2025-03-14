# home-sales-challenge

## files
- [Home_Sales](Home_Sales.ipynb) uses PySpark & SQL to explore home sales data & identify key metrics (see below for specifics). Run in Google Colab for best results.
- Data is stored in AWS S3 & is retrieved in the file above (via PySpark)

## exploration
Queries we perform include:
- What is the average price for a four-bedroom house sold for each year? 
- What is the average price of a home for each year the home was built, that has three bedrooms and three bathrooms? 
- What is the average price of a home for each year the home was built, that has three bedrooms, three bathrooms, two floors, and is greater than or equal to 2,000 square feet?
- What is the average price of a home per "view" rating having an average home price greater than or equal to $350,000? 
    - We query this question twice more to see whether caching or parquet improves performance. The initial query runs in ~0.5 seconds on average; caching & parquet both run in about 0.4 seconds. (Since the dataset isn't very large to begin with and we partitioned the table on a column that wasn't really relevant to the query, it's unsurprising that using parquet didn't improve performance by more than 0.1 seconds.)

See the Jupyter Notebook file for results.

## sources
- Starter code provided by bootcamp
- [Stack Overflow](https://stackoverflow.com/questions/17762639/this-sql-order-by-is-not-working-properly) for help on remembering how to cast a string column to int