<!-- loioe57e12d39535439eb078078228c6f7bf -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Preview and Edit Local Table \(File\) Data

You want to preview and edit local table \(file\) data.

Local Tables \(File\) are intended for file storage with large amount of data. Due to the volume of data, some actions are limited compared to what you can do in the *Data Builder*.

> ### Caution:  
> To perform the following actions, your table :
> 
> -   Must have the status *Deployed*
> -   Contain at least one key column

> ### Restriction:  
> Some activities like default sorting and filtering are disabled.



<a name="loioe57e12d39535439eb078078228c6f7bf__section_h54_ll4_12c"/>

## Previewing Data in the Data Preview

To preview data, from the table editor, click <span class="SAP-icons-V5"></span> \(Data Viewer\).

The record count on data preview may not be available if some data statistics have not been computed yet. For more information, see [Monitoring Local Tables (File)](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/6b2d0073a8684ee6a59d6f47d00ec895.html "Monitor your local tables (file). Check how and when they were last updated and if new data has still to be merged.") :arrow_upper_right:.

> ### Note:  
> The data is read from the object store using SAP HANA SQL on Files to optimize the resources usage \(see [SAP HANA Native SQL on Files: Overview](https://help.sap.com/docs/hana-cloud-database/sap-hana-cloud-sap-hana-database-sql-on-files-guide/sap-hana-native-sql-on-files-overview?q=sap+hana+sql+on+files)\).



<a name="loioe57e12d39535439eb078078228c6f7bf__section_fph_dm4_12c"/>

## Reorder Your data

You can decide how you want to display your data:

-   **Reorder**: Drag and drop your columns to reorder them.



<a name="loioe57e12d39535439eb078078228c6f7bf__section_whk_h44_12c"/>

## Customize Your View

You can choose which columns from your table you want to display. Click <span class="FPA-icons-V3"></span> \(Columns Settings\) and select the columns to show in the preview.



<a name="loioe57e12d39535439eb078078228c6f7bf__section_qkd_t44_12c"/>

## Find and Replace Strings

Find & Replace operation on local tables \(File\) works slightly differently compared to local tables:

-   The *Find and Replace* activity is run as an asynchronous task using Apache Spark application 300. If the find and replace task uses more memory than the resources allowed by the application 300, the task will fail. For more information, see [Create a File Space to Load Data in the Object Store](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/947444683e524cfd9169d7671b72ba0c.html "Create a file space and allocate compute resources to it. File spaces are intended for loading and preparing large quantities of data in an inexpensive inbound staging area and are stored in the SAP Datasphere object store.") :arrow_upper_right: 
-   Filtering is not possible during *Find and Replace*.
-   *Find and replace* is done via the *Data Viewer* whereas in local table it's done via the *Data Editor*.
-   You can access the detailed logs of the find and replace task by navigating to the *Local Tables \(File\)* monitor. For more information, see [Monitoring Local Tables (File)](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/6b2d0073a8684ee6a59d6f47d00ec895.html "Monitor your local tables (file). Check how and when they were last updated and if new data has still to be merged.") :arrow_upper_right:.

For more information on local table *Find and Replace*, see [Maintain Local Table Data](maintain-local-table-data-4bd5e64.md) .

