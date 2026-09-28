<!-- loio4fe921866ee44d6e8bb13d92f378d3a2 -->

# MySQL Sources for Replication Flows

You can use MySQL connections as sources in replication flows to replicate data into supported targets. This feature uses the Connectivity Framework and supports the Initial Only load type.



## Prerequisites

-   You have created a MySQL connection in Connection Management and it is available in your space.
-   Only tables that contain a primary key are supported as replication sources.
-   Only the Initial Only load type is supported. Initial and Delta and Delta Only load types are not supported.



## Restrictions

-   Source settings are not available for this source type.
-   Custom parameters are not supported.
-   Connections through load balancers are not supported.



## Partitioning Timeouts for Large MySQL Tables

If a partitioning timeout occurs, try the following in order:

-   Stale table statistics: MySQL statistics in `information_schema` can take time to update. Stale statistics lead to incorrect group calculations and a partitioning timeout. Run the following statement, then rerun the replication `ANALYZE TABLE <tableIdentifier>;`flow:


-   Persistent timeout – InnoDB tuning: If the timeout persists, review the following MySQL parameters to ensure the index fits in memory and I/O is tuned for sequential large-table reads:


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Recommended Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    `innodb_buffer_pool_size`
    
    </td>
    <td valign="top">
    
    70–80% of RAM \(dedicated server\); at minimum, twice the index size
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `innodb_buffer_pool_instances`
    
    </td>
    <td valign="top">
    
    1 per GB of buffer pool; maximum 8
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `innodb_read_io_threads`
    
    </td>
    <td valign="top">
    
    8 for SSD; 16 or more for NVMe \(restart required\)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `innodb_read_ahead_threshold`
    
    </td>
    <td valign="top">
    
    0 for sequential replication scans
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `read_rnd_buffer_size`
    
    </td>
    <td valign="top">
    
    32 MB for large table reads
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `max_connections`
    
    </td>
    <td valign="top">
    
    Set conservatively; each idle connection uses approximately 1 MB
    
    </td>
    </tr>
    </table>
    

-   Continued DEADLINE\_EXCEEDED errors – covering index: On very large tables, create the `SAP_MYSQL_REPLICATION_PK` index to allow the connector to scan only the primary key columns instead of the full clustered index. The index must cover exactly the primary key columns and nothing else:`-- Replace pk1, pk2, ... with the actual primary key column names in declaration order. CREATE INDEX SAP_MYSQL_REPLICATION_PK ON `schema`.`table` (`pk1`, `pk2`, ...);`

    -   Index creation runs online but takes time proportional to table size. Monitor progress with:`SELECT STAGE, WORK_COMPLETED, WORK_ESTIMATED FROM performance_schema.events_stages_current;`

    -   After creation, verify the index is used:`EXPLAIN SELECT `pk1`, ..., `pkN` FROM `schema`.`table` ORDER BY `pk1`, ..., `pkN` LIMIT 1 OFFSET 1000000; -- Expected: key = SAP_MYSQL_REPLICATION_PK, Extra = Using index`

    -   Verify the index size fits within your `innodb_buffer_pool_size`:`SELECT INDEX_NAME, ROUND(stat_value * @@innodb_page_size / 1024 / 1024 / 1024, 2) AS size_gb FROM mysql.innodb_index_stats WHERE database_name = '<schema>' AND table_name = '<table>' AND stat_name = 'size';`


    > ### Note:  
    > `SAP_MYSQL_REPLICATION_PK` is only applied when no filters are set, or when filters reference PK columns only. If any filter references a non-PK column, MySQL must perform a back-lookup to the original clustered index for every row, making `SAP_MYSQL_REPLICATION_PK` counterproductive. In this case, the index is not applied:
    > 
    > -   No filter: index is "applied
    > -   Filter on PK columns only \(for example, `WHERE pk1 = 'X'`\): index is "applied"
    > -   Filter on a non-PK column \(for example, `WHERE STATUS = 'A'`\): index is "not applied"
    > -   Filter on both PK and non-PK columns \(for example, `WHERE STATUS = 'A' AND pk1 = 'X'`\): index is "not applied"




## Data Types

