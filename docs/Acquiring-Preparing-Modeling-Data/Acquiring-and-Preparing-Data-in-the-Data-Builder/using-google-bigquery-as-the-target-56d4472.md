<!-- loio56d4472a0e1f44d58e07ca26ab666328 -->

# Using Google BigQuery As the Target

If you use Google BigQuery as the target for your replication flow, you need to consider the following additional specifics and conditions.

> ### Note:  
> You can only use a non-SAP target for a replication flow if your admin has assigned capacity units to Premium Outbound Integration. For more information, see [Configure the Size of Your SAP Datasphere Tenant](https://help.sap.com/docs/SAP_DATASPHERE/9f804b8efa8043539289f42f372c4862/33f8ef4ec359409fb75925a68c23ebc3.html).

This topic contains the following sections:

-   [General Properties](using-google-bigquery-as-the-target-56d4472.md#loio56d4472a0e1f44d58e07ca26ab666328__section_ReplFlow_GBQ_General) 

-   [Target Tables](using-google-bigquery-as-the-target-56d4472.md#loio56d4472a0e1f44d58e07ca26ab666328__section_ReplFlow_GBQ_TargetTables) 

-   [Target Columns](using-google-bigquery-as-the-target-56d4472.md#loio56d4472a0e1f44d58e07ca26ab666328__section_ReplFlow_GBQ_TargetColumns) 

-   [Data Types](using-google-bigquery-as-the-target-56d4472.md#loio56d4472a0e1f44d58e07ca26ab666328__section_ReplFlow_GBQ_DataTypes) 

-   [Primary Key](using-google-bigquery-as-the-target-56d4472.md#loio56d4472a0e1f44d58e07ca26ab666328__section_ReplFlow_GBQ_PrimaryKey) 

-   [SQL Statement](using-google-bigquery-as-the-target-56d4472.md#loio56d4472a0e1f44d58e07ca26ab666328__section_ReplFlow_GBQ_SQL) 




<a name="loio56d4472a0e1f44d58e07ca26ab666328__section_ReplFlow_GBQ_General"/>

## General Properties

The system always uses **write mode** *Append*.

The *Truncate* setting is not available.



<a name="loio56d4472a0e1f44d58e07ca26ab666328__section_ReplFlow_GBQ_TargetTables"/>

## Target Tables

Target table names may only contain the following special characters:

-   Hyphen \(-\)

-   Underscore \(\_\)

-   Space \( \)


The maximum length for target column names is 300 characters.

If the **target structure already exists** in Google BigQuery, you cannot make changes such as renaming a column or changing a data type in SAP Datasphere. You need to do this directly in Google BigQuery.



<a name="loio56d4472a0e1f44d58e07ca26ab666328__section_ReplFlow_GBQ_TargetColumns"/>

## Target Columns

The system automatically adds the following columns to the **schema of the target table**:

-   OPERATION\_FLAG

-   IS\_DELETED

-   RECORDSTAMP


These columns are needed to capture changes in the source so that they can be replicated to the target, and you cannot change their names or settings.

In the following cases, target column names have to be changed so that they can be used for replication into Google BigQuery. You can change the names for the relevant target columns manually or choose *Auto-Projection*.

-   If a target column has the same name as one of the columns for change data capturing, the target column has to be renamed. Auto-Projection does this by adding the prefix AUTOPREFIX\_ to the name of the target column, for example AUTOPREFIX\_RECORDSTAMP.

-   Some characters, such as slash \(/\), cannot be used in column names in Google BigQuery. If a target column name contains any of these characters, Auto-Projection replaces the unallowed characters with an underscore \(\_\).

-   Some column name prefixes are reserved within Google BigQuery, for example \_TABLE\_, \_FILE\_, or \_PARTITION\_. If a target column name contains any of these prefixes, Auto-Projection adds AUTOPREFIX\_ in front of the existing name.




<a name="loio56d4472a0e1f44d58e07ca26ab666328__section_ReplFlow_GBQ_DataTypes"/>

## Data Types

Google BigQuery does not support the data types DECFLOAT16, DECFLOAT34 and UINT64. The system automatically converts DECFLOAT16 and DECFLOAT34 into DECIMAL\(38,9\) and UINT64 into DECIMAL\(20,0\). The first value in brackets is the precision \(total number of digits\), the second one is the scale \(number of digits after the decimal point\).

For the DECFLOAT data types, the following conditions apply:

-   Precision can be between 38 and 77.

-   Scale can be between 9 and 38.

-   Precision minus scale must be 29 or larger.

-   By default, values that are too large are clamped in accordance with the maximum values for the respective target data type.

    If you don't want this, you can deactivate clamping for individual replication objects \(by deselecting *Clamp Decimal Floating-Point Data Type* in the *Details* side panel\) or for all objects in the replication flow \(by deselecting *Clamp Decimal Floating-Point Data Type* in the target settings\). If you do so, and if there are values that are too large, the replication fails and you get an error message informing you about the issue.


For data type UINT64, the number of digits before the decimal point \(precision minus scale\) must be 20 or greater.



<a name="loio56d4472a0e1f44d58e07ca26ab666328__section_ReplFlow_GBQ_PrimaryKey"/>

## Primary Key

A **primary key** can be created in Google BigQuery if the following prerequisites are met:

-   There are no more than **16 key columns**.

-   All key columns have one of the following **Google BigQuery data types**:

    -   BIGNUMERIC

    -   BOOLEAN

    -   DATE

    -   DATETIME

    -   INT64

    -   NUMERIC

    -   STRING

    -   TIMESTAMP



If either of these prerequisites is not met and you still run a replication flow, **none** of the columns in the target gets defined as a primary key column.



<a name="loio56d4472a0e1f44d58e07ca26ab666328__section_ReplFlow_GBQ_SQL"/>

## SQL Statement

You can view and copy the **SQL Create Table statement** of a replication object so that you can modify and run it directly in Google BigQuery. This can be useful, for example, if you want to change partitions and clusters for a new target object. To do so, choose View SQL Create Table Statement or Copy SQL Create Table Statement from the context menu for the relevant target object.

