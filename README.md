# YouTube Data Analysis ETL Using AWS (S3, Glue, Lambda, Athena, Cloudwatch, QuickSight) 

This project creates a scalable data pipeline to analyze YouTube data from Kaggle using AWS services. It processes raw JSON and CSV files into cleansed, partitioned datasets, integrates them with ETL workflows, and catalogs data for querying. Final insights are visualized in QuickSight dashboards.

## Dataset Description (Trending YouTube Video Statistics)
The Youtube Kaggle dataset contains raw JSON and CSV files with details about trending YouTube videos by region and category. It provides insights into video popularity, user engagement, and regional content trends, making it valuable for:
•	Identifying popular categories and regions for targeted content creation.
•	Analyzing audience engagement metrics like likes, dislikes, and comments.
•	Tracking video performance trends over time.

**Dataset Link:** https://www.kaggle.com/datasets/datasnaek/youtube-new

## Business Problem
This project addresses the following business questions:
1. What types of content perform best in specific regions?
2. Which video categories generate the highest engagement?
3. How does audience interaction (likes, dislikes, comments) correlate with views?
4. What keywords or topics drive video popularity?

## AWS Services Used
- **AWS S3**: Data storage for raw, cleansed, and final datasets.
- **AWS Glue**: ETL processes and data cataloging.
- **AWS Lambda**: JSON data processing and array expansion.
- **Amazon Athena**: Data querying and analysis.
- **Amazon QuickSight**: Visualization and dashboard creation.
- **AWS CloudWatch**: Monitoring logs for Glue and Lambda.
- **IAM Roles**: Secure access control for AWS services.

## Architecture Diagram

![Architecture Diagram](https://github.com/deept-agl/Youtube-data-ETL-Analysis-using-AWS/blob/main/Youtube_Analysis_Architecture_Digaram.drawio.png)

## Steps Implemented

1. Data Ingestion- Downloaded Kaggle dataset consisting of multiple CSV and JSON files. Bulk uploaded files to the S3 raw bucket using AWS CLI.

2. Data Cataloging- Created a Glue crawler to catalog raw data in S3. Queried raw data using Athena for initial exploration.

3. Data Processing
- JSON Files:Developed a Lambda function to process raw JSON files. Expanded arrays and stored processed data in the cleansed S3 bucket in Parquet format. Added an S3 trigger to automatically invoke the Lambda function when new files are uploaded.
- CSV Files: Created a Glue ETL job to process raw CSV files. Stored processed data in the cleansed S3 bucket partitioned by region.

4. Data Integration- Developed a Glue ETL job to join cleansed CSV and JSON files on id and category_id. Stored the integrated dataset in the final analytics S3 bucket in Parquet format. Created a Glue catalog for the final analytics dataset.

5. Data Visualization-Queried final analytics data using Athena. Connected Athena to Amazon QuickSight to build dashboards and reports.

## Quicksight Dashboard

![Yotube Analytics Dashboard](https://github.com/deept-agl/Youtube-data-ETL-Analysis-using-AWS/blob/main/Snippets/Youtube_Analytics_Dashboard.png)


   
