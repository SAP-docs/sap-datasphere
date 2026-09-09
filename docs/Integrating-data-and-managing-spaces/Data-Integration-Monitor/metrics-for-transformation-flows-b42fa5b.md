<!-- loiob42fa5b6f4e04a9491efa9bf7dab0929 -->

# Metrics for Transformation Flows

View metrics for completed transformation flow runs.

Metrics provide the record count for source and target tables used in the flow. You can view the following metrics for a completed transformation flow run:

-   `SPARK_APPLICATION_INDEX`

    The index or identifier of the Apache Spark application used to execute the transformation flow. This identifier can be used to track and monitor the Spark application in the cluster's resource manager.

-   `SPARK_PYTHON_FILE_CREATED_AT_RUNTIME`

    Indicates whether a Python file was generated and created at runtime during the Spark-based transformation flow execution. This is common when Python operators are used in the flow.

-   `SPARK_RESOURCE_ID`

    ID of the job used to run the transformation flow on an Apache Spark runtime. This ID must be provided to the SAP support to retrieve and analyze the jobs, and identify the cause of errors.

-   `PYTHON_AVG_BATCH_SIZE`

    Average size of all batches during Python operator execution. It gives a global view of the typical batch size. Comparing this metric against the minimum and maximum batch sizes can help understand the variance in batch sizes. If the average batch size is significantly different from the minimum and maximum, it might suggest inconsistent batch sizing and potential data skew.

-   `BATCH_COLUMN`

    The name of the column used to partition data into batches for HANA-based transformation flows. This column is used to divide the dataset into logical batches for processing.

-   `BATCH_SIZE`

    The number of records processed in each batch during a HANA-based transformation flow run. This metric helps identify the granularity of batch processing and can be used to optimize performance.

-   `RUNTIME`

    Runtime is used to run the transformation flow. It can be HANA \(for a transformation flow in a space with Storage Type SAP HANA Database \(disk and In-Memory\)\) or SPARK \(for transformation flow in a space with Storage Type SAP HANA Data Lake Files\).

-   `BATCH_COL_NUM_OF_DISTINCT_VAL_NOT_NULL`

    The count of unique values in the batch column, excluding NULL values. This metric helps understand how many distinct batches will be created during the transformation flow execution on HANA.

-   `FLATTEN_OPERATOR_COUNT`

    Shows if a Flatten operator is used in the transformation flow. The value is always set to `1` becuase there can't be more than one Flatten operator per transformation flow. See [Creating a Flatten Operator](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/34f48faf744a429f9db581e5b43b920a.html "Learn how to create a Flatten operator in Apache Spark transformation flows to simplify complex star-schema data models. The operator automatically joins tables to create flattened tables for machine learning, AI, and analytics use cases.") :arrow_upper_right:

-   `EXECUTION_MODE`

    The "Run Mode" is defined in the settings for a transformation flow run: 0 means "Performance-Optimized \(Recommended\)" and 1 means "Memory-Optimized". For more information about the "Run Mode", see [Change Transformation Flow Settings](change-transformation-flow-settings-f7da029.md).

-   `INCREMENTAL_AGGREGATION`

    Indicates whether incremental aggregation is enabled for the transformation flow. When enabled, aggregations are computed incrementally, which can improve performance for repeated runs on updated datasets.

-   `LOAD_TYPE`

    The load type for a transformation flow run. For more information about load types, see [Creating a Transformation Flow](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/f7161e6c20204672ac4a6d90c81762e4.html "Create a transformation flow to load data from one or more sources, apply transformations (such as a join), and output the result in a target table. You can load a full set of data from one or more sources to a target table. You can add local tables and views, Open SQL schema objects, and also remote tables located in BW Bridge spaces. You can also load delta changes (including deleted records) from one source table to a target table.") :arrow_upper_right:.

-   `PYTHON_MAX_BATCH_SIZE`

    Size of the largest batch processed during Python operator execution. It can help identify if there are unusually large batches, which may indicate data skew \(a situation where certain batches contain significantly more data than others\). Large batches can lead to performance bottlenecks, as they may take disproportionately longer to process compared to smaller batches.

-   `PYTHON_MIN_BATCH_SIZE`

    Size of the smallest batch processed during Python operator execution. It provides insight into the smallest unit of data being processed. Consistently small batches might indicate evenly distributed data or very fine-grained task partitioning.

-   `CURRENT_ACTIVE_RECORD_COUNT`

    The number of active records present in the target table\(s\) after the transformation flow run completes. This metric is useful for tracking data volume changes and validating the output of the transformation flow.

