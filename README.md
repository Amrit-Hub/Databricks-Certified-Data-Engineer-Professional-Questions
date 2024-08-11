# Databricks Certified Data Engineer Professional Questions

## Suggestions

- [Practice from these notebooks throroughly](/files/advanced-data-engineering-with-databricks.dbc) and below pdf
  * [Incremental processing](/files/ade-mod-1-incremental-processing-with-spark-structured-streaming.pdf)
  * [ETL patterns](/files/ade-mod-2-streaming-etl-patterns-with-dlt.pdf)
  * [Data Privacy](/files/ade-mod-3-data-privacy-patterns.pdf)
  * [Performnace Optimization](/files/ade-mod-4-performance-optimization-with-spark-and-delta-lake.pdf)
  * [DLT practices](/files/ade-mod-5-swe-practices-with-dlt.pdf)
  * [Automate prod workflows](/files/files/ade-mod-6-automate-production-workflows.pdf)
  * [Knowledge check](/files/ADEWD_Knowledge_Checks.pdf)
  * [Udemy Practice](https://www.udemy.com/course/practice-exams-databricks-data-engineer-professional-k/)[I personally opted this which is MUST. Use Udemy for Bussiness for free]

Repo [link](https://github.com/Amrit-Hub/Databricks-Certified-Data-Engineer-Professional-Questions)

## Topics

I was able to note down these topics memory based.

1. How can you read parameters using `dbutils.widgets.text` and retrieve their values?
   * **Hint** : Focus on using `dbutils.widgets.get` to retrieve the values.
2. How do you provide read access for a production notebook to a new data engineer for review?
   * **Hint** : The answer involves setting the notebook's permissions to "Can Read."
3. When attaching a notebook to a cluster, which permission allows you to run the notebook?
   * **Hint** : The user needs "Can Restart" permission.
4. Should production DLT pipelines be run on a job cluster or an all-purpose cluster?
5. Does a CTAS (CREATE TABLE AS SELECT) operation execute the load every time or only during table creation?
6. How can you control access to read production secrets using scope access control?
   * **Hint** : The answer involves setting "Read" permissions on the scope or secret.
7. Where does the `%sh` command run in Databricks?
   * **Hint** : It runs on the driver node.
8. If a query contains a filter, how does Databricks use file statistics in the transaction log?
9. What happens when you run a `VACUUM` command on a shallow clone table?
   * **Hint** : Running `VACUUM` on a shallow clone table will result in an error?
10. Which type of join (left, inner, right) is not possible when performing a join between a static DataFrame and a streaming DataFrame?
    * **Hint** : Consider the limitations of streaming joins.
11. When the source is a CDC (Change Data Capture), should you use `MERGE INTO` or leverage the Change Data Feed (CDF) feature?
12. How can you find the difference between the previous and present commit in a Delta table?
13. What is the best approach for nightly jobs that overwrite a table for the business team with the least latency?
    * **Hint** : Should you write to the table nightly or create a view?
14. What does the `OPTIMIZE TABLE` command do, and what is the target file size?
    * **Hint** : Focus on the target file size of 1GB.
15. In a streaming scenario, what does the `.withWatermark` function do with a delay of 10 minutes?
16. How does aggregating on the source and then overwriting/appending to the target impact data load?
17. Why did you receive three email notifications when a job was set to trigger an email if `mean(temp) > 120`?
    * **Hint** : Investigate multiple triggers for the email alert.
18. Why should the checkpoint directory be unique for each stream in a streaming job?
19. How would you set up an Autoloader scenario to load data into a bronze table with history and update the target table?
20. How can you handle streaming deduplication based on a given code scenario?
21. For batch loading, what happens if the load is set to overwrite or append?
    * **Hint** : Consider the impact on the target table.
22. In a Change Data Feed (CDF) scenario, if `readChangeFeed` starts at version 0 and append is used, will there be deduplication?
23. How can you identify whether a table is SCD Type 1 or 2 based on an upsert operation?
24. To avoid performance issues, should you decrease the trigger time or not?
25. How does Delta Lake decide on file skipping based on columns in a query, and what are the implications for nested columns?
26. What does granting "Usage" and "Select" permissions on a Delta table allow a user to do?
27. How do you create an unmanaged table in Databricks?
28. What makes a date column a good candidate for partitioning in a Delta table?
29. What happens in the transaction log when you rename a Delta table using `ALTER TABLE xx RENAME xx`?
30. How would you handle an error with a check constraint and what would you recommend?
31. When using `DESCRIBE` commands, how can you retrieve table properties, comments, and partition details?
    * **Hint** : Use `DESCRIBE HISTORY`, `DESCRIBE EXTENDED`, or `DESCRIBE DETAIL`.?
32. How are file statistics used in Delta Lake, and why are they important?
33. In the Ganglia UI, how can you detect a spill during query execution?
34. If a repo branch is missing locally, how can you retrieve that branch with the latest code changes?
35. After deleting records with a query like `DELETE FROM A WHERE id IN (SELECT id FROM B)`, can you time travel to see the deleted records, and how can you prevent their permanent deletion?
36. What are the differences between DBFS and mounts in Databricks?
37. If the API `2.0/jobs/create` is executed three times with the same JSON, what will happen? Will it execute or create three jobs?
38. What is DBFS in Databricks?
39. How do you install a Python library using `%pip` in a Databricks notebook?
40. If Task 1 has downstream Task 2 and Task 3 running in parallel, and Task 1 and Task 2 succeed while Task 3 fails, what will be the final job status?
    * **Hint** : The job may show as partially completed.
41. How do you handle streaming job retries in production, specifically with job clusters, unlimited retries, and a maximum of one concurrent run?
42. How can you clone an existing job and version it using the Databricks CLI?
43. When converting a large JSON file (1TB) to Parquet with a partition size of 512 MB, what is the correct order of steps? Should you read, perform narrow transformations, repartition (2048 partitions), then convert to Parquet?
44. What happens in the target table when duplicates are dropped during a batch read and append operation?
45. If a column was missed during profiling from Kafka, how can you ensure that the data is fully replayable in the future?
    * **Hint** : Consider writing to a bronze table.
46. How do you handle access control for users in Databricks?
47. What is the use of the `pyspark.sql.functions.broadcast` function in a Spark job?
    * **Hint** : It distributes the data to all worker nodes.
48. What happens when performing a join on `orders_id` with a condition "when not matched, insert *"?
    * **Hint** : The operation will insert records that don’t have a match.
49. Given a function definition for loading bronze data, how would you write a silver load function to transform and update downstream tables?
50. If the code includes `CASE WHEN is_member("group") THEN email ELSE 'redacted' END AS email`, what will be the output if the user is not a member of the group?
51. How can you use the Ganglia UI to view logs and troubleshoot a Databricks job?
52. When working with multi-task jobs, how do you list or get the tasks using the API `2.0/jobs/list` or `2.0/jobs/run/list`?
53. What is unit testing, and how is it applied in a Databricks environment?
54. What happens when multiple `display()` commands are executed repeatedly in development, and what is the impact in production?
55. Will the `option("readChangeFeed")` work on a source Delta table with no CDC enabled?
56. How can you identify whether a tumbling or sliding window is being used based on the code provided?
57. What performance tuning considerations are involved with `spark.sql.files.maxPartitionBytes` and `spark.sql.shuffle.partitions`?

## Must Read hyperlinks

No matter what, please read these databricks docs. Note the Important tags in these pages and questions at the end on some pages.

1. [Data skipping with Z-order indexes for Delta Lake](https://docs.databricks.com/en/delta/data-skipping.html)
2. [Clone a table on Databricks](https://docs.databricks.com/en/delta/clone.html)
3. [Delta table streaming reads and writes](https://docs.databricks.com/en/structured-streaming/delta-lake.html)
4. [Structured Streaming Programming Guide - Spark 3.5.0 Documentation](https://spark.apache.org/docs/latest/structured-streaming-programming-guide.html)
5. [Configure Structured Streaming trigger intervals](https://docs.databricks.com/en/structured-streaming/triggers.html)
6. [Configure Delta Lake to control data file size](https://docs.databricks.com/en/delta/tune-file-size.html)
7. [Introducing Stream-Stream Joins in Apache Spark 2.3](https://www.databricks.com/blog/2018/03/13/introducing-stream-stream-joins-in-apache-spark-2-3.html)
8. [Best Practices for Using Structured Streaming in Production - The Databricks Blog](https://www.databricks.com/blog/streaming-production-collected-best-practices)
9. [What is Auto Loader?](https://docs.databricks.com/en/ingestion/auto-loader/index.html)
10. [Upsert into a Delta Lake table using merge](https://docs.databricks.com/en/delta/merge.html)
11. [Use Delta Lake change data feed on Databricks](https://docs.databricks.com/en/delta/delta-change-data-feed.html)
12. [Apply watermarks to control data processing thresholds](https://docs.databricks.com/en/structured-streaming/watermarks.html)
13. [Use foreachBatch to write to arbitrary data sinks](https://docs.databricks.com/en/structured-streaming/foreach.html)
14. [How to Simplify CDC With Delta Lake&#39;s Change Data Feed](https://www.databricks.com/blog/2021/06/09/how-to-simplify-cdc-with-delta-lakes-change-data-feed.html)
15. [VACUUM](https://docs.databricks.com/en/sql/language-manual/delta-vacuum.html)
16. [Jobs access control](https://docs.databricks.com/en/security/auth-authz/access-control/jobs-acl.html)
17. [Cluster access control](https://docs.databricks.com/en/security/auth-authz/access-control/cluster-acl.html)
18. [Secret access control](https://docs.databricks.com/en/security/auth-authz/access-control/secret-acl.html)
19. [Hive metastore privileges and securable objects (legacy)](https://docs.databricks.com/en/data-governance/table-acls/object-privileges.html)
20. [Data objects in the Databricks lakehouse](https://docs.databricks.com/en/lakehouse/data-objects.html)
21. [Constraints on Databricks](https://docs.databricks.com/en/tables/constraints.html)
22. [When to partition tables on Databricks](https://docs.databricks.com/en/tables/partitions.html)
23. [Manage clusters](https://docs.databricks.com/en/compute/clusters-manage.html)
24. [Export and import Databricks notebooks](https://docs.databricks.com/en/notebooks/notebook-export-import.html)
25. [Unit testing for notebooks](https://docs.databricks.com/en/notebooks/testing.html)
26. [Databricks SQL Statement Execution API – Announcing the Public Preview](https://www.databricks.com/blog/2023/03/07/databricks-sql-statement-execution-api-announcing-public-preview.html)
27. [Transform data with Delta Live Tables](https://docs.databricks.com/en/delta-live-tables/transform.html)
28. [Manage data quality with Delta Live Tables](https://docs.databricks.com/en/delta-live-tables/expectations.html)
29. [Simplified change data capture with the APPLY CHANGES API in Delta Live Tables](https://docs.databricks.com/en/delta-live-tables/cdc.html)
30. [Monitor Delta Live Tables pipelines](https://docs.databricks.com/en/delta-live-tables/observability.html)
31. [Load data with Delta Live Tables](https://docs.databricks.com/en/delta-live-tables/load.html)
32. [What is Delta Live Tables?](https://docs.databricks.com/en/delta-live-tables/index.html)
33. [Solved: Re: What is the difference between Streaming live ... - Databricks - 17121](https://community.databricks.com/t5/data-engineering/what-is-the-difference-between-streaming-live-table-and-live/m-p/17122#M11172)
34. [What are all the Delta things in Databricks?](https://docs.databricks.com/en/introduction/delta-comparison.html)
35. [Parameterized queries with PySpark](https://www.databricks.com/blog/parameterized-queries-pyspark)
36. [Recover from Structured Streaming query failures with workflows](https://docs.gcp.databricks.com/en/structured-streaming/query-recovery.html)
37. [Jobs API 2.0](https://docs.databricks.com/en/workflows/jobs/jobs-2.0-api.html)
38. [OPTIMIZE](https://docs.databricks.com/en/sql/language-manual/delta-optimize.html)
39. [Adding and Deleting Partitions in Delta Lake tables](https://delta.io/blog/2023-01-18-add-remove-partition-delta-lake/)
40. [What is the Databricks File System (DBFS)?](https://docs.databricks.com/en/dbfs/index.html)
41. [Mounting cloud object storage on Databricks](https://docs.databricks.com/en/dbfs/mounts.html)
42. [Databricks widgets](https://docs.databricks.com/en/notebooks/widgets.html)
43. [Performance Tuning](https://spark.apache.org/docs/latest/sql-performance-tuning.html)
