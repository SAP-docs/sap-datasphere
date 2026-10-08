<!-- loio54bbb56eabf44bb382adb615e0299a73 -->

# Oracle Sources for Replication Flows

You can use Oracle as a source connection in replication flows to replicate data into supported targets. This connection supports the *Initial Only*, *Initial and Delta*, and *Delta Only* load types.



## Prerequisites

-   You have created an Oracle connection in Connection Management and it is available in your space.
-   The following Oracle versions are supported: Oracle 12c, Oracle 18c, and Oracle 19c.
-   Only tables with primary keys are supported as replication sources.
-   Initial Only, Initial and Delta, and Delta Only load types are supported.



## Restrictions

-   Views and tables without a primary key cannot be added as source objects.
-   Connections through load balancers are not supported.
-   Scan listeners are not supported.



## Replicating Source Objects Without Primary Keys



## Data Types

The following table shows how Oracle source data types are mapped to internal data types. Data types that are not supported cannot be replicated.


<table>
<tr>
<th valign="top">

Oracle Source

</th>
<th valign="top">

SAP Datasphere

</th>
</tr>
<tr>
<td valign="top">

BINARY\_DOUBLE

</td>
<td valign="top">

float64

</td>
</tr>
<tr>
<td valign="top">

BINARY\_FLOAT

</td>
<td valign="top">

float32

</td>
</tr>
<tr>
<td valign="top">

BLOB

</td>
<td valign="top">

binary

</td>
</tr>
<tr>
<td valign="top">

CHAR\(n\), 1<=n<=5000

</td>
<td valign="top">

string\(n\)

</td>
</tr>
<tr>
<td valign="top">

CLOB

</td>
<td valign="top">

string

</td>
</tr>
<tr>
<td valign="top">

DATE

</td>
<td valign="top">

timestamp

</td>
</tr>
<tr>
<td valign="top">

FLOAT

</td>
<td valign="top">

float64

</td>
</tr>
<tr>
<td valign="top">

LONG

</td>
<td valign="top">

string

</td>
</tr>
<tr>
<td valign="top">

LONG RAW

</td>
<td valign="top">

binary

</td>
</tr>
<tr>
<td valign="top">

NCHAR\(n\), 1<=n<=5000

</td>
<td valign="top">

string\(n\)

</td>
</tr>
<tr>
<td valign="top">

NCLOB

</td>
<td valign="top">

string

</td>
</tr>
<tr>
<td valign="top">

NUMBER

</td>
<td valign="top">

decfloat34

</td>
</tr>
<tr>
<td valign="top">

NUMBER\(p,s\)

</td>
<td valign="top">

decimal\(p,s\)

</td>
</tr>
<tr>
<td valign="top">

NVARCHAR2\(n\), 1<=n<=5000

</td>
<td valign="top">

string\(n\)

</td>
</tr>
<tr>
<td valign="top">

RAW\(n\), 1<=n<=5000

</td>
<td valign="top">

binary\(n\)

</td>
</tr>
<tr>
<td valign="top">

TIMESTAMP

</td>
<td valign="top">

timestamp

</td>
</tr>
<tr>
<td valign="top">

TIMESTAMP WITH LOCAL TIME ZONE

</td>
<td valign="top">

timestamp

</td>
</tr>
<tr>
<td valign="top">

TIMESTAMP WITH TIME ZONE

</td>
<td valign="top">

timestamp

</td>
</tr>
<tr>
<td valign="top">

VARCHAR2\(n\), 1<=n<=5000

</td>
<td valign="top">

string\(n\)

</td>
</tr>
<tr>
<td valign="top">

XMLTYPE

</td>
<td valign="top">

Not Supported

</td>
</tr>
</table>

> ### Note:  
> Oracle `DATE` columns map to `timestamp`, not `date`, as Oracle date values include time information. All timestamp values are normalized to UTC.

