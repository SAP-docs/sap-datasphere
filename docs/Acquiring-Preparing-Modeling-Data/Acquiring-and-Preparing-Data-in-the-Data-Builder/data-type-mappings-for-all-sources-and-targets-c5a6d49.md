<!-- loioc5a6d493793048049f01a804e96f6fc6 -->

# Data Type Mappings for All Sources and Targets

This topic contains the data type mapping tables for all replication flow source and target connections. For each source connection, the table shows how source data types are mapped to internal data types. For each target connection, the table shows how internal data types are mapped to target data types. Data types that cannot be replicated are marked as Not Supported.



## REST API Sources - Data Types

The following table shows how REST API source data types are mapped to internal data types. Data types that are not supported are skipped during replication.


<table>
<tr>
<th valign="top">

Source Data Type

</th>
<th valign="top">

SAP Datasphere

</th>
</tr>
<tr>
<td valign="top">

boolean

</td>
<td valign="top">

boolean

</td>
</tr>
<tr>
<td valign="top">

byte

</td>
<td valign="top">

uint8

</td>
</tr>
<tr>
<td valign="top">

date

</td>
<td valign="top">

date

</td>
</tr>
<tr>
<td valign="top">

datetime

</td>
<td valign="top">

timestamp

</td>
</tr>
<tr>
<td valign="top">

datetimeoffset

</td>
<td valign="top">

timestamp

</td>
</tr>
<tr>
<td valign="top">

decimal

</td>
<td valign="top">

decfloat34

</td>
</tr>
<tr>
<td valign="top">

decimal\(p,s\)

</td>
<td valign="top">

decimal\(p,s\)

</td>
</tr>
<tr>
<td valign="top">

double

</td>
<td valign="top">

float64

</td>
</tr>
<tr>
<td valign="top">

guid

</td>
<td valign="top">

string\(36\)

</td>
</tr>
<tr>
<td valign="top">

hana.ST\_GEOMETRY

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

hana.ST\_POINT

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

int16

</td>
<td valign="top">

int16

</td>
</tr>
<tr>
<td valign="top">

int32

</td>
<td valign="top">

int32

</td>
</tr>
<tr>
<td valign="top">

int64

</td>
<td valign="top">

int64

</td>
</tr>
<tr>
<td valign="top">

sbyte

</td>
<td valign="top">

uint8

</td>
</tr>
<tr>
<td valign="top">

single

</td>
<td valign="top">

float32

</td>
</tr>
<tr>
<td valign="top">

string \(size ≤ 5000\)

</td>
<td valign="top">

string\(size\)

</td>
</tr>
<tr>
<td valign="top">

string \(size \> 5000\)

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

string \(without size\)

</td>
<td valign="top">

string

</td>
</tr>
<tr>
<td valign="top">

time

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

timeofday

</td>
<td valign="top">

Not Supported

</td>
</tr>
</table>



## SAP HANA Cloud Data Lake File Sources - Data Types

The following table shows how SAP HANA Cloud, Data Lake Files source data types are mapped to internal data types. Data types that are not supported cannot be replicated.


<table>
<tr>
<th valign="top">

Source Data Type

</th>
<th valign="top">

SAP Datasphere

</th>
</tr>
<tr>
<td valign="top">

array

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

binary

</td>
<td valign="top">

binary\(5000\)

</td>
</tr>
<tr>
<td valign="top">

boolean

</td>
<td valign="top">

boolean

</td>
</tr>
<tr>
<td valign="top">

byte

</td>
<td valign="top">

uint8

</td>
</tr>
<tr>
<td valign="top">

date

</td>
<td valign="top">

date

</td>
</tr>
<tr>
<td valign="top">

decimal

</td>
<td valign="top">

decimal\(p,s\)

</td>
</tr>
<tr>
<td valign="top">

double

</td>
<td valign="top">

float64

</td>
</tr>
<tr>
<td valign="top">

float

</td>
<td valign="top">

float32

</td>
</tr>
<tr>
<td valign="top">

integer

</td>
<td valign="top">

int32

</td>
</tr>
<tr>
<td valign="top">

long

</td>
<td valign="top">

int64

</td>
</tr>
<tr>
<td valign="top">

map

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

short

</td>
<td valign="top">

int16

