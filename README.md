# datatransfersqltobigquery
DataPath - Automating Data Transfer From A SQL Instance To BigQuery

Technologies Used: 
 - Programming Language: Python 
 - Database Management: SQL | SQl Workbench
 - Google Cloud Console: SQL Instance & BigQuery
 - Google Collab
The objective of this project was to develop an automated solution that allows the transfer of data from a SQL instance to BigQuery. In the realm of Data Engineering, this process is the first layer when working with Data Lakes: the Ingestion Process.

A Data Lake is a centralized repository of structured, semi-structured, and unstructed data. The data that the data lake contains, can be fed through multiple sources. In the case for this project, I had a Database (retail_db) hosted on a SQL Instance on Google Cloud and transferred the data to a data lake hosted on BigQuery. In the Ingestion process, the data that is being transferred is called Raw Data since we are doing an exact copy of the tables in the database into the data lake. Once the data is transferred, inside the data lake the data in cleaned up.

To automate the data transfer of the Retail_Db Database hosted on MySQL Cloud to BigQuery, I developed a Python Script that: 1) Connects to MySQL with the user input credentials, 2) Shows and prompts the user which table the user wishes to transfer to BigQuery, 3) Connects to BigQuery, 4) Transfers the desired tables to BigQuery.

Process:
Environment Set Up using Google Collab as text editor
Program prompts the user to input the required information to establish the database connection: IP, Username, Password, DB Name. The inputed credentials are inserted into the userinput list and each index is used for the DB connection function.
Using the pd.read_sql() function from the pandas library, we obtain the names of the tables that the database has.
The program then prompts the user to choose which tables the user wants to transfer to BigQuery. The chosen table names are inserted to the chooseinput (list []) variable. This variable is the one that is going to be used to construct the strings required for the data transfer function.
We establish the connection to BigQuery and Create a BigQuery client.
We then transfer the data through iteration. Per iteration, the loop: Establishes a connection to mysql, Constructs the string command that states which table should be transferred, Grabs all the data from the desired table by creating and executing a query that SELECT * FROM the desired table, and Writes into BigQuery the desired table with all of its data.
