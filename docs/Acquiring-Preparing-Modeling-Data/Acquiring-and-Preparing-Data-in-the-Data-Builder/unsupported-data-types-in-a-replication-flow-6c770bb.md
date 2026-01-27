<!-- loio6c770bbebb3c4086b30945fd2ebbfd75 -->

# Unsupported Data Types in a Replication Flow

Replication flows support all data types in SAP Datasphere \(see, [Column Data Types](column-data-types-7b1dc6e.md)\), except for the following sources and target connections.



<a name="loio6c770bbebb3c4086b30945fd2ebbfd75__section_hg5_5t2_3gc"/>

## Sources

The following source data types are not supported in replication flow:


<table>
<tr>
<th valign="top">

Sources

</th>
<th valign="top">

Unsupported Data Types

</th>
</tr>
<tr>
<td valign="top">

Microsoft SQL Server \(MSSQL\) / Microsoft Azure SQL Database

</td>
<td valign="top">

-   binary\(n\)*\(5000 < n <= 8000*\)
-   varbinary\(n\)*\(5000 < n <= 8000*\)
-   varbinary\(max\)
-   ntext
-   image
-   cursor
-   nvarchar\(max\)
-   geography
-   geometry
-   table
-   json
-   hierarchyid
-   sql\_variant
-   char\(n\)*\(5000 < n <= 8000*\)
-   varchar\(n\)*\(5000 < n <= 8000*\)
-   xml



</td>
</tr>
<tr>
<td valign="top">

SAP HANA

</td>
<td valign="top">

-   BLOB
-   CLOB
-   NCLOB
-   TEXT
-   ARRAY
-   ST\_GEOMETRY
-   ST\_POINT
-   REAL\_VECTOR



</td>
</tr>
<tr>
<td valign="top">

Snowflake

</td>
<td valign="top">

-   VARIANT, OBJECT, ARRAY, GEOMETRY, GEOGRAPHY, VECTOR.
-   VARCHAR\[n\], BINARY\[n\] with n \> 5000 characters/bytes.
-   Snowflake also does not support LOB types \(BLOB, CLOB\), ENUMs, and custom user types.



</td>
</tr>
<tr>
<td valign="top">

ABAP

</td>
<td valign="top">

-   D16R – Floating point saved as binary data
-   D34R – Floating point saved as binary data
-   LRAW – Long byte string
-   RAW – Byte sequence
-   LCHR \(if length \> 5000\) – Long character string
-   STRG – String
-   RSTR – Byte string
-   STRING \(if length \> 5000\) - String



</td>
</tr>
</table>



<a name="loio6c770bbebb3c4086b30945fd2ebbfd75__section_ptm_4v2_3gc"/>

## Targets

The following target data types are not supported in replication flow:


<table>
<tr>
<th valign="top">

Target

</th>
<th valign="top">

Unsupported Data Types

</th>
</tr>
<tr>
<td valign="top">

Google BigQuery

</td>
<td valign="top">

The following data types will be converted:

-   decfloat16 will be converted to decimal \(38,6\)
-   decfloat34 will be converted to decimal \(38,6\)
-   uint64 will be converted to decimal\(20,0\)



</td>
</tr>
<tr>
<td valign="top">

Local Table \(File\)

</td>
<td valign="top">

The following data types will be converted:

-   decfloat16 will be converted to decimal \(38,6\)
-   decfloat34 will be converted to decimal \(38,6\)
-   uint64 will be converted to decimal\(20,0\)

The following data types will be skipped:

-   time
-   hana.ST\_POINT
-   hana.ST\_GEOMETRY
-   uint8
-   tiny int
-   datatime



</td>
</tr>
</table>