</td>
</tr>
<tr>
<td valign="top">

string

</td>
<td valign="top">

string\(5000\)

</td>
</tr>
<tr>
<td valign="top">

struct

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

timestamp

</td>
<td valign="top">

timestamp

</td>
</tr>
</table>



## Apache Kafka - Targets

The following table shows how internal data types are mapped to Apache Kafka target data types for both AVRO and JSON formats.


<table>
<tr>
<th valign="top">

SAP Datasphere

</th>
<th valign="top">

AVRO Data Type

</th>
<th valign="top">

JSON Data Type

</th>
</tr>
<tr>
<td valign="top">

binary

</td>
<td valign="top">

bytes

</td>
<td valign="top">

String \(base64-encoded\)

</td>
</tr>
<tr>
<td valign="top">

boolean

</td>
<td valign="top">

boolean

</td>
<td valign="top">

Boolean

</td>
</tr>
<tr>
<td valign="top">

date

</td>
<td valign="top">

int \(date\)

</td>
<td valign="top">

String \(YYYY-MM-DD\)

</td>
</tr>
<tr>
<td valign="top">

decimal\(p,s\)

</td>
<td valign="top">

bytes \(DECIMAL p,s\)

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

decfloat16

</td>
<td valign="top">

bytes \(DECIMAL 28,6\)

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

decfloat34

</td>
<td valign="top">

bytes \(DECIMAL 38,6\)

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

float32

</td>
<td valign="top">

float

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

float64

</td>
<td valign="top">

double

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

int8

</td>
<td valign="top">

int

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

int16

</td>
<td valign="top">

int

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

int32

</td>
<td valign="top">

int

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

int64

</td>
<td valign="top">

long

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

string

</td>
<td valign="top">

string

</td>
<td valign="top">

String

</td>
</tr>
<tr>
<td valign="top">

time

</td>
<td valign="top">

long \(timestamp-micros\)

</td>
<td valign="top">

String \(HH:MM:SS.NNNNNNNNNN\)

</td>
</tr>
<tr>
<td valign="top">

timestamp

</td>
<td valign="top">

long \(timestamp-micros\)

</td>
<td valign="top">

String \(YYYY-MM-DD HH:MM:SS.NNNNNNNNNN\)

</td>
</tr>
<tr>
<td valign="top">

uint8

</td>
<td valign="top">

int

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

uint64

</td>
<td valign="top">

bytes \(DECIMAL 20,0\)

</td>
<td valign="top">

Number

</td>
</tr>
</table>



## Confluent Kafka - Targets

The following table shows how internal data types are mapped to Confluent Kafka target data types for both AVRO and JSON formats.


<table>
<tr>
<th valign="top">

SAP Datasphere

</th>
<th valign="top">

AVRO Data Type

</th>
<th valign="top">

JSON Data Type

</th>
</tr>
<tr>
<td valign="top">

binary

</td>
<td valign="top">

bytes

</td>
<td valign="top">

String \(base64-encoded\)

</td>
</tr>
<tr>
<td valign="top">

boolean

</td>
<td valign="top">

boolean

</td>
<td valign="top">

Boolean

</td>
</tr>
<tr>
<td valign="top">

date

</td>
<td valign="top">

int \(date\)

</td>
<td valign="top">

String \(YYYY-MM-DD\)

</td>
</tr>
<tr>
<td valign="top">

decimal\(p,s\)

</td>
<td valign="top">

bytes \(DECIMAL p,s\)

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

decfloat16

</td>
<td valign="top">

bytes \(DECIMAL 28,6\)

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

decfloat34

</td>
<td valign="top">

bytes \(DECIMAL 38,6\)

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

float32

</td>
<td valign="top">

float

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

float64

</td>
<td valign="top">

double

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

int8

</td>
<td valign="top">

int

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

int16

</td>
<td valign="top">

int

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

int32

</td>
<td valign="top">

int

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

int64

</td>
<td valign="top">

long

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

string

</td>
<td valign="top">

string

</td>
<td valign="top">

String

</td>
</tr>
<tr>
<td valign="top">

time

</td>
<td valign="top">

long \(timestamp-micros\)

</td>
<td valign="top">

String \(HH:MM:SS.NNNNNNNNNN\)

</td>
</tr>
<tr>
<td valign="top">

timestamp

