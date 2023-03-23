<!-- loiof918d0dc3a424e83b0107e2048e46aac -->

# Using a Cloud Storage As the Target

Running a replication flow with a cloud storage \(Data Lake Files from SAP HANA Cloud, data lake\) as the target creates various files and structures.

If you use Data Lake Files as the target, the system proceeds as follows:

Upon completion of the initial load, the system writes a `_SUCCESS` file. Downstream applications that can access the object store directly can use this file to verify that the replication completed successfully without having to check the replication flow status.

The `.sap.partfile.metadata` objects include metadata information for the replication object. It exists in the root of each data file directory and is created and referenced as part of replication flow processing. Additionally, you can leverage these objects for interpreting and processing the data files.

The replication flow creates multiple files \(<code>part-*.<i class="varname">&lt;extension&gt;</i></code>\) during initial and delta loading. The number and size of these files depends on the source table size and structure as well as change frequency \(during delta loading\).

Each file contains the source columns as defined in the mapping for the replication object in the replication flow. The system appends the following columns:

-   *\_\_operation\_type*: Identifies the type of target row:
    -   *L*: Written as part of the initial load.
    -   *I*: After the initial load completed, new source row added.
    -   *U*: After the initial load completed, update to a source row.
    -   *X*: After the initial load completed, source row deleted. The only target columns to contain data for this operation code are those that reflect the source key columns. All other target columns are empty.

-   *\_\_sequence\_number*: An integer value that reflects the sequential order of the delta row in relation to other deltas. This column is empty for initial load rows and is not populated for all source systems \(for example, ABAP\).
-   *\_\_timestamp*: The UTC date and time the system wrote the row.

