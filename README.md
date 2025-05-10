Home Sales Project
==================

Project Description:
--------------------
This project analyzes home sales data using Apache Spark and SparkSQL. The objective is to generate key metrics from the home_sales_revised.csv dataset (downloaded from an AWS S3 bucket) through a series of SQL queries and Spark operations. The assignment focuses on the following tasks:
  • Reading the CSV file into a PySpark DataFrame.
  • Creating a temporary view ("home_sales") from the DataFrame.
  • Executing multiple SparkSQL queries to calculate:
      - The average selling price (rounded to two decimal places) for four-bedroom houses sold per year.
      - The average selling price for homes with three bedrooms and three bathrooms grouped by the year built.
      - The average selling price for homes with three bedrooms, three bathrooms, two floors, and at least 2,000 square feet per year built.
      - The average price per “view” rating (rounded to two decimal places) for ratings where the average home price is at least $350,000. This query also includes runtime measurement.
  • Caching the temporary table and comparing query runtimes with and without caching.
  • Partitioning the dataset by the "date_built" field, writing out the Parquet files, recreating a temporary view of the partitioned data, and re-running the "view" query to measure its runtime.
  • Uncaching the table and verifying that it is no longer cached.


Repository Contents:
--------------------
- Home_Sales_Colab.ipynb : The main notebook containing the complete PySpark project code, including data ingestion, SparkSQL queries, caching, partitioning, and performance measurements.
- README.txt            : This readme file documenting the project description, installation and usage instructions, and details about the repository contents.


Installation and Setup:
-----------------------
1. Apache Spark and Java:
   - For Google Colab, the notebook installs Spark and Java automatically, setting the required environment variables (SPARK_HOME, JAVA_HOME, etc.). I have built in some checks on the installation as Colab had some initial errors running this. 


Usage Instructions:
-------------------
1. Open the "Home_Sales.ipynb" notebook using Google Colab. I have not provided provisions for a local installation. 
2. Run the notebook cells sequentially:
   - The notebook begins by reading the CSV file into a PySpark DataFrame.
   - It then creates a temporary SparkSQL view called "home_sales".
   - Next, it executes four main queries to calculate average home prices under different conditions.
   - The notebook caches the temporary table, re-runs a query to compare cached vs. uncached performance, and measures run times.
   - The data is then partitioned by the "date_built" field and written out in Parquet format. A temporary view from this partitioned data is created, and the last query is re-executed with runtime measurement.
   - Finally, the cached temporary table is uncached and verified.
3. Verify that all outputs and runtime measurements are correct and that the notebook meets all assignment criteria before submitting.

Additional Notes:
-----------------
- The notebook includes detailed comments and markdown cells explaining each step of the process.
- If using Google Colab, ensure that the environment variables (especially JAVA_HOME and SPARK_HOME) are set as shown in the notebook.

Disclaimer: 
--------------------
All code is my own, Google's Gemini AI assistant did assist in troubleshooting and debugging extensively during the initial configuration. MS Copilot was used to help ensure consistency and readability as well. 