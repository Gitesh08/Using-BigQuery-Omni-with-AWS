# Using-BigQuery-Omni-with-AWS

BigQuery Omni lets you run BigQuery analytics on data stored in AWS S3. You will create an authorized connection between Google Cloud BigQuery and AWS S3, query data residing in S3 buckets without any data movement and write query results back to AWS S3 buckets.

![sample csv](https://github.com/Gitesh08/Using-BigQuery-Omni-with-AWS/assets/115268756/3a433dbb-c2a1-44bd-a203-653df3dfc9ca)


Objectives:

1] Create a connection between Google Cloud and AWS

2] Authorize BigQuery Omni to read data in an AWS S3 bucket

3] Create a BigQuery external table that references the raw data in AWS S3 bucket

4] Run queries on AWS S3 data

5] Export query results to AWS S3 bucket


Implementation:

Task 1: Create a BigQuery AWS connection

1) Create an AWS IAM policy for BigQuery
2) Validate the AWS IAM for BigQuery
3) Create the BigQuery AWS connection
4) Add a Trust Relationship to the AWS role

Task 2: Run queries on the AWS S3 external table

1) Create a BigQuery dataset
2) Create an external table

Task 3: Create an external table and query AWS S3 data

1) Query the external table
   
   SELECT * FROM `S3 bucket name.bq_omni_demo.bq-omni-table`

Task 4: Export query results to AWS S3

1) Export Query Results
   
EXPORT DATA WITH CONNECTION `aws-us-east-1.bq-omni-aws-connector`
OPTIONS(uri="s3://S3 bucket name/exports/*", format="CSV")
AS SELECT * FROM `S3 bucket name.bq_omni_demo.bq-omni-table`

2) Navigate to your S3 bucket and verify the data has been exported in the exports directory.

Check out complete workflow: https://medium.com/@gmahadik8080/using-bigquery-omni-with-aws-b09a0d3ca440

Great! You have successfully executed an export query and created a file in your S3 bucket.
