<!-- loio12b6825ac6d34db9902460f665cfcb88 -->

# Data Lake API

SAP Datasphere provides two procedures to access SAP HANA Cloud, data lake.



The following procedures are available in the schema `DWC_GLOBAL`:

-   ```
"DWC_GLOBAL"."DATA_LAKE_EXECUTE" ( IN STMT NCLOB )
```

    This procedure is used to execute statements in data lake. It's a wrapper procedure around the data lake procedure `REMOTE_EXECUTE`. This enables you to create or drop tables in data lake, or to load data from files.

-   ```
"DWC_GLOBAL"."DATA_LAKE_CREATE_VIRTUAL_TABLE"
                      (
                       IN VIRTUAL_TABLE_NAME NVARCHAR(256),
                       IN DATA_LAKE_TABLE_NAME NVARCHAR(256),
                       IN TARGET_SCHEMA_SYS BOOLEAN DEFAULT false
                      ).
```

-   This procedure provides the option to create SAP HANA virtual tables in the open SQL schema that refer to objects in data lake. These virtual tables are used to query data in the data lake. For more information see [Data Lake SQL Statements Versus SAP HANA Cloud SQL Statements](https://help.sap.com/viewer/071308868de34b289a6b1553b8cc37b9/cloud/en-US/f23b60ec161a46f9b906eac15c5a3b95.html).

    The procedure can also be used to access system views of data lake in schema `SYS`. The optional `IN` parameter `IN_TARGET_SCHEMA_SYS` needs to be to true to create a virtual table on a data lake system view. For more information see [System Views \[Data Lake\]](https://help.sap.com/viewer/9f153559aeb5471d8aff9384cdc500db/cloud/en-US/92e2e6c466d844e0b0e961069aa3b8d7.html).

    Virtual tables can be dropped directly using `DROP TABLE` <virtual\_table\_name\> syntax.

    For more information see [Query Data Lake Data](https://help.sap.com/viewer/071308868de34b289a6b1553b8cc37b9/cloud/en-US/9c80f123c5d74f71a9f536682f2f479c.html).




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