-   `PREVIOUS_ACTIVE_RECORD_COUNT`

    The number of active records present in the target table\(s\) before the transformation flow run begins. This metric is useful for comparing data volume before and after the transformation to validate changes.

-   `NUMBER_OF_BATCHES`

    The total number of batches created and processed during a HANA-based transformation flow run. This metric provides insight into how the data was partitioned and processed.

-   `RUN_FLAGGED_RECORD_COUNT`

    The number of records that were flagged during the transformation flow run, typically due to data quality issues, validation failures, or other exceptions. This metric helps monitor data quality and identify problem records.

-   `NUMBER_OF_RECORDS`

    The number of records written to the target table.

-   `OPERATORS_WITH_ERROR_STACK_COUNT` 

    The count of operators in the transformation flow that failed validation during the run. This metric helps identify operators that may have configuration issues or data quality problems.

-   `PYTHON_OPERATOR_COUNT`

    The total number of Python operators used in the transformation flow. Python operators allow custom data transformations using Python code.

-   `REMOTE_ACCESS` 

    Shows "true" if a remote access has been used when executing the transformation flow. This is possible only when the transformation flow consumes a BW Bridge object imported as remote table.

-   `REMOVE_DUPLICATE_OPERATOR_COUNT` 

    Shows if a Remove Duplicate operator is used in the transformation flow. The value indicates the number of Remove Duplicate operators present in the flow. See Creating a Remove Duplicate Operator.

-   `MEMORY_CONSUMPTION_MIB`

    The peak memory consumption \(in mebibytes\) for the SAP HANA database while running the transformation flow.

-   `SHARED_DELTA_SHARE_SOURCE_COUNT`

    The number of Delta Sharing source objects consumed by the transformation flow. Delta Sharing sources are external data sources shared through the Delta Sharing protocol.

-   `SHARED_DELTA_SHARE_SOURCE_VOLUME_IN_BYTES`

    The total data volume from all Delta Sharing source objects consumed during the transformation flow run.

-   `SHARED_LTF_SOURCE_COUNT`

    The number of shared local table sources stored in SAP HANA Data Lake Files consumed by the transformation flow.

-   `SHARED_REMOTE_DELTA_SHARING_CLIENT_SOURCE_COUNT`

    The number of remote Delta Sharing source objects consumed by the transformation flow. Remote Delta Sharing sources are external data sources accessed through remote connections.

-   `SHARED_HANA_SOURCE_COUNT`

    The total data volume from all shared SAP HANA source objects consumed during the transformation flow run.

-   `SHARED_HANA_SOURCE_VOLUME_IN_BYTES`

    The total data volume from all shared SAP HANA source objects consumed during the transformation flow run.

-   `SHARED_SOURCE`

    Indicates whether the transformation flow consumes shared objects as source tables. When "Yes", it means one or more source tables are shared objects rather than local tables.

-   `LOAD_UNIT_TARGET` 

    Target tables created in spaces with SAP HANA Cloud, SAP HANA database storage have the value *PAGE* if the selected storage is "Disk", or *COLUMN* if the selected storage is "In-Memory".

-   `CURRENT_TOTAL_TABLE_SIZE_IN_BYTES`

    The total amount of storage consumed by the target table\(s\) after the transformation flow run completes. This metric helps monitor storage utilization and plan capacity requirements.

-   `PYTHON_TOTAL_BATCHES` 

    Total number of batches processed in the given task. It provides insight into how many times the batch processing logic was ran. A high number of batches might indicate a large dataset, fine-grained batch sizes, or efficient parallel processing..

-   `TRUNCATE`

    Indicates whether the *Delete All Before Loading* option is used for the transformation flow run. For more information, see [Create or Add a Target Table to a Transformation Flow](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/0950746ab4444e5ca6a665ee1b0380a1.html "A transformation flow writes data to a target table. You can create a new target table or use an existing one.") :arrow_upper_right:.

-   `VIEW_TRANSFORM_STACK_SIZE (GRAPHICAL)` 

    The number of view transform operators created using the graphical editor in the transformation flow.

-   `VIEW_TRANSFORM_STACK_SIZE (SPARK_SQL)` 

    The number of view transform operators created using Spark SQL in the transformation flow.

-   `VIEW_TRANSFORM_STACK_SIZE (SQL)` 

    The number of view transform operators created using SQL statements in the transformation flow.

-   `VIEW_TRANSFORM_STACK_SIZE (SQL_SCRIPT)` 

    The number of view transform operators created using SQL Script in the transformation flow.