</td>
<td valign="top">

long \(timestamp-micros\)

</td>
<td valign="top">

String \(YYYY-MM-DD HH:MM:SS.NNNNNNNNNN\)

</td>
</tr>
<tr>
<td valign="top">

uint8

</td>
<td valign="top">

int

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

uint64

</td>
<td valign="top">

bytes \(DECIMAL 20,0\)

</td>
<td valign="top">

Number

</td>
</tr>
</table>



## Cloud Storage Providers - Targets

The following table shows how internal data types are mapped to target data types for cloud storage provider targets. The target data type depends on the file format: Parquet, CSV, or JSON/JSONLines.


<table>
<tr>
<th valign="top">

SAP Datasphere

</th>
<th valign="top">

Parquet Data Type

</th>
<th valign="top">

CSV Representation

</th>
<th valign="top">

JSON Data Type

</th>
</tr>
<tr>
<td valign="top">

binary

</td>
<td valign="top">

BYTE\_ARRAY

</td>
<td valign="top">

Base64-encoded

</td>
<td valign="top">

String \(base64-encoded\)

</td>
</tr>
<tr>
<td valign="top">

boolean

</td>
<td valign="top">

BOOLEAN

</td>
<td valign="top">

true or false

</td>
<td valign="top">

Boolean

</td>
</tr>
<tr>
<td valign="top">

date

</td>
<td valign="top">

INT32 \(DATE\)

</td>
<td valign="top">

YYYY-MM-DD

</td>
<td valign="top">

String \(YYYY-MM-DD\)

</td>
</tr>
<tr>
<td valign="top">

decimal\(p,s\)

</td>
<td valign="top">

DECIMAL\(p,s\)

</td>
<td valign="top">

As is

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

decfloat16

</td>
<td valign="top">

DECIMAL\(28,6\)

</td>
<td valign="top">

As is

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

decfloat34

</td>
<td valign="top">

DECIMAL\(38,6\)

</td>
<td valign="top">

As is

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

float32

</td>
<td valign="top">

FLOAT

</td>
<td valign="top">

Decimal or scientific notation

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

float64

</td>
<td valign="top">

DOUBLE

</td>
<td valign="top">

Decimal or scientific notation

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

int8

</td>
<td valign="top">

INT32

</td>
<td valign="top">

Integer \(base 10\)

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

int16

</td>
<td valign="top">

INT32

</td>
<td valign="top">

Integer \(base 10\)

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

int32

</td>
<td valign="top">

INT32

</td>
<td valign="top">

Integer \(base 10\)

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

int64

</td>
<td valign="top">

INT64

</td>
<td valign="top">

Integer \(base 10\)

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

string

</td>
<td valign="top">

BYTE\_ARRAY \(STRING\)

</td>
<td valign="top">

As is

</td>
<td valign="top">

String

</td>
</tr>
<tr>
<td valign="top">

time

</td>
<td valign="top">

INT64 \(TIME microseconds\)

</td>
<td valign="top">

HH:MM:SS.NNNNNNNNNN

</td>
<td valign="top">

String \(HH:MM:SS.NNNNNNNNNN\)

</td>
</tr>
<tr>
<td valign="top">

timestamp

</td>
<td valign="top">

INT64 \(TIMESTAMP microseconds\)

</td>
<td valign="top">

YYYY-MM-DD HH:MM:SS.NNNNNNNNNN

</td>
<td valign="top">

String \(YYYY-MM-DD HH:MM:SS.NNNNNNNNNN\)

</td>
</tr>
<tr>
<td valign="top">

uint8

</td>
<td valign="top">

INT32

</td>
<td valign="top">

Integer \(base 10\)

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

uint64

</td>
<td valign="top">

INT64

</td>
<td valign="top">

Integer \(base 10\)

</td>
<td valign="top">

Number

</td>
</tr>
</table>



## SFTP - Targets

The following table shows how internal data types are mapped to target data types for SFTP targets. The target data type depends on the file format: Parquet, CSV, or JSON/JSONLines.


<table>
<tr>
<th valign="top">

SAP Datasphere

</th>
<th valign="top">

Parquet Data Type

</th>
<th valign="top">

CSV Representation

</th>
<th valign="top">

JSON Data Type

</th>
</tr>
<tr>
<td valign="top">

