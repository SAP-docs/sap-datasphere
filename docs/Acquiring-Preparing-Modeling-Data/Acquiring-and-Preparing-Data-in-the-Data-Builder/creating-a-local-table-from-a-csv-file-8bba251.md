<!-- loio8bba251c78874736963703cff56b1b74 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Local Table from a CSV File

Import a `.csv` file to create a table and fill it with the data from the file.



<a name="loio8bba251c78874736963703cff56b1b74__context_drj_k2f_ypb"/>

## Context

> ### Note:  
> This procedure explains how to upload a CSV file to create a new local table in SAP Datasphere with the possibility to perform some data transformations during the upload. To load data into an existing local table \(without transformations\), use the <span class="FPA-icons"></span> \(Upload Data From CSV File\) tool in the table editor \(see [Creating a Local Table](creating-a-local-table-2509fe4.md)\).



## Procedure

1.  In the side navigation area, click ![](../Creating-Finding-Sharing-Objects/images/Data_Builder_f73dc45.png) \(*Data Builder*\), select a space if necessary, and click *Import* \> *Import CSV File* to open the editor.

2.  Click *Select Source File*, navigate to, and select the CSV file you want to upload.

    > ### Note:  
    > The file extension must be `*.csv`. The file size must not exceed 200 MB.

3.  Review the following options, and then click *Upload* to open your file in SAP Datasphere:


    <table>
    <tr>
    <th valign="top">

    Option


    
    </th>
    <th valign="top">

    Description


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
        Use first row as column header.


    
    </td>
    <td valign="top">
    
        Select if your file contains column headers in its first line.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        CSV Delimiter


    
    </td>
    <td valign="top">
    
        Select the character used to signify the boundary between columns. In general, the default value, ***Auto-detect*** is sufficient.


    
    </td>
    </tr>
    </table>
    
    The preview page shows a data preview on the left and a side panel showing the properties of the file or of a selected column, on the right.

4.  \[optional\] In the side panel, review the list of columns to be created. Hover over a column in the list and click *Details* to view and modify the properties of the column \(see [Column Properties and Profiling](column-properties-and-profiling-32654ad.md)\).

    > ### Note:  
    > The values of a hana.REAL column are automatically converted when their format is invalid.
    > 
    > > ### Example:  
    > > The value ***1.1*** will be read and written as ***1.100000023841858***.
    > 
    > This will cause issues if this column is used as a calculated column. In that case, avoid conversion by setting the column to another data type.

5.  \[optional\] Perform data preparation transformations to modify the list of columns to be created, to delete rows, and to modify data in cells \(see [Apply Data Transforms](apply-data-transforms-3f0d747.md)\).

6.  When you have performed all necessary transformations and validations, click *Deploy* to open the *Deploy Table* dialog.

7.  Enter a business and technical name for your table and click *Deploy* to create the table and deploy it with the imported data.

    You are returned to the *Data Builder* start page and will receive a notification when the deployment is complete and the table can be opened in the table editor.


