<!-- loiobdff6b91cf4b44f895429c23566b3ea0 -->

# SAP Datasphere Local Table \(File\) Sources for Replication Flows

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

> ### Caution:  
> When using local tables \(file\) as the source of a replication flow, follow these best practices:
> 
> -   Do not pause replication flows for more than 30 days: If a replication flow remains paused beyond the retention period, the required historical delta versions may no longer be available. As a result, the flow may fail with Delta table/version-related errors when processing resumes. For more information, see the paragraph "Log Retention Period and Prompt Processing of Changes" in [Creating a Local Table \(File\)](creating-a-local-table-file-d21881b.md).
> -   Restart a failed replication flow instead of resuming it: If a replication flow fails, use *Restart* rather than *Resume*. A restart performs a new initialization based on the latest available snapshot and is the supported recovery method, provided that the current snapshot is still accessible.



## Data Types

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