binary

</td>
<td valign="top">

BYTE\_ARRAY

</td>
<td valign="top">

Base64-encoded

</td>
<td valign="top">

String \(base64-encoded\)

</td>
</tr>
<tr>
<td valign="top">

boolean

</td>
<td valign="top">

BOOLEAN

</td>
<td valign="top">

true or false

</td>
<td valign="top">

Boolean

</td>
</tr>
<tr>
<td valign="top">

date

</td>
<td valign="top">

INT32 \(DATE\)

</td>
<td valign="top">

YYYY-MM-DD

</td>
<td valign="top">

String \(YYYY-MM-DD\)

</td>
</tr>
<tr>
<td valign="top">

decimal\(p,s\)

</td>
<td valign="top">

DECIMAL\(p,s\)

</td>
<td valign="top">

As is

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

decfloat16

</td>
<td valign="top">

DECIMAL\(28,6\)

</td>
<td valign="top">

As is

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

decfloat34

</td>
<td valign="top">

DECIMAL\(38,6\)

</td>
<td valign="top">

As is

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

float32

</td>
<td valign="top">

FLOAT

</td>
<td valign="top">

Decimal or scientific notation

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

float64

</td>
<td valign="top">

DOUBLE

</td>
<td valign="top">

Decimal or scientific notation

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

int8

</td>
<td valign="top">

INT32

</td>
<td valign="top">

Integer \(base 10\)

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

int16

</td>
<td valign="top">

INT32

</td>
<td valign="top">

Integer \(base 10\)

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

int32

</td>
<td valign="top">

INT32

</td>
<td valign="top">

Integer \(base 10\)

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

int64

</td>
<td valign="top">

INT64

</td>
<td valign="top">

Integer \(base 10\)

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

string

</td>
<td valign="top">

BYTE\_ARRAY \(STRING\)

</td>
<td valign="top">

As is

</td>
<td valign="top">

String

</td>
</tr>
<tr>
<td valign="top">

time

</td>
<td valign="top">

INT64 \(TIME microseconds\)

</td>
<td valign="top">

HH:MM:SS.NNNNNNNNNN

</td>
<td valign="top">

String \(HH:MM:SS.NNNNNNNNNN\)

</td>
</tr>
<tr>
<td valign="top">

timestamp

</td>
<td valign="top">

INT64 \(TIMESTAMP microseconds\)

</td>
<td valign="top">

YYYY-MM-DD HH:MM:SS.NNNNNNNNNN

</td>
<td valign="top">

String \(YYYY-MM-DD HH:MM:SS.NNNNNNNNNN\)

</td>
</tr>
<tr>
<td valign="top">

uint8

</td>
<td valign="top">

INT32

</td>
<td valign="top">

Integer \(base 10\)

</td>
<td valign="top">

Number

</td>
</tr>
<tr>
<td valign="top">

uint64

</td>
<td valign="top">

INT64

</td>
<td valign="top">

Integer \(base 10\)

</td>
<td valign="top">

Number

</td>
</tr>
</table>



## Google BigQuery - Targets

The following table shows how internal data types are mapped to Google BigQuery target data types. Note that uint64 is mapped to NUMERIC\(20,0\).


<table>
<tr>
<th valign="top">

SAP Datasphere

</th>
<th valign="top">

Google BigQuery Data Type

</th>
</tr>
<tr>
<td valign="top">

binary\(n\), 1<=n<=5000

</td>
<td valign="top">

BYTES\(n\)

</td>
</tr>
<tr>
<td valign="top">

boolean

</td>
<td valign="top">

BOOL

</td>
</tr>
<tr>
<td valign="top">

date

</td>
<td valign="top">

DATE

</td>
</tr>
<tr>
<td valign="top">

decimal\(p,s\)

</td>
<td valign="top">

NUMERIC\(p,s\) or BIGNUMERIC\(p,s\)

</td>
</tr>
<tr>
<td valign="top">

decfloat16

</td>
<td valign="top">

NUMERIC\(38,9\)

</td>
</tr>
<tr>
<td valign="top">

decfloat34

</td>
<td valign="top">

NUMERIC\(38,9\)

</td>
</tr>
<tr>
<td valign="top">

float32

</td>
<td valign="top">

FLOAT64

