<!-- loio12c45eb2659f4069b29ef4d69bdd9070 -->

# SAP Datasphere Targets

If you use the local repository \(SAP Datasphere\) as the target for your replication flow, you need to consider additional specifics and conditions.

The **target container** is automatically defined as the space you are in and cannot be changed.

The **target object** is always a local table. By default, the system creates a new target local table \(based on the name and structure of the corresponding source table\) when you deploy the replication flow. Alternatively, you can use an existing local table as the target. To do so, choose *Map to Existing Target Object* \(from the*Additional Options* menu for the target object\).

SAP Datasphere supports two types of local tables: local tables stored on disk or in-memory and local table \(file\). For more information about these two types and their differences, see [Creating a Local Table \(File\)](creating-a-local-table-file-d21881b.md).



<a name="loio12c45eb2659f4069b29ef4d69bdd9070__section_ojz_2lr_zcc"/>

## Local Table As Target

For load type *Initial and Delta*, we recommend using a target table that supports delta capturing. For background information, see [Capturing Delta Changes in Your Local Table](capturing-delta-changes-in-your-local-table-154bdff.md).

For information about supported data types, see [Capturing Delta Changes in Your Local Table](capturing-delta-changes-in-your-local-table-154bdff.md).



<a name="loio12c45eb2659f4069b29ef4d69bdd9070__section_yxy_glr_zcc"/>

## Local Table \(File\) As Target

> ### Note:  
> Using a local table \(file\) as the target for a replication flow is only possible in a file space. For more information, see [Creating a Local Table \(File\)](creating-a-local-table-file-d21881b.md).

The following **sources** are **not** supported:

-   Cloud storage providers, such as Amazon Simple Storage Service, Google Cloud Storage, or Microsoft Azure Data Lake Gen2

-   ABAP-based objects that do not have a primary key

-   Tables in which a column with data type `time` is defined as a primary key column

-   ABAP cluster tables


**Properties**:

-   **Delta capturing** is **activated** by default and cannot be switched off.

-   **Delete All Before Loading** is **deactivated** by default and cannot be switched on. To remove existing data from the target table, go to the table editor for your target table **before** running your replication flow and choose *Delete Data From Table*.

-   Only load type *Initial and Delta* can be used.

-   Clamping: By default, if there are values that are too large, the replication fails and you get an error message informing you about the issue. If you don't want this, you can activate clamping for individual replication objects \(by selecting *Clamp Decimal Floating-Point Data Type* in the side panel\) or for all objects in the replication flow \(by selecting *Clamp Decimal Floating-Point Data Type* in the target settings\). If you do so, values that are too large are clamped in accordance with the maximum values for the respective target data type.


**A target column name** can include alphanumeric characters and underscores \(\_\), but no special characters, and it cannot start with an underscore. If a target column name contains a special character, the system automatically replaces it with an underscore \(auto-projection\).

Columns that have the data type `decfloat16` or `decfloat34` are automatically converted to `decimal(38,6)`. You cannot add new target columns with data type `decfloat16` or `decfloat34`.

Columns that have the data type `uint64`are automatically converted to `decimal(20,0)`. You cannot add new columns with data type `uint64`.

Columns that have the data type `time` are **skipped**, that is, they don't get included in the target table.

For more information about supported data types, see [Data Types Supported By Local Tables \(File\)](data-types-supported-by-local-tables-file-2f39104.md).

