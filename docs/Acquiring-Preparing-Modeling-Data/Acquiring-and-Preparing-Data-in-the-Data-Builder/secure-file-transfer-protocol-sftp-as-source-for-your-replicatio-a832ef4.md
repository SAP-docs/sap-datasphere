<!-- loioa832ef4cee9d4d3aa1210869743b6173 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Secure File Transfer Protocol \(SFTP\) as Source for Your Replication Flow

You want to replicate data from a file storage using a secure file transfer protocol \(SFTP\) connection for secure and reliable file transfers to a supported target.



<a name="loioa832ef4cee9d4d3aa1210869743b6173__section_h24_wxl_lfc"/>

## Prerequisites

All objects in your replication flow have load type *Initial Only* \(Delta loading is not supported\).

The data you want to replicate is stored in CSV files, and one of the following delimiters is used:

-   Comma \(,\)

-   Semicolon \(;\)

-   Colon \(:\)

-   Vertical slash \(|\)

-   Horizontal tabulator \(also known as tab or \\t\)


The CSV files are located in a folder, which serves as the source container for your replication flow. All files have the same schema.



<a name="loioa832ef4cee9d4d3aa1210869743b6173__section_itl_fyl_lfc"/>

## Source Settings

The following properties are relevant for secure file transfer protocol \(SFTP\) connection as sources for a replication flow. You can review and change these properties for the replication flow itself \(by choosing <span class="FPA-icons-V3"></span> \(Browse source settings\)\) or for individual replication objects \(by selecting an object so that its properties get displayed in the side panel\).


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

Fail on Data Truncation

</td>
<td valign="top">

Enable this option if you want the replication to fail if the source data is too long.

By default, the replication fails if it encounters a string value greater than 5000 or a binary value greater than 5000. If you deactivate this property, source values that are too long are automatically truncated.

</td>
</tr>
<tr>
<td valign="top">

Fail on Incompatible Data

</td>
<td valign="top">

Enable this option if you want the replication to fail when it encounters values that are incompatible with the data type of the relevant target column. By default, the replication fails if it encounters incompatible data. If you deactivate this option, the system replaces incompatible values with NULL values.

</td>
</tr>
<tr>
<td valign="top">

Define Max. Number of Partitions

</td>
<td valign="top">

Enable this option if you want to define the maximum number of partitions manually. By default, the system uses 10 partitions. If you activate this option, an additional input field is displayed where you can enter the maximum number of partitions.

</td>
</tr>
<tr>
<td valign="top">

Max. Number of Partitions

</td>
<td valign="top">

Enter the maximum number of partitions to be used during the replication. By default, the system uses a maximum of 10 partitions for a replication object. However, depending on the specifics of your replication flow it may make sense to change this value \(for example if you use filtering so that only a fraction of the data is actually relevant for replication\). You can enter any integer number between 1 and 2147483647.

</td>
</tr>
<tr>
<td valign="top">

Include Subfolders

</td>
<td valign="top">

\[Read-Onlly\] Default value is NO. Data in subfolders is ignored during the replication.

</td>
</tr>
<tr>
<td valign="top">

Global Pattern

</td>
<td valign="top">

Enter a global pattern if you want to only replicate files whose names conform with the pattern.

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
</table>



<a name="loioa832ef4cee9d4d3aa1210869743b6173__section_yl2_3fm_lfc"/>

## Configuring the Schema \(and Related Properties

As the source objects are CSV files, you must define a primary key. You can do it in the *Object Properties* panel, under *Source Schema Settings* \> *Configure Schema*.

In addition, you can change the following **other properties** here:

-   **File Delimiter**: The existing delimiter is automatically entered as the default value. You can change it to any of the allowed values as listed above.

-   **Encoding**: The existing encoding value is automatically entered as the default default value. Alternatively \(if the system cannot determine the existing value\), UTF-8 is used as the default. You can change it to UTF-16 or ISO-8859-1.

-   **File Header**: By default, the system assumes that the first row in each CSV file is a header. If this is not the case, deactivate this property. The system then automatically names the columns as C\(index\), starting with C0.