</td>
</tr>
<tr>
<td valign="top">

float64

</td>
<td valign="top">

FLOAT64

</td>
</tr>
<tr>
<td valign="top">

int8

</td>
<td valign="top">

INT64

</td>
</tr>
<tr>
<td valign="top">

int16

</td>
<td valign="top">

INT64

</td>
</tr>
<tr>
<td valign="top">

int32

</td>
<td valign="top">

INT64

</td>
</tr>
<tr>
<td valign="top">

int64

</td>
<td valign="top">

INT64

</td>
</tr>
<tr>
<td valign="top">

string\(n\), 1<=n<=5000

</td>
<td valign="top">

STRING\(n\)

</td>
</tr>
<tr>
<td valign="top">

time

</td>
<td valign="top">

TIME

</td>
</tr>
<tr>
<td valign="top">

timestamp

</td>
<td valign="top">

TIMESTAMP

</td>
</tr>
<tr>
<td valign="top">

uint8

</td>
<td valign="top">

INT64

</td>
</tr>
<tr>
<td valign="top">

uint64

</td>
<td valign="top">

NUMERIC\(20,0\)

</td>
</tr>
<tr>
<td valign="top">

geometry

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

geometryewkb

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

string

</td>
<td valign="top">

Not Supported

</td>
</tr>
</table>



## SAP Datasphere - Targets

The following table shows how internal data types are mapped to SAP Datasphere \(HANA\) target data types.


<table>
<tr>
<th valign="top">

SAP Datasphere

</th>
<th valign="top">

SAP Datasphere \(HANA\) Data Type

</th>
</tr>
<tr>
<td valign="top">

binary\(n\), 1<=n<=5000

</td>
<td valign="top">

VARBINARY\(n\)

</td>
</tr>
<tr>
<td valign="top">

boolean

</td>
<td valign="top">

BOOLEAN

</td>
</tr>
<tr>
<td valign="top">

date

</td>
<td valign="top">

DATE

</td>
</tr>
<tr>
<td valign="top">

decimal\(p,s\)

</td>
<td valign="top">

DECIMAL\(p,s\)

</td>
</tr>
<tr>
<td valign="top">

decfloat16

</td>
<td valign="top">

SMALLDECIMAL

</td>
</tr>
<tr>
<td valign="top">

decfloat34

</td>
<td valign="top">

DECIMAL

</td>
</tr>
<tr>
<td valign="top">

float32

</td>
<td valign="top">

REAL

</td>
</tr>
<tr>
<td valign="top">

float64

</td>
<td valign="top">

DOUBLE

</td>
</tr>
<tr>
<td valign="top">

int8

</td>
<td valign="top">

SMALLINT

</td>
</tr>
<tr>
<td valign="top">

int16

</td>
<td valign="top">

SMALLINT

</td>
</tr>
<tr>
<td valign="top">

int32

</td>
<td valign="top">

INTEGER

</td>
</tr>
<tr>
<td valign="top">

int64

</td>
<td valign="top">

BIGINT

</td>
</tr>
<tr>
<td valign="top">

string

</td>
<td valign="top">

NCLOB

</td>
</tr>
<tr>
<td valign="top">

string\(n\), 1<=n<=5000

</td>
<td valign="top">

NVARCHAR\(n\)

</td>
</tr>
<tr>
<td valign="top">

time

</td>
<td valign="top">

TIME

</td>
</tr>
<tr>
<td valign="top">

timestamp

</td>
<td valign="top">

TIMESTAMP

</td>
</tr>
<tr>
<td valign="top">

uint8

</td>
<td valign="top">

TINYINT

</td>
</tr>
<tr>
<td valign="top">

uint64

</td>
<td valign="top">

DECIMAL\(20,0\)

</td>
</tr>
</table>



## SAP S/4HANA ABAP Sources - Data Types

The following table shows how SAP S/4HANA ABAP \(ODP\) source data types are mapped to internal data types.


<table>
<tr>
<th valign="top">

ODP Data Type

</th>
<th valign="top">

SAP Datasphere

</th>
</tr>
<tr>
<td valign="top">

ACCP

</td>
<td valign="top">

string\(6\)

</td>
</tr>
<tr>
<td valign="top">

CHAR

</td>
<td valign="top">

string\(n\)

