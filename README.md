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
  * [Udemy Course](https://www.udemy.com/course/practice-exams-databricks-data-engineer-professional-k/)[I personally opted this which is MUST. Use Udemy for Bussiness for free]

Repo [link](https://github.com/Amrit-Hub/Databricks-Certified-Data-Engineer-Professional-Questions)

## Questions

I was able to note down these memory based questions.

1. Read parameters using dbutils.widgets.text and then get
2. Read access for prod notebook for review to new data engineer - Can Read
3. Attach notebook to cluster and run - Can Restart
4. Production DLT pipelines in job cluster or all pupose cluster
5. CTAS- executes load everytime or while table creation
6. Scope access control to read prod secrets - Read on scope or secret
7. %sh runs on driver node only
8. If there is filter in query - file statistics in transaction log
9. Vacuum run on shallo clone table- Error
10. static_df.join(streaming_df) - which is not possible- left/inner/right
11. Source is CDC - use merge into or leverage CDF feature
12. How to find difference between previous and present commit
13. Nighly jobs to overwrite a table for Bussiness team with least latency - Write to table nightly or create view
14. What is Optimize Table - File target of 1GB?
15. from code - .withWatermark for 10 inutes delay data
16. from code - aggregate on source and overwrite/append to target
17. Email notification in job run where mean(temp) > 120?. received email 3 time,  why?
18. Checkpoint should be unique for each streams
19. Autoloader scenario based question in bronze with history and do update in target
20. Streaming deduplication scenario from code question
21. from code - batch load will overwrite/append?
22. in CDF, if readChangeFeed start version is 0, and append, will there be deduplication?
23. from code - Upsert- identify table is SCD 1 or 2
24. To avoid performance issue, decrease trigger time or not
25. delta table file skipping column decision based question - forst 32 questions, nested or not
26. Grant usage and grand select on delta- what will it do?
27. how to create unmanaged table?
28. good candidate for partition column - date col
29. Alter table xx rename xx - what happens in transaction log
30. add check constraint error and recommendation
31. tbl properties + comments + partition details - describe history/extended/detail?
32. question on delta lake file statistics
33. ganglia UI- detect spill based question
34. repo branch missing on local - how to get that branch with latest code changes
35. delete from A where id in (select id from B) -  can we time travel and see those deleted records? and how to prevent?
36. what is difference between dbfs and mounts
37. api 2.0/jobs/create is exceuted 3 time using a json. what will happen? will it execute or create 3 jobs?
38. What is dbfs
39. install python lib - %pip install
40. Task 1 has downstream task 2 and 3 in parallel. 1 passes, 2 passes, 3 fail- partially completed?
41. streaming job retries in prod - job cluster, unlimited retries and 1 max concurrent run
42. clone existing job and version it- how to do using databricks cli
43. large json 1TB converted to parquet files with partition size of 512 MB - since its not delta table - read>narrow transformation>repartition 2048(1TB*1024*1024/512)>convert to parquet? order of these steps?
44. from code - drop duplicated on batch read and append- what happens in target table dedupliactes?
45. one column was missed in prof from kafka- in future, to avoid - write to bronze to have full replayable history
46. question on giving access control to users
47. pyspark.sql.function.broadcast- what is the use- distribute to all worker nodes?
48. from code - join on orders_is, when not matched- insert *- what it does
49. def bronze_load is given. write silver load function so that it was be transformed and updated downstream
50. case when is_member("group") then email else 'redacted end as email, lsv from table- what output if not member of group
51. ganlia UI question to see logs based question
52. how to get task having multi task run - 2.0/jobs/list or get ot 2.0/jobs/run/list or get
53. what is unit testing
54. in dev, multiple display() is executed repeatedly. what happens in prod?
55. from delta, read has option("readChangeFeed") -  will it work on source delta table with no CDC
56. from code - identlty tumbling or sliding window

## Must Read hyperlinks

No matter what, please read these databricks docs. Note the Important tags in these pages and questions at the end on some pages.

1. [Data skipping with Z-order indexes for Delta Lake](https://docs.databricks.com/en/delta/data-skipping.html)
2. [Clone a table on Databricks](https://docs.databricks.com/en/delta/clone.html)
3. [Delta table streaming reads and writes](https://docs.databricks.com/en/structured-streaming/delta-lake.html)
4. [Structured Streaming Programming Guide - Spark 3.5.0 Documentation](https://spark.apache.org/docs/latest/structured-streaming-programming-guide.html)
5. [Configure Structured Streaming trigger intervals](https://docs.databricks.com/en/structured-streaming/triggers.html)
6. [Configure Delta Lake to control data file size](https://docs.databricks.com/en/delta/tune-file-size.html)
7. [Introducing Stream-Stream Joins in Apache Spark 2.3 | Databricks Blog](https://www.databricks.com/blog/2018/03/13/introducing-stream-stream-joins-in-apache-spark-2-3.html)
8. [Best Practices for Using Structured Streaming in Production - The Databricks Blog](https://www.databricks.com/blog/streaming-production-collected-best-practices)
9. [What is Auto Loader?](https://docs.databricks.com/en/ingestion/auto-loader/index.html)
10. [Upsert into a Delta Lake table using merge](https://docs.databricks.com/en/delta/merge.html)
11. [Use Delta Lake change data feed on Databricks](https://docs.databricks.com/en/delta/delta-change-data-feed.html)
12. [Apply watermarks to control data processing thresholds](https://docs.databricks.com/en/structured-streaming/watermarks.html)
13. [Use foreachBatch to write to arbitrary data sinks](https://docs.databricks.com/en/structured-streaming/foreach.html)
14. [How to Simplify CDC With Delta Lake&#39;s Change Data Feed | Databricks Blog](https://www.databricks.com/blog/2021/06/09/how-to-simplify-cdc-with-delta-lakes-change-data-feed.html)
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
26. [Databricks SQL Statement Execution API – Announcing the Public Preview | Databricks Blog](https://www.databricks.com/blog/2023/03/07/databricks-sql-statement-execution-api-announcing-public-preview.html)
27. [Transform data with Delta Live Tables](https://docs.databricks.com/en/delta-live-tables/transform.html)
28. [Manage data quality with Delta Live Tables](https://docs.databricks.com/en/delta-live-tables/expectations.html)
29. [Simplified change data capture with the APPLY CHANGES API in Delta Live Tables](https://docs.databricks.com/en/delta-live-tables/cdc.html)
30. [Monitor Delta Live Tables pipelines](https://docs.databricks.com/en/delta-live-tables/observability.html)
31. [Load data with Delta Live Tables](https://docs.databricks.com/en/delta-live-tables/load.html)
32. [What is Delta Live Tables?](https://docs.databricks.com/en/delta-live-tables/index.html)
33. [Solved: Re: What is the difference between Streaming live ... - Databricks - 17121](https://community.databricks.com/t5/data-engineering/what-is-the-difference-between-streaming-live-table-and-live/m-p/17122#M11172)
34. [What are all the Delta things in Databricks?](https://docs.databricks.com/en/introduction/delta-comparison.html)
35. [Parameterized queries with PySpark | Databricks Blog](https://www.databricks.com/blog/parameterized-queries-pyspark)
36. [Recover from Structured Streaming query failures with workflows | Databricks on Google Cloud](https://docs.gcp.databricks.com/en/structured-streaming/query-recovery.html)
37. [Jobs API 2.0](https://docs.databricks.com/en/workflows/jobs/jobs-2.0-api.html)
38. [OPTIMIZE](https://docs.databricks.com/en/sql/language-manual/delta-optimize.html)
39. [Adding and Deleting Partitions in Delta Lake tables | Delta Lake](https://delta.io/blog/2023-01-18-add-remove-partition-delta-lake/)
40. [What is the Databricks File System (DBFS)?](https://docs.databricks.com/en/dbfs/index.html)
41. [Mounting cloud object storage on Databricks](https://docs.databricks.com/en/dbfs/mounts.html)
42. [Databricks widgets](https://docs.databricks.com/en/notebooks/widgets.html)