The following table shows how MySQL source data types are mapped to internal data types. Data types that are not supported cannot be replicated.


<table>
<tr>
<th valign="top">

MySQL Data Type

</th>
<th valign="top">

SAP Datasphere

</th>
</tr>
<tr>
<td valign="top">

BIGINT

</td>
<td valign="top">

int64

</td>
</tr>
<tr>
<td valign="top">

BIGINT UNSIGNED

</td>
<td valign="top">

uint64

</td>
</tr>
<tr>
<td valign="top">

BINARY\(n\), VARBINARY\(n\), 1≤n≤5000

</td>
<td valign="top">

binary\(n\)

</td>
</tr>
<tr>
<td valign="top">

BINARY\(n\), VARBINARY\(n\), n \> 5000

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

BIT\(1\)

</td>
<td valign="top">

bool

</td>
</tr>
<tr>
<td valign="top">

BIT\(n \> 1\)

</td>
<td valign="top">

binary\(n\)

</td>
</tr>
<tr>
<td valign="top">

BLOB, MEDIUMBLOB, LONGBLOB

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

BOOL, BOOLEAN

</td>
<td valign="top">

int8

</td>
</tr>
<tr>
<td valign="top">

CHAR\(n\), NCHAR\(n\), 1≤n≤5000

</td>
<td valign="top">

string\(n\)

</td>
</tr>
<tr>
<td valign="top">

CHAR\(n\), NCHAR\(n\), n \> 5000

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

DATE, YEAR

</td>
<td valign="top">

date

</td>
</tr>
<tr>
<td valign="top">

DECIMAL \(unknown precision/scale\)

</td>
<td valign="top">

decfloat34

</td>
</tr>
<tr>
<td valign="top">

DECIMAL\(p,s\)

</td>
<td valign="top">

decimal\(p,s\)

</td>
</tr>
<tr>
<td valign="top">

DOUBLE, REAL

</td>
<td valign="top">

float64

</td>
</tr>
<tr>
<td valign="top">

ENUM, SET

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

FLOAT

</td>
<td valign="top">

float32

</td>
</tr>
<tr>
<td valign="top">

GEOMETRY, GEOMETRYCOLLECTION, LINESTRING, MULTILINESTRING, MULTIPOINT, MULTIPOLYGON, POINT, POLYGON

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

INT, MEDIUMINT

</td>
<td valign="top">

int32

</td>
</tr>
<tr>
<td valign="top">

INT UNSIGNED, MEDIUMINT UNSIGNED

</td>
<td valign="top">

uint64

</td>
</tr>
<tr>
<td valign="top">

JSON

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

SMALLINT

</td>
<td valign="top">

int16

</td>
</tr>
<tr>
<td valign="top">

SMALLINT UNSIGNED

</td>
<td valign="top">

uint64

</td>
</tr>
<tr>
<td valign="top">

TEXT, MEDIUMTEXT, LONGTEXT, 1≤n≤5000

</td>
<td valign="top">

string\(n\)

</td>
</tr>
<tr>
<td valign="top">

TEXT, MEDIUMTEXT, LONGTEXT, n \> 5000

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

TIME

</td>
<td valign="top">

time

</td>
</tr>
<tr>
<td valign="top">

TIMESTAMP\(n\), DATETIME\(n\)

</td>
<td valign="top">

timestamp

</td>
</tr>
<tr>
<td valign="top">

TINYBLOB

</td>
<td valign="top">

binary\(n\)

</td>
</tr>
<tr>
<td valign="top">

TINYINT

</td>
<td valign="top">

int8

</td>
</tr>
<tr>
<td valign="top">

TINYINT UNSIGNED

</td>
<td valign="top">

uint8

</td>
</tr>
<tr>
<td valign="top">

TINYTEXT

</td>
<td valign="top">

string\(n\)

</td>
</tr>
<tr>
<td valign="top">

VARCHAR\(n\), NVARCHAR\(n\), 1≤n≤5000

</td>
<td valign="top">

string\(n\)

</td>
</tr>
<tr>
<td valign="top">

VARCHAR\(n\), NVARCHAR\(n\), n \> 5000

</td>
<td valign="top">

Not Supported

</td>
</tr>
</table>