</td>
</tr>
<tr>
<td valign="top">

CLNT

</td>
<td valign="top">

string\(3\)

</td>
</tr>
<tr>
<td valign="top">

CUKY

</td>
<td valign="top">

string\(5\)

</td>
</tr>
<tr>
<td valign="top">

DATS

</td>
<td valign="top">

date or string\(8\)

</td>
</tr>
<tr>
<td valign="top">

DEC

</td>
<td valign="top">

decimal\(p,s\)

</td>
</tr>
<tr>
<td valign="top">

DFIL16\_DEC

</td>
<td valign="top">

decfloat16

</td>
</tr>
<tr>
<td valign="top">

DFIL34\_RAW

</td>
<td valign="top">

decfloat34

</td>
</tr>
<tr>
<td valign="top">

DFIL34\_SCL

</td>
<td valign="top">

decfloat34

</td>
</tr>
<tr>
<td valign="top">

DFLIL\_RAW

</td>
<td valign="top">

binary

</td>
</tr>
<tr>
<td valign="top">

GEOM\_EWKB

</td>
<td valign="top">

binary

</td>
</tr>
<tr>
<td valign="top">

INT1

</td>
<td valign="top">

uint8

</td>
</tr>
<tr>
<td valign="top">

INT2

</td>
<td valign="top">

int16

</td>
</tr>
<tr>
<td valign="top">

INT4

</td>
<td valign="top">

int32

</td>
</tr>
<tr>
<td valign="top">

INT8

</td>
<td valign="top">

int64

</td>
</tr>
<tr>
<td valign="top">

LANG

</td>
<td valign="top">

string\(1\)

</td>
</tr>
<tr>
<td valign="top">

LCHR

</td>
<td valign="top">

string\(n\)

</td>
</tr>
<tr>
<td valign="top">

LRAW

</td>
<td valign="top">

binary\(n\)

</td>
</tr>
<tr>
<td valign="top">

NUMC

</td>
<td valign="top">

string\(n\)

</td>
</tr>
<tr>
<td valign="top">

PREC

</td>
<td valign="top">

int16

</td>
</tr>
<tr>
<td valign="top">

RAW

</td>
<td valign="top">

binary\(n\)

</td>
</tr>
<tr>
<td valign="top">

RAWSTRING

</td>
<td valign="top">

binary

</td>
</tr>
<tr>
<td valign="top">

SSTRING

</td>
<td valign="top">

string

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

TIMS

</td>
<td valign="top">

time or string\(6\)

</td>
</tr>
<tr>
<td valign="top">

UNIT

</td>
<td valign="top">

string\(2-3\)

</td>
</tr>
</table>

> ### Note:  
> For DATS and TIMS columns, the internal data type depends on the Content Type setting. With Template Type, DATS maps to date and TIMS maps to time. With Native Type \(default\), both map to their string representations \(string\(10\) and string\(8\) respectively\).



## SAP ECC/BW Sources

The following table shows how SAP ECC/BW \(ODP\) source data types are mapped to internal data types.


<table>
<tr>
<th valign="top">

ODP Data Type

</th>
<th valign="top">

SAP Datasphere

</th>
</tr>
<tr>
<td valign="top">

ACCP

</td>
<td valign="top">

string\(6\)

</td>
</tr>
<tr>
<td valign="top">

CHAR

</td>
<td valign="top">

string\(n\)

</td>
</tr>
<tr>
<td valign="top">

CLNT

</td>
<td valign="top">

string\(3\)

</td>
</tr>
<tr>
<td valign="top">

CUKY

</td>
<td valign="top">

string\(5\)

</td>
</tr>
<tr>
<td valign="top">

DATS

</td>
<td valign="top">

date or string\(8\)

</td>
</tr>
<tr>
<td valign="top">

DEC

</td>
<td valign="top">

decimal\(p,s\)

</td>
</tr>
<tr>
<td valign="top">

DFIL16\_DEC

</td>
<td valign="top">

decfloat16

</td>
</tr>
<tr>
<td valign="top">

DFIL34\_RAW

</td>
<td valign="top">

decfloat34

</td>
</tr>
<tr>
<td valign="top">

DFIL34\_SCL

</td>
<td valign="top">

decfloat34

</td>
</tr>
<tr>
<td valign="top">

