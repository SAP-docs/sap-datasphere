<!-- loiob42fa5b6f4e04a9491efa9bf7dab0929 -->

# Metrics for Transformation Flows

View metrics for completed transformation flow runs.

Metrics provide the record count for source and target tables used in the flow. You can view the following metrics for a completed transformation flow run:

-   `LOAD_TYPE`

    The load type for a transformation flow run. For more information about load types, see [Creating a Transformation Flow](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/f7161e6c20204672ac4a6d90c81762e4.html "Create a transformation flow to load data from one or more sources, apply transformations (such as a join), and output the result in a target table. You can load a full set of data from one or more sources to a target table. You can add local tables and views, Open SQL schema objects, and also remote tables located in BW Bridge spaces. You can also load delta changes (including deleted records) from one source table to a target table.") :arrow_upper_right:.

-   `TRUNCATE`

    Indicates whether the *Delete All Before Loading* option is used for the transformation flow run. For more information, see [Create or Add a Target Table to a Transformation Flow](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/0950746ab4444e5ca6a665ee1b0380a1.html "A transformation flow writes data to a target table. You can create a new target table or use an existing one.") :arrow_upper_right:.

-   `REMOTE_ACCESS` 

    Shows "true" if a remote access has been used when executing the transformation flow. This is possible only when the transformation flow consumes a BW Bridge object imported as remote table.

-   `NUMBER_OF_RECORDS`

    The number of records written to the target table.

-   `MEMORY_CONSUMPTION_MIB`

    The peak memory consumption \(in mebibytes\) for the SAP HANA database while running the transformation flow.

-   `RUNTIME`

    Runtime is used to run the transformation flow. It can be HANA \(for a transformation flow in a space with Storage Type SAP HANA Database \(disk and In-Memory\)\) or SPARK \(for transformation flow in a space with Storage Type SAP HANA Data Lake Files\).

-   `LOAD_UNIT_TARGET` 

    Target tables created in spaces with SAP HANA Cloud, SAP HANA database storage have the value *PAGE* if the selected storage is “Disk”, or *COLUMN* if the selected storage is “In-Memory”.

-   `EXECUTION_MODE` 

    The “Run Mode” is defined in the settings for a transformation flow run: 0 means “Performance-Optimized \(Recommended\)” and 1 means “Memory-Optimized”. For more information about the "Run Mode", see [Change the Run Mode for a Transformation Flow](change-the-run-mode-for-a-transformation-flow-f7da029.md).

-   `VIEW TRANSFORM STACK SIZE ACCOUNT`

    The number of view transform nodes inside the transformation flow.

-   `SPARK_RESOURCE_ID`

    ID of the job used to run the transformation flow on an Apache Spark runtime. This ID must be provided to the SAP support to retrieve and analyze the jobs, and identify the cause of errors.

-   `PYTHON_TOTAL_BATCHES`

    Total number of batches processed in the given task. It provides insight into how many times the batch processing logic was executed. A high number of batches might indicate a large dataset, fine-grained batch sizes, or efficient parallel processing.

-   `PYTHON_MAX_BATCH_SIZE`

    Size of the largest batch processed. It can help identify if there are unusually large batches, which may indicate data skew \(a situation where certain batches contain significantly more data than others\). Large batches can lead to performance bottlenecks, as they may take disproportionately longer to process compared to smaller batches.

-   `PYTHON_MIN_BATCH_SIZE`

    Size of the smallest batch processed. It provides insight into the smallest unit of data being processed. Consistently small batches might indicate evenly distributed data or very fine-grained task partitioning.

-   `PYTHON_AVG_BATCH_SIZE`

    Average size of all batches. It gives a global view of the typical batch size. Comparing this metric against the minimum and maximum batch sizes can help understand the variance in batch sizes. If the average batch size is significantly different from the minimum and maximum, it might suggest inconsistent batch sizing and potential data skew.


