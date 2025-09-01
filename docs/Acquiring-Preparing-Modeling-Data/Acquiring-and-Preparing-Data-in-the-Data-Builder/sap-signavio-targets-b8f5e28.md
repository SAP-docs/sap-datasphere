<!-- loiob8f5e28d34b44d71a52f6265e4fc245f -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# SAP Signavio Targets

If you use SAP Signavio as the target for your replication flow, you need to consider the following additional specifics and conditions.



<a name="loiob8f5e28d34b44d71a52f6265e4fc245f__section_ndy_jgg_tcc"/>

## General Information

The target container is created automatically and called <datasphere space ID\>/<Technical name of the replication flow\>.

The default load type is *Initial Only*. You can change it to *Initial and Delta* \(with a default time interval of 24 hours\). Note that *Delta Only* is not supported.



<a name="loiob8f5e28d34b44d71a52f6265e4fc245f__section_a2x_zbg_tcc"/>

## Additional Properties

The following properties are relevant for SAP Signavio targets. You can review these properties for the replication flow itself \(by choosing <span class="FPA-icons-V3"></span> \(Browse source settings\)\) or for individual replication objects \(by selecting an object so that its properties get displayed in the side panel\).

> ### Note:  
> The values for these properties are fixed and cannot be changed.


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Value

</th>
<th valign="top">

Comment

</th>
</tr>
<tr>
<td valign="top">

*Group Delta by*

</td>
<td valign="top">

*None*

</td>
<td valign="top">

It means that it is not possible to create additional folders for sorting updates based on the date or hour.

</td>
</tr>
<tr>
<td valign="top">

*File Type*

</td>
<td valign="top">

*Parquet*

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

*Enable Apache Spark Compatibility*

</td>
<td valign="top">

*No*

</td>
<td valign="top">

It means that time data type columns are not converted to int64 and stored in the Parquet files.

</td>
</tr>
<tr>
<td valign="top">

*File Compression*

</td>
<td valign="top">

*Snappy*

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

*Suppress Duplicates*

</td>
<td valign="top">

*No*

</td>
<td valign="top">

It means that if a data record already exists in the target, this record is still written to the target once again.

</td>
</tr>
</table>



<a name="loiob8f5e28d34b44d71a52f6265e4fc245f__section_ReplFlow_GBQ_TargetColumns"/>

## Target Columns

The system automatically adds the following columns to the **schema of the target table**:


<table>
<tr>
<th valign="top">

Column

</th>
<th valign="top">

Data Type

</th>
</tr>
<tr>
<td valign="top">

\_\_operation\_type

</td>
<td valign="top">

String

</td>
</tr>
<tr>
<td valign="top">

\_\_sequence\_number

</td>
<td valign="top">

Unit64

</td>
</tr>
<tr>
<td valign="top">

\_\_timestamp

</td>
<td valign="top">

Timestamp

</td>
</tr>
</table>

These columns are needed to capture changes in the source so that they can be replicated to the target, and you cannot change their names or settings.

If a target column has the same name as one of the columns for change data capturing, the target column has to be renamed. Auto-Projection does this by adding the prefix AUTOPREFIX\_ to the name of the target column, for example AUTOPREFIX\_timestamp.

