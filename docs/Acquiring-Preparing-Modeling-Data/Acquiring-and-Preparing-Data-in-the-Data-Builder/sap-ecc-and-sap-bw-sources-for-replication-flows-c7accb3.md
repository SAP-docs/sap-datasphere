<!-- loioc7accb3184274e1eb25c582bf3235789 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# SAP ECC and SAP BW Sources for Replication Flows

You can replicate data from SAP ECC and SAP BW systems using ODP via the CFW ABAP Connector as a source for replication flows.



## Prerequisites

-   All objects in your replication flow have load type *Initial Only*. Delta loading is currently not supported.

-   Only ODP datasets with a primary key are supported.
-   To display available ODP datasets, you need to enter a search string in the *Select Source Objects* dialog. By default, no datasets are displayed.



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

\[only relevant for ABAP-based source systems\]. Select the best content type to use when loading data from an ABAP-based system. 

You can choose between 2 content types:

-   *Template Type*: The data types used in the source table are applied to the target table. *DATE* and *TIME* columns keep their corresponding date and time data types.
-   *Native Type* \(default\): Different data types are applied to the target table based on the source metadata. *DATE* and *TIME* columns are represented as *string* using the native length provided by the source metadata.

> ### Example:  
> Your source table contains a date column that doesn't have values in ISO format. If you select the content type *Template Type* your replication flow run will fail with an error because the target table will expect data in ISO format. You'd better select the *Native Type* to run the replication flow, so that the data type will be turned into string.

> ### Note:  
> This option is available only for replication flows created from wave 2025.04.It's best to use it for new targets, or for existing targets but only if you are certain about the existing column data types in the target. Otherwise, the replication flow deployment or run will fail due to a column data type mismatch between the source and target.
> 
> -   You can modify the content type later but with some restrictions. As the content type selection is at replication flow level, changing it will affect the source column data types \(date, time, and timestamp\) for all existing replication objects in the replication flow. For more information, see [Modify a Replication Flow](modify-a-replication-flow-a24c71f.md).



</td>
</tr>
</table>

