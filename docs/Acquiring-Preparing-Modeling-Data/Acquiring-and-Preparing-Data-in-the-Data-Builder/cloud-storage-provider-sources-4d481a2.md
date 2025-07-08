<!-- loio4d481a2c620f4b52ba65b360299d7719 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Cloud Storage Provider Sources

If you use a cloud storage provider as the source for your replication flow, you need to consider additional specifics and conditions.



<a name="loio4d481a2c620f4b52ba65b360299d7719__section_ReplTargets_NonSAPSources"/>

## Available Sources

The following cloud storage providers can be used as the source of a replication flow:

-   Data lake Files from SAP HANA Cloud, data lake

-   Amazon Simple Storage Service

-   Google Cloud Storage

-   Microsoft Azure Data Lake Gen2


For more information about the corresponding connection types, see [Integrating Data via Connections](https://help.sap.com/docs/SAP_DATASPHERE/be5967d099974c69b77f4549425ca4c0/eb85e157ab654152bd68a8714036e463.html).



<a name="loio4d481a2c620f4b52ba65b360299d7719__section_ReplFlow_NonSAP_Sources_Prerequisites"/>

## Prerequisites

All objects in your replication flow have load type *Initial Only*.

The data you want to replicate is stored in CSV files, and one of the following delimiters is used:

-   Comma \(,\)

-   Semicolon \(;\)

-   Colon \(:\)

-   Vertical slash \(|\)

-   Horizontal tabulator \(also known as tab or \\t\)


The CSV files are located in a folder, which serves as the source container for your replication flow. All files have the same schema.



<a name="loio4d481a2c620f4b52ba65b360299d7719__section_ReplFlow_NonSAP_Sources_Properties"/>

## Additional Properties

The following properties are relevant for cloud storage providers as sources for a replication flow. You can review and change these properties for the replication flow itself \(by choosing <span class="FPA-icons-V3"></span> \(Browse source settings\)\) or for individual replication objects \(by selecting an object so that its properties get displayed in the side panel\).


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

Enable this option if you want the replication to fail if the source data is too long. By default, the replication fails if it encounters a string value greater than 5000, a binary value greater than 3000, or a decimal value with precision between 1 and 76 \(1 <= precision <= 76\) and scale between 0 and precision \(0 <= scale <= precision\). If you deactivate this property, source values that are too long are automatically truncated.

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

Enable this option if you want data that is stored in subfolders to be included in the replication. By default, the data in all subfolders of the selected CSV files is considered for replication, and there is no maximum depth for nesting. If you disable this option, data in subfolders is ignored during the replication.

</td>
</tr>
<tr>
<td valign="top">

Global Pattern

</td>
<td valign="top">

Enter a global pattern if you want to only replicate files whose names conform with the pattern. See below for detailed examples.

</td>
</tr>
</table>



<a name="loio4d481a2c620f4b52ba65b360299d7719__section_ReplFlow_NonSAP_Sources_Schema"/>

## Defining the Schema \(and Related Properties\)

In the step for selecting the source objects for your replication flow, you get a list of all files in the relevant folder. You then select the file whose metadata \(particularly the schema\) you want to use for the target.

You can edit the schema later if necessary. To do so, select the object whose schema you want to change, then choose *Edit Schema* \(in the properties panel\). A list of the source columns with their respective data type and other relevant properties \(such as precision and scale\) is displayed. Change these values as required, then choose *Update Schema*.

> ### Caution:  
> If you define mappings and make schema changes afterwards \(except for defining columns as primary key columns\), the existing mappings get deleted when you update the schema.

In addition, you can change the following **other properties** here:

-   **File Delimiter**: The existing delimiter is automatically entered as the default value. You can change it to any of the allowed values as listed above.

-   **Encoding**: The existing encoding value is automatically entered as the default default value. Alternatively \(if the system cannot determine the existing value\), UTF-8 is used as the default. You can change it to UTF-16 or ISO-8859-1.

-   **File Header**: By default, the system assumes that the first row in each CSV file is a header. If this is not the case, deactivate this property. The system then automatically names the columns as C\(index\), starting with C0.


**Specify primary key columns**: The source files do not have a primary key defined, while the target tables need to have a primary key. Consequently, you have to specify the primary key columns for the target. To do so, select the relevant object, then choose *Configure Schema* \(in the *Source Schema Settings* section of the properties panel\) and mark the relevant columns as key columns.



<a name="loio4d481a2c620f4b52ba65b360299d7719__section_ReplFlow_NonSAP_Sources_GlobalPatterns"/>

## Examples for Global Patterns

You have the following files:

-   /datasetFolder/example.csv

-   /datasetFolder/test1.csv

-   /datasetFolder/test2.csv

-   /datasetFolder/test3.json

-   /datasetFolder/subfolder1/test4.csv

-   /datasetFolder/subfolder1/subfolder2/test5.csv


Example 1:

You define a global pattern as “test\*.csv”. The result is that only the matching files from the dataset folder are picked up \(regardless of whether the configuration property *Include Subfolders* is enabled or disabled\):

-   /datasetFolder/test1.csv

-   /datasetFolder/test2.csv


Example 2:

You define the global pattern as “\*\*/test\*.csv” and enable *Include Subfolders*. Then the result looks like this:

-   /datasetFolder/test1.csv

-   /datasetFolder/test2.csv

-   /datasetFolder/subfolder1/test4.csv

-   /datasetFolder/subfolder1/subfolder2/test5.cs


If *Include Subfolders* is disabled, the result is as follows, even if the global pattern allows going to the subfolders:

-   /datasetFolder/test1.csv

-   /datasetFolder/test2.csv


