<!-- loio03191f36e9144b2aaa47b8c9eea039c1 -->

# Partitioning Local Tables

Create partitions for your local table to break your data down into smaller tables, and better manage tables with large volume of data.



<a name="loio03191f36e9144b2aaa47b8c9eea039c1__section_dvb_fjh_1fc"/>

## Introduction to Partitioning

Working with large volume of data can cause memory shortages and take many system resources. One solution can be to use partitions: You create partitions based on one or several columns of your table to break your data down into smaller and more manageable parts. When a table is partitioned, the split is done in such a way that each partition contains a different set of rows of the table, depending on the partition type you have chosen for your data load:

-   *Range*: You select one column of your table that will serve for the partitioning. The table will then be split into several partitions according to the different ranges you have defined. For example, you have set the column Year as the column to serve the partition. This column contains data from the year 2000 to the year 2025. You have defined the partition ranges as follows:

    -   Range 1: From the year 2000 to the year 2005
    -   Range 2: From the year 2006 to the year 2010
    -   Range 3: From the year 2011 to the Year 2015
    -   Range 4: From the year 2016 to the Year 2020
    -   Range 5: From the year 2021 to the Year 2025

    You will get 5 partitions, but they can contain different amounts of data.

-   *Hash*: You select one or more columns of your table that will serve for the partitioning. The table will then be split into the number of partitions you have defined. In our example above, if you have set 15 partitions on the Year column, you will have 15 partitions that will contain the same amount of data.

> ### Restriction:  
> -   Supported data types include:
> 
>     -   String
>     -   Integer, Integer 64, Decimal, hana.SMALLINT, hana.TINYINT
>     -   Date, DateTime, Timestamp
>     -   Binary
> 
>     For more information, see [Partitioning Limits](https://help.sap.com/docs/HANA_CLOUD_DATABASE/f9c5015e72e04fffa14d7d4f7267d897/8dd866a688ec4914a074727a2c800142.html) in the *SAP HANA Cloud, SAP HANA Database* documentation.
> 
> -   Your table must not contain data yet.



<a name="loio03191f36e9144b2aaa47b8c9eea039c1__section_c5k_hjh_1fc"/>

## Procedure

To create partitions for local table:

1.  Go to the *Data Builder*
2.  Create your local table \(for more information, see [Creating a Local Table](creating-a-local-table-2509fe4.md)\)
3.  Go to the *Partitions* tab.
4.  Click *Define Partitions*, select the *Partition Type* and enter its definition:
    -   *Range* Partition:


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
        
        *Column*
        
        </td>
        <td valign="top">
        
        Select the column from which the partition will be defined.

        > ### Note:  
        > If you have defined key columns, you can select only a key column. If you have no key columns defined, all columns with compatible data types can be selected. Note that you won’t be able to define a key column later, until the partitions are in place.


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Partitions*
        
        </td>
        <td valign="top">
        
        Create the number of desired partitions by entering a range for each of them. Note that ranges can't overlap.

        > ### Note:  
        > If you have data outside the defined partition ranges, an *Others* partition will be created to store this data.


        
        </td>
        </tr>
        </table>
        
    -   *Hash* partition:


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
        
        *Columns*
        
        </td>
        <td valign="top">
        
        Select one or several columns from which the partition will be defined.

        > ### Note:  
        > If your table have got key columns, only these columns will be displayed for selection. If you have no key columns defined, all columns with compatible data types can be selected. Note that you won’t be able to define a key column later, until the partitions are in place.


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Number of Hash Partitions*
        
        </td>
        <td valign="top">
        
        Create the number of desired partitions.

        > ### Note:  
        > The default value is 10.


        
        </td>
        </tr>
        </table>
        
        > ### Note:  
        > If your table was created during a data product installation, automatic hash partitioning will happen for entities of large tables. Based on key columns defined for this table, data will be partitioned into 8 partitions.


5.  Save the partition definition and deploy the table.

    > ### Note:  
    > Once deployed, you won’t be able to change the data type of the primary key that has been used for partitioning. But you can still change or delete the partitions until you have added data in your table.


