<!-- loioe57e12d39535439eb078078228c6f7bf -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Preview and Edit Local Table \(File\) Data

Local Tables \(File\) are intended for file storage with large amount of data. Due to the volume of data, some actions are limited compared to what you can do in the *Data Builder*.

> ### Caution:  
> To perform the following actions, your table :
> 
> -   Must have the status *Deployed*
> -   Contain at least one key column



<a name="loioe57e12d39535439eb078078228c6f7bf__section_h54_ll4_12c"/>

## Previewing Data in the Data Preview

To preview data, from the table editor, click <span class="SAP-icons-V5"></span> \(Data Viewer\).

> ### Note:  
> Data preview of local tables \(file\) displays only active records. This is different to local tables where the data preview displays records from the delta capture entity. For more information, see [Maintain Local Table Data](maintain-local-table-data-4bd5e64.md)



<a name="loioe57e12d39535439eb078078228c6f7bf__section_fph_dm4_12c"/>

## Reorder Your data

You can decide how you want to display your data:

-   **Reorder**: Drag and drop your columns to reorder them.
-   **Sort**: Click on the column header and click <span class="SAP-icons-V5"></span> \(Sort Ascending\) or <span class="SAP-icons-V5"></span> \(Sort Descending\).



<a name="loioe57e12d39535439eb078078228c6f7bf__section_whk_h44_12c"/>

## Customize Your View

You can choose which columns from your table you want to display. Click <span class="FPA-icons-V3"></span> \(Columns Settings\) and select the columns to show in the preview.



<a name="loioe57e12d39535439eb078078228c6f7bf__section_fdf_q44_12c"/>

## Filter Your Data

-   Click on the column header and <span class="FPA-icons-V3"></span> \(Filter\) to open the *Define Filter* dialog. Click <span class="FPA-icons-V3"></span> \(Add Filter\), select a column to filter on, a filtering option, and a value. You can apply several filters.



<a name="loioe57e12d39535439eb078078228c6f7bf__section_qkd_t44_12c"/>

## Find and Replace Strings

Find & Replace operation on local tables \(File\) works slighlty differently compared to local tables:

-   Due to high volume of data, the *Find and Replace* action is run as an asynchronous task using Apache Spark application 300. If the find and replace task uses more memory than the resources allowed by the application 300, the task will fail. For more information, see [Create a File Space to Load Data in the Object Store](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/947444683e524cfd9169d7671b72ba0c.html "Create a space with SAP HANA data lake files storage in the object store, allocate compute resources and assign one or more users to allow them to start acquiring and preparing data. File spaces are intended for loading and preparing large quantities of data in an inexpensive inbound staging area.") :arrow_upper_right: 
-   Find and replace is done via the *Data Viewer* whereas in local table it's done via the *Data Editor*.
-   You can access the detailed logs of the find and replace task via the *Find and Replace Log* button \(in the *Table Editor* toolbar section\).

For more information on local table *Find and Replace*, see [Maintain Local Table Data](maintain-local-table-data-4bd5e64.md) .

