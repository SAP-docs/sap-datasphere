<!-- loioaf67fc6241d445e9b49ccd2f03d72f9e -->

# Snowflake Sources for Replication Flows

You can use Snowflake as a source connection in replication flows to replicate data into supported targets. This feature uses the Connectivity Framework and supports the *Initial Only* load type.



## Prerequisites

-   Make sure you have created a Snowflake connection in Connection Management and that it is available in your space. For more information, see [Snowflake Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/d9ead8bb44ac456d99a141b4e3f5e973.html "Use the connection to connect to and access data from a Snowflake database.") :arrow_upper_right:
-   Only standard tables with primary keys and hybrid tables are supported \(Views are not supported\). Ensure that the defined primary keys comply with Snowflake constraints to avoid replication flow failures. For more information, refer to the Snowflake documentation.
-   GCP regional endpoints are not supported.
-   Only the *Initial Only* load type is supported. *Initial and Delta* and *Delta Only* load types are not supported.



## Replicating Source Objects Without Primary Keys

Replicating source objects without a primary key is not supported. Only source objects that have a primary key defined can be used as source objects in a replication flow.

> ### Note:  
> Only standard tables with primary keys and hybrid tables are supported \(Views are not supported\). Ensure that the defined primary keys comply with Snowflake constraints to avoid replication flow failures. For more information, refer to the Snowflake documentation.



<a name="loioaf67fc6241d445e9b49ccd2f03d72f9e__section_data_types"/>

## Data Types

The following table shows how Snowflake source data types are mapped to internal data types.


<table>
<tr>
<th valign="top">

Snowflake Source

</th>
<th valign="top">

SAP Datasphere

</th>
</tr>
<tr>
<td valign="top">

ARRAY

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

BINARY

</td>
<td valign="top">

varbinary\(8388608\)

</td>
</tr>
<tr>
<td valign="top">

BINARY\(n\), 1<=n<=5000

</td>
<td valign="top">

binary\(n\)

</td>
</tr>
<tr>
<td valign="top">

BINARY\(n\), n \> 5000

</td>
<td valign="top">

varbinary\(n\)

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

BYTEINT

</td>
<td valign="top">

varbinary\(8,0\)

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

CHAR VARYING\(n\), 1<=n<=5000

</td>
<td valign="top">

string\(n\)

</td>
</tr>
<tr>
<td valign="top">

CHARACTER\(n\), 1<=n<=5000

</td>
<td valign="top">

string\(n\)

</td>
</tr>
<tr>
<td valign="top">

CHARACTER VARYING\(n\), 1<=n<=5000

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

date

</td>
</tr>
<tr>
<td valign="top">

DATETIME

</td>
<td valign="top">

timestamp

</td>
</tr>
<tr>
<td valign="top">

DECIMAL\(p,s\)

</td>
<td valign="top">

varbinary\(p,s\)

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

DOUBLE PRECISION

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

FLOAT4

</td>
<td valign="top">

float32

</td>
</tr>
<tr>
<td valign="top">

FLOAT8

</td>
<td valign="top">

float64

</td>
</tr>
<tr>
<td valign="top">

GEOGRAPHY

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

GEOMETRY

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

INT

</td>
<td valign="top">

varbinary\(38,0\)

</td>
</tr>
<tr>
<td valign="top">

INTEGER

</td>
<td valign="top">

varbinary\(38,0\)

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

NCHAR VARYING\(n\), 1<=n<=5000

</td>
<td valign="top">

string\(n\)

</td>
</tr>
<tr>
<td valign="top">

NUMBER

</td>
<td valign="top">

varbinary\(38,0\)

</td>
</tr>
<tr>
<td valign="top">

NUMBER\(p,s\)

</td>
<td valign="top">

varbinary\(p,s\)

</td>
</tr>
<tr>
<td valign="top">

NUMERIC\(p,s\)

</td>
<td valign="top">

varbinary\(p,s\)

</td>
</tr>
<tr>
<td valign="top">

NVARCHAR

</td>
<td valign="top">

string

</td>
</tr>
<tr>
<td valign="top">

NVARCHAR\(n\), 1<=n<=5000

</td>
<td valign="top">

string\(n\)

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

OBJECT

</td>
<td valign="top">

Not Supported

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

SMALLINT

</td>
<td valign="top">

varbinary\(38,0\)

</td>
</tr>
<tr>
<td valign="top">

STRING

</td>
<td valign="top">

string

</td>
</tr>
<tr>
<td valign="top">

STRING\(n\), 1<=n<=5000

</td>
<td valign="top">

string\(n\)

</td>
</tr>
<tr>
<td valign="top">

STRING\(n\), n \> 5000

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

TEXT

</td>
<td valign="top">

string

</td>
</tr>
<tr>
<td valign="top">

TEXT\(n\), 1<=n<=5000

</td>
<td valign="top">

string\(n\)

</td>
</tr>
<tr>
<td valign="top">

TEXT\(n\), n \> 5000

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

TIMESTAMP

</td>
<td valign="top">

timestamp

</td>
</tr>
<tr>
<td valign="top">

TIMESTAMP\_LTZ

</td>
<td valign="top">

timestamp

</td>
</tr>
<tr>
<td valign="top">

TIMESTAMP\_NTZ

</td>
<td valign="top">

timestamp

</td>
</tr>
<tr>
<td valign="top">

TIMESTAMP\_TZ

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

varbinary\(38,0\)

</td>
</tr>
<tr>
<td valign="top">

VARBINARY

</td>
<td valign="top">

varbinary\(8388608\)

</td>
</tr>
<tr>
<td valign="top">

VARBINARY\(n\), 1<=n<=5000

</td>
<td valign="top">

binary\(n\)

</td>
</tr>
<tr>
<td valign="top">

VARBINARY\(n\), n \> 5000

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

VARCHAR

</td>
<td valign="top">

string

</td>
</tr>
<tr>
<td valign="top">

VARCHAR\(n\), 1<=n<=5000

</td>
<td valign="top">

string\(n\)

</td>
</tr>
<tr>
<td valign="top">

VARCHAR\(n\), n \> 5000

</td>
<td valign="top">

Not Supported

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

VARIANT

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

VECTOR

</td>
<td valign="top">

Not Supported

</td>
</tr>
</table>

