<!-- loio870401f211f94132909bd9f2fafd91b2 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Load or Delete Local Table Data

You can upload data from a CSV file to a local table. You can also delete all data from the table.

> ### Note:  
> Users with the standard *DW Modeler* role can use these tools. For more information, see [Roles and Privileges by App and Feature](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/internal/en-US/2d8b7d04dcae402f911d119437ce0a74.html "Review the standard roles and the privileges needed to access apps, tools, and other features of SAP Datasphere.") :arrow_upper_right:.

Use these tools in the toolbar *Edit* section:


<table>
<tr>
<th valign="top">

Tool



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

<span class="FPA-icons"></span> \(Upload Data From CSV File\)



</td>
<td valign="top">

Select your CSV file and follow the instructions.

> ### Note:  
> The file extension must be \*.csv. The file size must not exceed 25MB.

The following options are available:

-   Select the *Delete Existing Data Before Upload* option if appropriate.

-   Select *Use first row as column header* if your file contains column headers in its first line.
-   Next to *Insert missing string value as*, select *Empty value* or *NULL* before adding a record. All new empty values are stored as the selected value.
-   Select the character used to signify the boundary between columns in *CSV Delimiter*. In general, the default value ***Auto-detect*** is sufficient.

Review the matching of columns in your table with those in your CSV file.

> ### Note:  
> This data upload does not support the data transformations available when creating a table from a CSV file \(see [Creating a Local Table from a CSV File](creating-a-local-table-from-a-csv-file-8bba251.md)\).
> 
> The data in your CSV file must match the table structure, including respecting all data types and structures.
> 
> Date and time format support in this data upload is restricted as follows:
> 
> -   Date columns: `YYYY-MM-DD`, `YYYY/MM/DD`, `YYYY/MM-DD`, `YYYY-MM/DD`, or `YYYYMMDD`
> -   Time columns: `HH:MI:SS` or `HH24:MI[:SS]` 
> -   Date time columns: `YYYY-MM-DD HH:MI:SS`



</td>
</tr>
<tr>
<td valign="top">

<span class="FPA-icons"></span> \(Delete\)



</td>
<td valign="top">

Delete all the data in your table. This action cannot be reversed.



</td>
</tr>
</table>

