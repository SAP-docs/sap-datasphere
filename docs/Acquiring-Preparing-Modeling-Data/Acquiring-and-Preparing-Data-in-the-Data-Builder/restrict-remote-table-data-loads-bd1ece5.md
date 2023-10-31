<!-- loiobd1ece5c9f78444c87708ef11eed0a31 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Restrict Remote Table Data Loads

Remove unnecessary columns, create filters or add columns to reduce the volume of data that is loaded in your remote table.



<a name="loiobd1ece5c9f78444c87708ef11eed0a31__prereq_iyj_yvr_hrb"/>

## Prerequisites

-   Your remote table must be already deployed in your space.

-   Remote Tables that use an SAP HANA smart data integration ABAP or SAP HANA smart data integration CDI based connections must have been imported using a DP Agent with version equal or higher than 2.5.4.1.
-   To ensure that the filters won’t impact existing partitioning or statistics, the DWC\_DATAINTEGRATION.read privilege must be assigned to your profile.

> ### Caution:  
> You might check the impact on the existing dependent objects when you create filters, add columns or remove columns.



## Context

Loading larger data volumes can take a long time and cause high memory peaks. To optimize performance and reduce data footprint, you can load only the data you need in your remote table. SAP Datasphere offers several ways to control the volume of data that is loaded in your remote table. From the table editor of the *Data Builder*, you can remove the unnecessary columns, define a central filter to load only the data that is needed, and you can add new columns available in the source, or reinsert previously excluded columns.



## Procedure

1.  Remove columns from your remote table definitions:

    > ### Restriction:  
    > You can’t delete key columns, and columns used in filters, partitioning, associations and hierarchies.

    1.  Go to *Columns* section.

    2.  Select the columns that you want to remove.
    3.  Click <span class="FPA-icons"></span> \(Remove\).

    4.  <span class="SAP-icons"></span> \(Deploy\) your remote table.

    > ### Restriction:  
    > In case you remove columns from the remote table definition compared to the source object \(remote table having less columns than the source entity\), real-time replications don't work for remote tables connected via SAP HANA smart data access or Cloud Connector for SAP HANA on-premise versions lower than 2.0 SPS06.

2.  Creating a filter.

    1.  Go to the *Filter* tab Select *Create filter* and define your filter conditions:


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
        
        Column
        
        </td>
        <td valign="top">
        
        Select the column that will be used to filter your data. 

        > ### Note:  
        > Filtering on columns with the following data types is not supported:
        > 
        > -   For SAP HANA data sources:
        > 
        >     -   Datetime types: DATE, TIME, TIMESTAMP, SECONDDATE
        > 
        >     -   Numeric types: TINYINT, SMALLINT, INT, BIGINT, DECIMAL\(p,s\)
        >     -   Character string: NVARCHAR
        > 
        > -   For ODP data sources, only the following columns can be selected:
        >     -   Columns which support where clause of the SELECT statement.
        > 
        >     -   The length of string columns must not exceed 45 characters. Otherwise, filter values would be cut off after 45 characters.
        > 
        > -   For SAP HANA smart data integration CDI based connections, you can filter only on columns with the following data type:
        >     -   NVARCHAR
        > 
        >     -   DATE
        >     -   BOOLEAN
        >     -   INTEGER
        >     -   BIGINT

        We recommend that you define your filters on columns that are not changing after initial creation. In case of using the advanced property "Triggers Record Primary Keys Only" in SAP HANA smart data integration based connections, filters on non-primary key columns won't work as expected.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Operator
        
        </td>
        <td valign="top">
        
        The filter only supports including conditions. You can choose between *Equal to* and *Between*.

        > ### Note:  
        > Filter conditions on one column will be defined as OR condition, while filters on distinct columns are applied as AND condition


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Values
        
        </td>
        <td valign="top">
        
        You must select existing values only.

        > ### Note:  
        > -   No dynamic filtering such as "last 3 years" is supported.
        > -   If a filter on a specific column is defined, records with null values in this column will not be replicated.


        
        </td>
        </tr>
        </table>
        
    2.  <span class="SAP-icons"></span> \(Deploy\)
    3.  Replicate your data

        > ### Note:  
        > -   When previewing data, filters are applied.
        > -   The task log displayed in the *Remote Table Monitor* details view will summarize the filter conditions used to load the new snapshot of data.
        > -   If you want to change your filter conditions, you need to remove the replicated data first, as filters cannot get changed when the remote table is in data access "replicated".

        > ### Caution:  
        > You might check the impact of your defined filters on data access control filters: after the filter conditions are applied, they may have different outputs or return no results.


3.  Add columns:

    1.  Go to the *Columns* section.

    2.  Click <span class="FPA-icons"></span> \(Add\)
    3.  Select the columns to add and click *OK*. You can add new columns available from the data source, or re-add previously excluded columns.
    4.  <span class="SAP-icons"></span> \(Deploy\)
    5.  Replicate your data.


