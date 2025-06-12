<!-- loio93d0b5d4faa24777a4b78513f7ed6172 -->

# Working with Data Lake

Assign a SAP Datasphere space to access and work with SAP HANA Cloud, data lake.



<a name="loio93d0b5d4faa24777a4b78513f7ed6172__prereq_bfs_q4q_dyb"/>

## Prerequisites

Before you can work with data lake, it must be enabled by selecting a storage size in *System* \> *Configuration* \> *Tenant Configuration* \(see [Configure the Size of Your SAP Datasphere Tenant](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/33f8ef4ec359409fb75925a68c23ebc3.html "Configure the size of your tenant by specifying resource sizes based on your business needs. Capacity Units (CU) are allocated to obtain storage and compute resources for your tenant.") :arrow_upper_right:.



## Context

You can assign a space that connects to data lake. Tables in the data lake can then be accessed via virtual tables in the open SQL schema. These tables can also be consumed in the *Data Builder*.

> ### Note:  
> -   Currently, DDL statements in your data lake are not audited.
> 
> -   For data flows, only APPEND \(UPSERT option not selected\) and TRUNCATE modes are supported. APPEND \(with UPSERT option selected\) and DELETE modes are not supported.



## Procedure

1.  Go to *Space Management*. As only one space can connect to the data lake, you should check first that no other space already has access to the data lake. To do so, you can choose the table layout and sort on the *Data Lake Access* column.

2.  Select the space that you want to give access to the data lake. Alternatively, you can create a dedicated space for the data lake.

3.  Under *Storage Assignment* select the check box *Use this space to access the data lake*. Even though the option is available for selection, it will not be taken into account if another space can already access the data lake.

4.  Click *Save*.

    You can now use your preferred SQL tool to create tables in data lake and access these tables via SAP HANA virtual tables in your open SQL schema. SAP Datasphere offers two stored procedures that you can use to easily create and access the tables. For more information and examples on the stored procedures see [Data Lake API](data-lake-api-12b6825.md).

5.  In your SQL tool, use the `"DWC_GLOBAL"."DATA_LAKE_EXECUTE" ( IN STMT NCLOB )` stored procedure in the schema `DWC_GLOBAL` to create tables in data lake. Please note, that the statements issued via this procedure are not audited.

6.  Then create SAP HANA virtual tables in your open SQL schema that refer to the tables in data lake. The virtual tables are used to query the tables in data lake.

    Use the following procedure to create a virtual table in your open SQL schema:

    ```
    "DWC_GLOBAL"."DATA_LAKE_CREATE_VIRTUAL_TABLE"
                                (
                                  IN VIRTUAL_TABLE_NAME NVARCHAR(256),
                                  IN DATA_LAKE_TABLE_NAME NVARCHAR(256),
                                  IN TARGET_SCHEMA_SYS BOOLEAN DEFAULT false
                                ).
    ```




<a name="loio93d0b5d4faa24777a4b78513f7ed6172__result_uqx_lcp_2mb"/>

## Results

You can then work with your virtual tables in the *Data Builder* by selecting the open SQL schema used for the data lake.



## Example

Creating a table in data lake:

```
CALL "DWC_GLOBAL"."DATA_LAKE_EXECUTE"('CREATE TABLE TABLE1 ( MY_ID INTEGER ) ');
```

Creating a virtual table in open SQL schema:

```
CALL "DWC_GLOBAL"."DATA_LAKE_CREATE_VIRTUAL_TABLE"
                      ( VIRTUAL_TABLE_NAME => 'TABLE1_VT',
                        DATA_LAKE_TABLE_NAME => 'TABLE1'
                      ) ;
```

Inserting a record in the table:

```
INSERT INTO table1_vt VALUES (2);
```

Selecting data from the virtual table:

```
SELECT * FROM table1_vt;
```

Dropping the virtual table:

```
DROP TABLE table1_vt;
```

Dropping the table in data lake:

```
CALL "DWC_GLOBAL"."DATA_LAKE_EXECUTE"('DROP TABLE TABLE1');
```

Accessing the system views via the virtual table:

```
CALL "DWC_GLOBAL"."DATA_LAKE_CREATE_VIRTUAL_TABLE"
                      ( VIRTUAL_TABLE_NAME => 'SYSTAB',
                        DATA_LAKE_TABLE_NAME => 'SYSTAB',
                        TARGET_SCHEMA_SYS => true
                      ) ;
```

For more information see [System Views in Data Lake Relational Engine \(SAP HANA DB-Managed\)](https://help.sap.com/docs/SAP_HANA_DATA_LAKE/a898e08b84f21015969fa437e89860c8/92e2e6c466d844e0b0e961069aa3b8d7.html).

