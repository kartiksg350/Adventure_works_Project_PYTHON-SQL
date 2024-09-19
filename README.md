# Uploading-database-to-MySQL-using-Python

# AdventureWorks MySQL Upload

## Overview
This repository contains a Jupyter notebook designed to automate the process of loading data from local CSV files into a MySQL database. The notebook uses Python's pandas library to handle data manipulation and pymysql to connect and interact with the MySQL database.

The notebook is a valuable tool for automating data uploads to MySQL, making it suitable for ETL workflows or simple data migrations.

## Features
Data Loading: Automatically loads data from CSV files into pandas DataFrames.
Data Cleaning: Replaces NaN values with None, which corresponds to NULL in MySQL.
MySQL Connection: Establishes a connection to a local or remote MySQL database.
Data Insertion: Inserts rows from DataFrames into MySQL tables.
Error Handling: Provides basic error handling for MySQL and Python exceptions.

## Prerequisites
Before running the notebook, ensure you have the following:

Python 3.x
MySQL installed locally or on a remote server
Required Python packages:
pandas
pymysql

You can install the required packages using pip:
pip install pandas pymysql

## Usage
Step 1: Clone the Repository
First, clone this repository to your local machine:

git clone https://github.com/your-username/adventureworks-mysql-upload.git
cd adventureworks-mysql-upload

Step 2: Configure the Notebook
Update the File Paths: Modify the file path for your CSV file. For example:

file_path = r'E:\Courses\MySQL\AdventureWorks_Customers.csv'
Update the MySQL Credentials: Modify the MySQL connection details such as host, user, password, and database:

connection = pymysql.connect(
    host='localhost',
    user='root',
    password='your_password',
    database='adventureworks'
)

Step 3: Run the Notebook
Open the Jupyter notebook:

jupyter notebook AdventureWorks_MySQL_Load.ipynb
Run the cells sequentially to upload the CSV data into the MySQL database.

Step 4: Verify Data in MySQL
Once the notebook finishes executing, you can verify that the data was successfully uploaded to your MySQL database by running SQL queries such as:

SELECT * FROM tbl_stg_customers;

## Code Walkthrough
Data Loading: The notebook reads the CSV file into a pandas DataFrame using pd.read_csv() and handles any missing values by converting them to None.

MySQL Connection: A connection to the MySQL database is established using the pymysql.connect() function. Make sure to replace the placeholder values with your own credentials.

Data Insertion: The notebook iterates through the rows of the DataFrame and inserts the data into the specified MySQL table (tbl_stg_customers). Each record is inserted with a prepared SQL statement to prevent SQL injection.

Error Handling: If any errors occur during the MySQL operations, the transaction is rolled back to avoid partial inserts. General errors are also caught and printed to aid debugging.

## License
This project is licensed under the MIT License. See the LICENSE file for more details.

## Contact
For any questions or feedback, feel free to reach out:

Email: kartik350.ks@gmail.com
LinkedIn: https://www.linkedin.com/in/kartiksinghgautamba2023/
