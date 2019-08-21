# Data-Pipelines-with-Airflow
 Demo of Data pipeline using airflow to transfer data from S3 to Amzon Redshift
 and then preform a data quality check on the data loaded in the tables.

# Project Overview

 This project introduces core concepts of Apache Airflow. It is also a Demo of
 creating custom operators to perform tasks such as staging the data,
 filling the data warehouse, and running checks on the data as the final step.

## Datasets

 For this project, s3 links for the datasets are as belows

     Log data: s3://udacity-dend/log_data
     Song data: s3://udacity-dend/song_data


## Configuring the DAG

        In the DAG, default parameters are added as per below

            The DAG does not have dependencies on past runs
            On failure, the task are retried 3 times
            Retries happen every 5 minutes
            Catchup is turned off
            Do not email on retry

        In addition, task dependencies are set as per the graph view follows the flow shown in the image below.

 ![](Project%20Flow.JPG)

## Software

*  AWS S3, Redshift
*  Python 3.6 with airflow

## Programming languages

*  SQL
*  Python
*  JSON

## How to run

*  start airflow server
*  Start the Redshift server and note the details for creating connections
*  create connections for aws and redshift. Name should be aws_credentials, redshift
        ![](AirFlow%20Connection%201.JPG), ![](AirFlow%20Connection%201.JPG),![](AirFlow%20Connection%202.JPG)
        ![](AirFlow%20Connection%203.JPG),![](AirFlow%20Connection%204.JPG),![](AirFlow%20Connection%205.JPG)
* Run the DAG
* After the DAG is completed, all tasks will be marked as green
        ![](DAG%20Success.JPG)

## Code Walkthrough
