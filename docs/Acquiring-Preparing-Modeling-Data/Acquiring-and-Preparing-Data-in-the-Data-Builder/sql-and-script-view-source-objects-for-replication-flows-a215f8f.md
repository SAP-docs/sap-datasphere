<!-- loioa215f8f8257d4cf88a9ef927b8b101c5 -->

# SQL and Script View Source Objects for Replication Flows

You want to use an SQL or a Script view as a source object for your replication flow.

If you use an SQL view or a script view as a source object for your replication flow, you need to consider additional specifics and conditions.



<a name="loioa215f8f8257d4cf88a9ef927b8b101c5__section_znd_yys_3fc"/>

## Available Sources

SQL or Script views can be selected as source objects for the following connections only:

-   SAP HANA Cloud
-   SAP HANA On-premise
-   SAP Datasphere



<a name="loioa215f8f8257d4cf88a9ef927b8b101c5__section_vrh_gzs_3fc"/>

## Prerequisites

You must ensure to meet the following prerequisites to add SQL or script view as source objects:

-   The load type must be *Initial Only*. Other load types are currently not supported.
-   You must define a primary key for your view to allow the deployment. You can do it in the*Object Properties* panel, under *Source Schema Settings* \> *Configure Schema*.

    > ### Note:  
    > Define primary key columns that follow the primary key constraints \(value must be unique and not null\). Wrong settings will result in data inconsistency.

-   Your view must not contain parameters.



<a name="loioa215f8f8257d4cf88a9ef927b8b101c5__section_clj_1fr_kfc"/>

## Restrictions

The following views are not supported:

-   SQL views without a semantic primary key
-   SQL views with input parameters
-   SQL views based on remote tables
-   Other SAP HANA SQL views of type OLAP, JOIN, HIERARCHY, or CALC.



## Replicating Source Objects Without Primary Keys

If a source object does not have a primary key, you can still use it in a replication flow by configuring the primary key columns manually. The target table requires a primary key, so you must define which columns serve as the key before you deploy the replication flow. To configure the primary key columns:

1.  Select the relevant source object.
2.  In the properties panel, go to the *Source Schema Settings* section and choose *Configure Schema.*
3.  Mark the relevant columns as key columns.

The columns you select as the primary key must contain unique, non-null values. Incorrect settings result in data inconsistency.



## Data Types

The following table shows how SAP HANA SQL data types are mapped to internal data types.


<table>
<tr>
<th valign="top">

SAP HANA SQL Data Type

</th>
<th valign="top">

Internal Data Type

</th>
</tr>
<tr>
<td valign="top">

ALPHANUM\(n\)

</td>
<td valign="top">

string\(n\)

</td>
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

BOOLEAN

</td>
<td valign="top">

bool

</td>
</tr>
<tr>
<td valign="top">

CLOB, NCLOB

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

date

</td>
</tr>
<tr>
<td valign="top">

DECIMAL

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

DOUBLE

</td>
<td valign="top">

float64

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

FLOAT\(n\), 1≤n≤24

</td>
<td valign="top">

float32

</td>
</tr>
<tr>
<td valign="top">

FLOAT\(n\), 25≤n≤53

</td>
<td valign="top">

float64

</td>
</tr>
<tr>
<td valign="top">

INTEGER

</td>
<td valign="top">

int32

</td>
</tr>
<tr>
<td valign="top">

NVARCHAR\(n\)

</td>
<td valign="top">

string\(n\)

</td>
</tr>
<tr>
<td valign="top">

REAL

</td>
<td valign="top">

float32

</td>
</tr>
<tr>
<td valign="top">

SECONDDATE

</td>
<td valign="top">

timestamp

</td>
</tr>
<tr>
<td valign="top">

SHORTTEXT\(n\)

</td>
<td valign="top">

string\(n\)

</td>
</tr>
<tr>
<td valign="top">

SMALLDECIMAL

</td>
<td valign="top">

decfloat16

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

TIME

</td>
<td valign="top">

time

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

TINYINT

</td>
<td valign="top">

uint8

</td>
</tr>
<tr>
<td valign="top">

VARBINARY\(n\)

</td>
<td valign="top">

binary\(n\)

</td>
</tr>
<tr>
<td valign="top">

VARCHAR\(n\)

</td>
<td valign="top">

string\(n\)

</td>
</tr>
</table>