DFLIL\_RAW

</td>
<td valign="top">

binary

</td>
</tr>
<tr>
<td valign="top">

GEOM\_EWKB

</td>
<td valign="top">

binary

</td>
</tr>
<tr>
<td valign="top">

INT1

</td>
<td valign="top">

uint8

</td>
</tr>
<tr>
<td valign="top">

INT2

</td>
<td valign="top">

int16

</td>
</tr>
<tr>
<td valign="top">

INT4

</td>
<td valign="top">

int32

</td>
</tr>
<tr>
<td valign="top">

INT8

</td>
<td valign="top">

int64

</td>
</tr>
<tr>
<td valign="top">

LANG

</td>
<td valign="top">

string\(1\)

</td>
</tr>
<tr>
<td valign="top">

LCHR

</td>
<td valign="top">

string\(n\)

</td>
</tr>
<tr>
<td valign="top">

LRAW

</td>
<td valign="top">

binary\(n\)

</td>
</tr>
<tr>
<td valign="top">

NUMC

</td>
<td valign="top">

string\(n\)

</td>
</tr>
<tr>
<td valign="top">

PREC

</td>
<td valign="top">

int16

</td>
</tr>
<tr>
<td valign="top">

RAW

</td>
<td valign="top">

binary\(n\)

</td>
</tr>
<tr>
<td valign="top">

RAWSTRING

</td>
<td valign="top">

binary

</td>
</tr>
<tr>
<td valign="top">

SSTRING

</td>
<td valign="top">

string

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

TIMS

</td>
<td valign="top">

time or string\(6\)

</td>
</tr>
<tr>
<td valign="top">

UNIT

</td>
<td valign="top">

string\(2-3\)

</td>
</tr>
</table>

> ### Note:  
> For DATS and TIMS columns, the internal data type depends on the Content Type setting. With Template Type, DATS maps to date and TIMS maps to time. With Native Type \(default\), both map to their string representations \(string\(10\) and string\(8\) respectively\).



## Snowflake Sources - Data Types

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



## Local Table \(File\) Sources - Data Types

The following table shows how Datasphere Local Table \(CDS\) data types are mapped to internal data types.


<table>
<tr>
<th valign="top">

CDS Data Type

</th>
<th valign="top">

SAP Datasphere

</th>
</tr>
<tr>
<td valign="top">

Binary

</td>
<td valign="top">

binary

</td>
</tr>
<tr>
<td valign="top">

Boolean

</td>
<td valign="top">

bool

</td>
</tr>
<tr>
<td valign="top">

Date

</td>
<td valign="top">

date

</td>
</tr>
<tr>
<td valign="top">

DateTime

</td>
<td valign="top">

timestamp

</td>
</tr>
<tr>
<td valign="top">

Decimal

</td>
<td valign="top">

decimal\(p,s\)

</td>
</tr>
<tr>
<td valign="top">

DecimalFloat

</td>
<td valign="top">

decfloat34

</td>
</tr>
<tr>
<td valign="top">

Double

</td>
<td valign="top">

float64

</td>
</tr>
<tr>
<td valign="top">

hana.BINARY

</td>
<td valign="top">

binary

</td>
</tr>
<tr>
<td valign="top">

hana.REAL

</td>
<td valign="top">

float32

</td>
</tr>
<tr>
<td valign="top">

hana.SMALLDECIMAL

</td>
<td valign="top">

decfloat16

</td>
</tr>
<tr>
<td valign="top">

hana.SMALLINT

</td>
<td valign="top">

int16

</td>
</tr>
<tr>
<td valign="top">

hana.TINYINT

</td>
<td valign="top">

uint8

</td>
</tr>
<tr>
<td valign="top">

Integer

</td>
<td valign="top">

int32

</td>
</tr>
<tr>
<td valign="top">

Integer64

</td>
<td valign="top">

int64

</td>
</tr>
<tr>
<td valign="top">

LargeBinary

</td>
<td valign="top">

binary

</td>
</tr>
<tr>
<td valign="top">

LargeString

</td>
<td valign="top">

string

</td>
</tr>
<tr>
<td valign="top">

String

</td>
<td valign="top">

string\(n\)

</td>
</tr>
<tr>
<td valign="top">

Time

</td>
<td valign="top">

time

