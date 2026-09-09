<!-- loiobdff6b91cf4b44f895429c23566b3ea0 -->

# Local Table \(File\) Sources for Replication Flows

You can use local table \(file\) sources in a replication flow to replicate data from local table files to supported target connections. This allows you to reuse data that has already been loaded into SAP Datasphere without extracting it again from the original source system.



## Prerequisites

-   A local table \(file\) source must already exist in your SAP Datasphere space \(see [Creating a Local Table \(File\)](creating-a-local-table-file-d21881b.md)\).
-   The source local table \(file\) must not be a shared local table \(file\).
-   You must have the required privileges to create and run replication flows.
-   *Initial Only*load type is supported for all local table \(file\) sources. *Initial and Delta* and *Delta Only* are supported only if the source object has *Delta Capturing*enabled.
-   Local tables \(file\) that have deletion vectors enabled are supported as sources for replication flows.



## Supported Target Connections

You can replicate local table file sources to the following targets:

-   SAP Datasphere \(HDL\_FILES\)
-   Amazon S3
-   Google Cloud Storage
-   Azure Data Lake Storage Gen2
-   Secure File Transfer Protocol \(SFTP\)

    > ### Caution:  
    > Secure File Transfer Protocol \(SFTP\) does not support the load type *Delta Only*.

-   Google BigQuery



## Procedure

1.  Open the replication flow in its editor.
2.  Choose*Add Source Objects*.
3.  Select the *SAP Datasphere \(HDL\_FILES\)* connection.
4.  Browse or search for the Local Table File that you want to use as the source.
5.  Select the local table file and choose *Add Selection*.

