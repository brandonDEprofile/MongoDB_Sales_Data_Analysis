📊 Sales Data Analysis with MongoDB

This project demonstrates how to import a large CSV dataset into MongoDB and analyze sales performance using aggregation pipelines and indexes. The script focuses on identifying profit trends across products, regions, and sales channels while measuring query execution time.

📁 Project Overview

The MongoDB script performs the following tasks:

Creates a database and collection

Imports a CSV file containing sales data

Runs aggregation queries to analyze profits

Measures query execution time

Creates indexes to optimize performance

🛠 Technologies Used

MongoDB

Mongo Shell (mongosh / mongo)

CSV Dataset (Sales Records)

📂 Dataset

The dataset used is a CSV file containing sales transaction records, including fields such as:

Item Type

Region

Sales Channel

Total Revenue

Total Profit

Example file name:

100000 Sales Records.csv

🚀 Setup & Usage
1️⃣ Start MongoDB

Ensure MongoDB is running locally.

mongod

2️⃣ Create Database and Collection

Run the following in the MongoDB shell:

use("sales_db");
db.createCollection("sales_records");

3️⃣ Import CSV Data

Import the CSV file into MongoDB:

mongoimport --db sales_db \
--collection sales_records \
--type csv \
--headerline \
--file "C:\wgu\100000 Sales Records.csv"


⚠️ Update the file path if needed for your system.

🔍 Queries & Analysis
Query 1 — Products with the Highest Profit

Groups sales by Item Type

Calculates total profit per product

Returns the top 5 most profitable items

Query 2 — Most Profitable Regions

Groups sales by Region

Ranks regions based on total profit

Query 3 — Online vs Offline Sales Performance

Compares Sales Channel

Calculates total profit and total revenue per channel

Each query measures and prints execution time in milliseconds.

⚡ Performance Optimization

Indexes are created to improve query performance:

// Query 1 optimization
db.sales_records.createIndex({ "Item Type": 1, "Total Profit": -1 });

// Query 2 optimization
db.sales_records.createIndex({ "Region": 1, "Total Profit": -1 });

// Query 3 optimization
db.sales_records.createIndex({ "Sales Channel": 1, "Total Profit": -1 });


These indexes help MongoDB efficiently group and sort large datasets.

📈 Sample Output

Each query prints:

Aggregation results

Execution time (milliseconds)

Example:

=== Query 1 Results ===
[ { _id: "Household", totalProfit: 123456789 } ]
Query 1 time (ms): 42

📌 Key Takeaways

Demonstrates real-world MongoDB aggregation usage

Highlights indexing for performance improvement

Suitable for large datasets (100k+ records)

Useful for data analytics and database optimization practice