</td>
</tr>
<tr>
<td valign="top">

Timestamp

</td>
<td valign="top">

timestamp

</td>
</tr>
<tr>
<td valign="top">

UInt8

</td>
<td valign="top">

uint8

</td>
</tr>
</table>



## SAP HANA Cloud, Data Lake Files Sources

The following table shows how Data Sharing source data types are mapped to internal data types.


<table>
<tr>
<th valign="top">

Data Sharing Data Type

</th>
<th valign="top">

SAP Datasphere

</th>
</tr>
<tr>
<td valign="top">

array

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

binary\(n\), 1<=n<=5,000

</td>
<td valign="top">

binary\(n\)

</td>
</tr>
<tr>
<td valign="top">

boolean

</td>
<td valign="top">

boolean

</td>
</tr>
<tr>
<td valign="top">

byte

</td>
<td valign="top">

int8

</td>
</tr>
<tr>
<td valign="top">

date

</td>
<td valign="top">

date

</td>
</tr>
<tr>
<td valign="top">

decimal

</td>
<td valign="top">

decimal\(p,s\)

</td>
</tr>
<tr>
<td valign="top">

double

</td>
<td valign="top">

float64

</td>
</tr>
<tr>
<td valign="top">

float

</td>
<td valign="top">

float32

</td>
</tr>
<tr>
<td valign="top">

int

</td>
<td valign="top">

int32

</td>
</tr>
<tr>
<td valign="top">

long

</td>
<td valign="top">

int64

</td>
</tr>
<tr>
<td valign="top">

map

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

short

</td>
<td valign="top">

int16

</td>
</tr>
<tr>
<td valign="top">

string

</td>
<td valign="top">

string\(5000\)

</td>
</tr>
<tr>
<td valign="top">

struct

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

timestamp

</td>
<td valign="top">

timestamp

</td>
</tr>
<tr>
<td valign="top">

union

</td>
<td valign="top">

Not Supported

</td>
</tr>
</table>



## Oracle Sources - Data Types

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



## MySQL Sources - Data Types

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



## Signavio - Targets

The following table shows how internal data types are mapped to Signavio target data types for Parquet format.


<table>
<tr>
<th valign="top">

SAP Datasphere

</th>
<th valign="top">

Parquet Type

</th>
</tr>
<tr>
<td valign="top">

binary

</td>
<td valign="top">

BYTE\_ARRAY

</td>
</tr>
<tr>
<td valign="top">

boolean

</td>
<td valign="top">

BOOLEAN

</td>
</tr>
<tr>
<td valign="top">

date

</td>
<td valign="top">

INT32

</td>
</tr>
<tr>
<td valign="top">

decimal\(p,s\)

</td>
<td valign="top">

FIXED\_LEN\_BYTE\_ARRAY

</td>
</tr>
<tr>
<td valign="top">

decfloat16

</td>
<td valign="top">

FIXED\_LEN\_BYTE\_ARRAY

</td>
</tr>
<tr>
<td valign="top">

decfloat34

</td>
<td valign="top">

FIXED\_LEN\_BYTE\_ARRAY

</td>
</tr>
<tr>
<td valign="top">

float32

</td>
<td valign="top">

FLOAT

</td>
</tr>
<tr>
<td valign="top">

float64

</td>
<td valign="top">

DOUBLE

</td>
</tr>
<tr>
<td valign="top">

int8

</td>
<td valign="top">

INT32

</td>
</tr>
<tr>
<td valign="top">

int16

</td>
<td valign="top">

INT32

</td>
</tr>
<tr>
<td valign="top">

int32

</td>
<td valign="top">

INT32

</td>
</tr>
<tr>
<td valign="top">

int64

</td>
<td valign="top">

INT64

</td>
</tr>
<tr>
<td valign="top">

string

</td>
<td valign="top">

BYTE\_ARRAY

</td>
</tr>
<tr>
<td valign="top">

time

</td>
<td valign="top">

INT64

</td>
</tr>
<tr>
<td valign="top">

timestamp

</td>
<td valign="top">

INT64

</td>
</tr>
<tr>
<td valign="top">

uint8

</td>
<td valign="top">

INT32

</td>
</tr>
<tr>
<td valign="top">

uint64

</td>
<td valign="top">

INT64

</td>
</tr>
</table>

