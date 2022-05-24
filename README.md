# PySpark on Databricks

Skillset:

* PySpark DataFrames
* Spark 2.0 DafaFrames
* Working with large dataset
* Spark specifics, e.g. Spark Streaming

## Concept Notes

1. Hadoop is a way to distribute very large files across multiple machines. It uses the Hadoop Distributed File System (HDFS), which allows a user to work with large datasets. It duplicates blocks of data for fault tolerance and also uses MapReduce to allow computations on that data. 

2. MapReduce is a way to splitting a computation task to a distributed set of files (such as HDFS). It consists of a Job Tracker and multiple Task Trackers. The Job Tracker sends code to run on the Task Trackers. The Task trackers allocate CPU and memory for the tasks and monitor the tasks on the worker nodes.

3. Spark is an open source project on Apache, a technology to handle big data. It can be considered as a flexible alternative to MapReduce. MapReduce requires files to be stored only in HDFS while Spark can use data stored in varies formats: Cassandra, AWS S3, HDFS, etc. Spark also can perform operations much faster than MapReduce. 

   Spark Resilient Distributed Dataset (RDD) has two types of Spark operations: transformations and actions. RDDs has four main features:

   * Distributed collection of data
   * Fault-tolerant
   * Parallel operation - partitioned
   * Ability to use many data sources

   Spark DataFrames are now the standard way of using Spark's Machine Learning Capabilities. 

4. There are four methods of accessing Spark:
   1. Ubuntu+Spark+Python on VirtualBox
   2. Amazon EC2 with Python and Spark (AWS 1 year free trial)
   3. Databricks Notebook System
   4. AWS Elastic MapReduce Platform (EMR) Notebook (not free)
5. Spark's MLlib is mainly designed for supervised and Unsupervised learning tasks, with most of its algorithms falling under those two categories.
6. Collaborative filtering (CF) is more commonly used than content-based systems. `spark.ml` uses the alternating least squares (ALS) algorithm to learn latent factors. ALS is a Matrix Factorization approach to implement a recommendation algorithm to decompose large user/item matrix into lower dimensional user factors and item factors.
7. Spark has a lot of `pyspark.ml` feature tools to help out with entire process of NLP.
8. Spark Streaming is an extension of the core Spark API that enables scalable high-throughput fault-tolerant stream processing of live data streams. 

## Set-up Databricks

Databricks is a company that provides clusters that run on top of AWS and adds a convince of having a Notebook System already set up and the ability to quickly add files. It has a free community version that supports a 6GB cluster. It also has its own storage format known as DBFS.

1. Create community edition Databricks account

2. Create a new cluster 

3. Create a new notebook - python

   `import pyspark`

4. Upload data from 'Table'

5. Load data 

   `df= sqlContext.sql("SELECT * FROM mytable")`