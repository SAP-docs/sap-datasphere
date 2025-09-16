<!-- loio6c770bbebb3c4086b30945fd2ebbfd75 -->

# Unsupported Data Types in Replication Flow

Replication flows support all data types in Datasphere \(see [Column Data Types](column-data-types-7b1dc6e.md)\), except for the following sources and target connections.



<a name="loio6c770bbebb3c4086b30945fd2ebbfd75__section_hg5_5t2_3gc"/>

## Sources

The following source connections are not supported in replication flow:


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

MS SQ

</td>
<td valign="top">

-   CLOB \(nvarchar\(max\)
-   varchar\(max\)
-   text
-   ntext\)
-   BLOB \(image,varbinary\(max\)\)
-   cursor
-   hierarchyid
-   sql\_variant
-   Spatial Geometry Types
-   rowversion
-   xml



</td>
</tr>
<tr>
<td valign="top">

Confluent

</td>
<td valign="top">

Not applicable.

</td>
</tr>
<tr>
<td valign="top">

Azure SQL

</td>
<td valign="top">

-   CLOB \(nvarchar\(max\)
-   varchar\(max\)
-   text
-   ntext\)
-   BLOB \(image, varbinary\(max\)\)
-   cursor
-   hierarchyid
-   sql\_variant
-   Spatial Geometry Types
-   rowversion
-   xml



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
</table>



<a name="loio6c770bbebb3c4086b30945fd2ebbfd75__section_ptm_4v2_3gc"/>

## Targets

The following target connections are not supported in replication flow:


<table>
<tr>
<th valign="top">

Target

</th>
<th valign="top">

Unsupported Data Types

</th>
<th valign="top">

Mapped to Higher Version of Data Types

</th>
</tr>
<tr>
<td valign="top">

GBQ

</td>
<td valign="top">

-   decfloat16
-   decfloat34
-   uint64



</td>
<td valign="top">

-   Mapped to target DECIMAL\(p,s\) with: \(9<=s<=38 && 29<=p-s<=38\) || \(p==77 && s ==38\) column type.
-   Mapped to target DECIMAL\(20,0\) column type.



</td>
</tr>
<tr>
<td valign="top">

LTF

</td>
<td valign="top">

-   decfloat16
-   decfloat34
-   uint64
-   time
-   hana.ST\_POINT
-   hana.ST\_GEOMETRY
-   uint8
-   tiny int
-   datatime



</td>
<td valign="top">

-   Mapped to target DECIMAL\(p,s\) with: \(9<=s<=38 && 29<=p-s<=38\) || \(p==77 && s ==38\) column type.
-   Mapped to target DECIMAL\(20,0\) column type.



</td>
</tr>
</table>

