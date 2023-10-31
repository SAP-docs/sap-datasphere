<!-- loio7b1dc6e0fad147de8e50aa8dc4744aa3 -->

# Column Data Types

SAP Datasphere supports a wide range of data types for your columns. Once a table is deployed and contains data, column data types can only be changed if the change is compatible with the type of data contained in the column and will not truncate any value.



> ### Note:  
> The SAP Cloud Application Programming Model \(CAP\) recommends to use the Core Data Services built-in types \(see [Built-in Types](https://cap.cloud.sap/docs/cds/types)\), but it is also possible to use the SAP HANA-specific data types, which all have a “`hana.`” prefix \(see [SAP HANA-Specific Data Types](https://cap.cloud.sap/docs/advanced/hana#hana-types)\).



<a name="loio7b1dc6e0fad147de8e50aa8dc4744aa3__section_qsw_brq_jrb"/>

## Datetime Data Types


<table>
<tr>
<th valign="top">

Data Type

</th>
<th valign="top">

Default Format

</th>
<th valign="top">

Supported Value Range

</th>
<th valign="top">

Can Be Converted To...

</th>
</tr>
<tr>
<td valign="top">

Date

</td>
<td valign="top">

YYYY-MM-DD

</td>
<td valign="top">

‘0001-01-01’ to ‘9999-12-31’

</td>
<td valign="top">

Datetime, String

</td>
</tr>
<tr>
<td valign="top">

Datetime

</td>
<td valign="top">

YYYY-MM-DD HH24:MI:SS

</td>
<td valign="top">

‘0001-01-01 00:00:00’ to ‘9999-12-31 23:59:59’

</td>
<td valign="top">

Date, String, Time

</td>
</tr>
<tr>
<td valign="top">

Time

</td>
<td valign="top">

HH24:MI:SS

</td>
<td valign="top">

‘00:00:00 ’ to ’23:59:59’

</td>
<td valign="top">

Datetime, String

</td>
</tr>
<tr>
<td valign="top">

Timestamp

</td>
<td valign="top">

YYYY-MM-DD HH24:MI:SS

</td>
<td valign="top">

‘0001-01-01 00:00:00’ to ‘9999-12-31 23:59:59’

</td>
<td valign="top">

String

</td>
</tr>
</table>



<a name="loio7b1dc6e0fad147de8e50aa8dc4744aa3__section_skv_trq_jrb"/>

## Character String Data Types


<table>
<tr>
<th valign="top">

Data Type

</th>
<th valign="top">

Can contain...

</th>
<th valign="top">

Can Be Converted To...

</th>
</tr>
<tr>
<td valign="top">

LargeString

</td>
<td valign="top">

Variable length string of up to 2 GB.

</td>
<td valign="top">

No data type conversion possible

</td>
</tr>
<tr>
<td valign="top">

String\(n\)

</td>
<td valign="top">

Variable-length Unicode string of up 5000 characters.

</td>
<td valign="top">

Binary, Boolean, Date, Datetime, Decimal, Double, hana.SMALLINT, hana.TINYINT, hana.SMALLDECIMAL, hana.REAL, hana.BINARY, Integer, Integer64, LargeBinary, LargeString, Time, Timestamp.

> ### Note:  
> `String(36)` only can also be converted to UUID.



</td>
</tr>
</table>



<a name="loio7b1dc6e0fad147de8e50aa8dc4744aa3__section_awx_2sq_jrb"/>

## Numeric Data Types


<table>
<tr>
<th valign="top">

Data Type

</th>
<th valign="top">

Description

</th>
<th valign="top">

Example Value

</th>
<th valign="top">

Can Be Converted To...

</th>
</tr>
<tr>
<td valign="top">

Decimal \(p, s\)

</td>
<td valign="top">

Precision \(p\) defines the number of total digits and can be between 1 and 38.

Scale \(s\) defines the number of digits after the decimal point and can be between 0 and p.

</td>
<td valign="top">

15.2

</td>
<td valign="top">

Double, String

</td>
</tr>
<tr>
<td valign="top">

DecimalFloat

</td>
<td valign="top">

Decimal floating-point number with 34 mantissa digits.

</td>
<td valign="top">

15.2

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Double

</td>
<td valign="top">

Double-precision, 64-bit floating-point number

</td>
<td valign="top">

15.2

</td>
<td valign="top">

String

</td>
</tr>
<tr>
<td valign="top">

Integer

</td>
<td valign="top">

Respective container's standard signed integer.

</td>
<td valign="top">

1337

</td>
<td valign="top">

Boolean, Decimal, Double, hana.SMALLINT, hana.TINYINT, Integer64, String

</td>
</tr>
<tr>
<td valign="top">

Integer64

</td>
<td valign="top">

Signed 64-bit integer

</td>
<td valign="top">

1337

</td>
<td valign="top">

Boolean, Decimal, Double, hana.SMALLINT, hana.TINYINT, Integer, String

</td>
</tr>
<tr>
<td valign="top">

hana.REAL

</td>
<td valign="top">

32-bit binary floating-point number

</td>
<td valign="top">

15.2

</td>
<td valign="top">

Double, hana.SMALLDECIMAL, String

</td>
</tr>
<tr>
<td valign="top">

hana.SMALLDECIMAL

</td>
<td valign="top">

64-bit decimal floating-point number, where \(p\) can be between 1 and 16 and s can be between -369 and 368.

</td>
<td valign="top">

15.2

</td>
<td valign="top">

Double, hana.REAL, String

</td>
</tr>
<tr>
<td valign="top">

hana.SMALLINT

</td>
<td valign="top">

Signed 16-bit integer supporting the values -32,768 to 32,767

</td>
<td valign="top">

15

</td>
<td valign="top">

Decimal, Double, hana.SMALLDECIMAL, hana.TINYINT, Integer, Integer64, hana.REAL, String

</td>
</tr>
<tr>
<td valign="top">

hana.TINYINT

</td>
<td valign="top">

Unsigned 8-bit integer supporting the values 0 to 255

</td>
<td valign="top">

15

</td>
<td valign="top">

Decimal, Double, hana.SMALLDECIMAL, hana.SMALLINT, hana.REAL, Integer, Integer64, String

</td>
</tr>
</table>

For more information, see [Numeric Data Types](https://help.sap.com/viewer/c1d3f60099654ecfb3fe36ac93c121bb/2021_4_QRC/en-US/4ee2f261e9c44003807d08ccc2e249ac.html) in the *SAP HANA Cloud, SAP HANA Database* documentation.



<a name="loio7b1dc6e0fad147de8e50aa8dc4744aa3__section_onh_xsq_jrb"/>

## Boolean Data Types


<table>
<tr>
<th valign="top">

Data Type

</th>
<th valign="top">

Can contain...

</th>
<th valign="top">

Can Be Converted To...

</th>
</tr>
<tr>
<td valign="top">

Boolean

</td>
<td valign="top">

`TRUE`, `FALSE` and `UNKNOWN`, where `UNKNOWN` is a synonym of `NULL`.

</td>
<td valign="top">

Integer, String

</td>
</tr>
</table>



<a name="loio7b1dc6e0fad147de8e50aa8dc4744aa3__section_wvh_2tq_jrb"/>

## Binary Data Types


<table>
<tr>
<th valign="top">

Data Type

</th>
<th valign="top">

Can contain...

</th>
<th valign="top">

Can Be Converted To...

</th>
</tr>
<tr>
<td valign="top">

Binary\(n\)

</td>
<td valign="top">

Variable length byte string with user-defined length limit of up to 4000 bytes.

</td>
<td valign="top">

String, LargeBinary, hana.BINARY

</td>
</tr>
<tr>
<td valign="top">

LargeBinary

</td>
<td valign="top">

Variable length byte string of up to 2 GB.

</td>
<td valign="top">

No data type conversion possible

</td>
</tr>
<tr>
<td valign="top">

hana.BINARY \(n\)

</td>
<td valign="top">

Byte string of fixed length \(n\).

</td>
<td valign="top">

LargeBinary, String, Binary

</td>
</tr>
</table>



<a name="loio7b1dc6e0fad147de8e50aa8dc4744aa3__section_xtl_2tq_jrb"/>

## Universally Unique Identifier Data Type


<table>
<tr>
<th valign="top">

Data Type

</th>
<th valign="top">

Description

</th>
<th valign="top">

Example Value

</th>
<th valign="top">

Can Be Converted To...

</th>
</tr>
<tr>
<td valign="top">

UUID

</td>
<td valign="top">

Universally unique identifier encoded as a 128-bit integer.

</td>
<td valign="top">

`be071623-8699-4106-b6fa-8e3cb04c261e`

</td>
<td valign="top">

String\(n\) where n \>=36

</td>
</tr>
</table>



<a name="loio7b1dc6e0fad147de8e50aa8dc4744aa3__section_gnl_mtq_jrb"/>

## Spatial Data Types


<table>
<tr>
<th valign="top">

Data Type

</th>
<th valign="top">

Can contain...

</th>
<th valign="top">

Can Be Converted To...

</th>
</tr>
<tr>
<td valign="top">

hana.ST\_GEOMETRY\[\(<srid\>\)\]

</td>
<td valign="top">

Spatial data in any form, including 0-dimensional points, lines, multi-lines, and polygons.

</td>
<td valign="top">

No data type conversion possible

</td>
</tr>
<tr>
<td valign="top">

hana.ST\_POINT\[\(<srid\>\)\]

</td>
<td valign="top">

Spatial data in the form of 0-dimensional points that represents a single location in coordinate space.

</td>
<td valign="top">

No data type conversion possible

</td>
</tr>
</table>

> ### Note:  
> Columns with data types `hana.ST_POINT[(<srid>)]` and `hana.ST_GEOMETRY[(<srid>)]` cannot be consumed directly in SAP Analytics Cloud in a view with a semantic usage of *Fact*. To use these geo-coordinates columns in SAP Analytics Cloud, add them to a view with a semantic usage of *Dimension*, and then create an association from your *Fact* to the *Dimension*.

