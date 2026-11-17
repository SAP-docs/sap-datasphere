<!-- loioc7accb3184274e1eb25c582bf3235789 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# SAP ECC and SAP BW Sources for Replication Flows

You can replicate data from SAP ECC and SAP BW systems using the ODP 2.0 framework. Unlike ABAP and SAP S/4HANA connections, replication flows connect directly to the ABAP system, so no DMIS add-on installation is required.



## Prerequisites

-   Make sure you have created a SAP ECC and BW connection in your space. For more information, see:
    -   [SAP ECC Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/e546ccd61af54bf49a0f531a43fe0961.html "Use an SAP ECC connection to access data from SAP ERP Central Component (SAP ECC) systems (on-premise).") :arrow_upper_right:
    -   [SAP BW Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/e589041e80264f43b6c209c407336376.html "Use an SAP BW connection to access data from SAP Business Warehouse (SAP BW) or SAP BW∕4HANA systems.") :arrow_upper_right:

-   Replication objects support the *Initial Only*, *Initial and Delta*, and *Delta Only load types*.
-   ODP datasets without a primary key are supported if you configure the primary key manually. To do so:
    -   Select the relevant object.
    -   Choose Configure Schema in the *Source Schema Settings* section of the properties panel.
    -   Mark the relevant columns as key columns.

-   To display available ODP datasets, you need to enter a search string in the *Select Source Objects* dialog. By default, no datasets are displayed.
-   Replication is limited to ODP BW and SAPI data sources.



## Source Settings

The following properties are relevant for SAP ECC and SAP BW connection as sources for a replication flow. You can review and change these properties for the replication flow itself \(by choosing <span class="FPA-icons-V3"></span> \(Browse source settings\)\) or for individual replication objects \(by selecting an object so that its properties get displayed in the side panel\).


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Shorten Long Data

</td>
<td valign="top">

By default, this option is enabled. If a field value is longer than the defined length, the value is shortened so replication can continue. If you disable this option, replication fails with an error when values exceed the defined length.

</td>
</tr>
<tr>
<td valign="top">

Replace Invalid Characters

</td>
<td valign="top">

By default, this option is enabled. Invalid characters in the source data are replaced so replication can continue. If you disable this option, replication fails with an error when invalid characters are found.

</td>
</tr>
<tr>
<td valign="top">

Max. Number of Partitions

</td>
<td valign="top">

By default, any settings that you have made at replication object level are kept intact if you make a different setting at replication flow level. To change this, enable this option.

</td>
</tr>
<tr>
<td valign="top">

Overwrite Source Settings at Object Level 

</td>
<td valign="top">

By default, any settings that you have made at replication object level are kept intact if you make a different setting at replication flow level. To change this, enable this option.

</td>
</tr>
<tr>
<td valign="top">

Content Type 

</td>
<td valign="top">

\[only relevant for ABAP-based source systems\] Select a content type to control how date and other data types are converted in the target table. 

You can choose between 2 content types:

-   *Template Type*: The data types used in the source table are applied to the target table. *DATE* and *TIME* columns keep their corresponding date and time data types.
-   *Native Type* \(default\): Different data types are applied to the target table based on the source metadata. *DATE* and *TIME* columns are represented as *string* using the native length provided by the source metadata.

For more information, see [SAP S/4HANA and Other ABAP Sources for Replication Flows](sap-s-4hana-and-other-abap-sources-for-replication-flows-3f70579.md).

</td>
</tr>
</table>



## Choose the Content Type

When working with SAP ECC and SAP BW sources, you can set the content type to control how source data types are applied to the target table. You can set it at the replication flow level, where it applies to all columns as the default, or at the column level, where it overrides the replication flow level setting for the columns you select.

For more information about the available content types and how to set or change them, see [SAP S/4HANA and Other ABAP Sources for Replication Flows](sap-s-4hana-and-other-abap-sources-for-replication-flows-3f70579.md).



## Replicate Source Objects Without Primary Keys

If a source object does not have a primary key, you can still use it in a replication flow by configuring the primary key columns manually. The target table requires a primary key, so you must define which columns serve as the key before you deploy the replication flow. To configure the primary key columns:

1.  Select the relevant source object.
2.  In the properties panel, go to the *Source Schema Settings* section and choose *Configure Schema.*
3.  Mark the relevant columns as key columns.

The columns you select as the primary key must contain unique, non-null values. Incorrect settings result in data inconsistency.



## Data Types

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

