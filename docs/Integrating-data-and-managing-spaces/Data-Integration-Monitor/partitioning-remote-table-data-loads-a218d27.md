<!-- loioa218d2715fd54b71a0b2060f4f97cf20 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Partitioning Remote Table Data Loads

Replication capabilities depend on the data type and size. Larger data volumes can cause replication runs to terminate because of memory shortage. From the *Remote Table Monitor* - Details screen, you can create partitions on columns from your dataset and break your data down into smaller and more manageable parts.

Replicating remote tables with larger data volumes without having out-of-memory errors or high memory peaks can sometimes be a challenge for Data modelers. To avoid such situations, you can create partitions per remote tables and thus enable partitioned data transfer of large datasets for supported connection types \(which are all remote table-enabled connections that use a Data Provisioning agent\).

> ### Note:  
> The partition is effective for both snapshot and real-time enabling replication if your remote table is connected to the source via SAP HANA smart data integration. However, it is not working for real-time replication if your remote table is connected via SAP HANA smart data access.



<a name="loioa218d2715fd54b71a0b2060f4f97cf20__section_gdk_tn2_ttb"/>

## Creating Partitions for Your Remote Tables

You can create partitions from the *Remote Table Monitor*– Details screeen:

1.  Click <span class="FPA-icons"></span> of the remote table you need to create partitions for.
2.  Go to the *Partitions* tab and click *Define Partitions*.
3.  In the *Define Partitions* window, define your partitions settings. Note that the available options can differ depending if your remote table is connected via SAP HANA smart data integration or SAP HANA smart data access:


    <table>
    <tr>
    <th valign="top">

    Property


    
    </th>
    <th valign="top">

    Description


    
    </th>
    <th valign="top">

    Comment


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Column*


    
    </td>
    <td valign="top">
    
    Select the column from which the partition will be defined.


    
    </td>
    <td valign="top">
    
    It might happen that you can’t see all the columns available in your dataset because:

    -   Not all data types are supported for partitioning depending on your data sources:
        -   SAP HANA data: Only the following data types are supported

            -   Datetime types: DATE, TIME, TIMESTAMP, SECONDDATE

            -   Numeric types: TINYINT, SMALLINT, INT, BIGINT, DECIMAL\(p,s\)
            -   Character string: NVARCHAR

            For more information, see [Partitioning Limits](https://help.sap.com/viewer/f9c5015e72e04fffa14d7d4f7267d897/2021_01_QRC/en-US/8dd866a688ec4914a074727a2c800142.html).


    -   \(SAP HANA smart data integration only\) If you select a non-key column to define your partitions, you must ensure that the column value of a record in the source data is not changed during replication. Otherwise, data loading may fail because a record with the same key is replicated in two different partitions.
    -   \(SAP HANA smart data access only\) You can create partitions only on key columns.
    -   \(SAP HANA smart data integration only\) You can't define partitions on columns, which contain amounts associated with a currency or quantities associated with a unit.
    -   \(SAP HANA smart data integration only\) For ODP data sources, only the following columns can be selected:

        -   Columns which support where clause of the SELECT statement.
        -   Columns equal to or less than 45 characters.

        > ### Restriction:  
        > For ODP data sources, you can create partitions on non-key columns only if your remote tables have been deployed using a DP agent connection from release 2.5.4.1.
        > 
        > Moreover, if the repository entity comprises filter capabilities, you first need to refresh the remote table in the Data Builder, before you can create partitions.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Parallel Processes* \(SAP HANA smart data integration only\)


    
    </td>
    <td valign="top">
    
    You can define up to 5 parallel processes.


    
    </td>
    <td valign="top">
    
    By default, the partitions are loaded one after the other to control resource consumption.

    > ### Note:  
    > No parallel processes are possible for remote tables connected with an SAP HANA smart data access adapter.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Partitions*


    
    </td>
    <td valign="top">
    
    Create the number of desired partitions by entering a range for each of them.

    > ### Caution:  
    > Ranges must not overlap

    .


    
    </td>
    <td valign="top">
    
    > ### Note:  
    > -   Partitioning requires an in-depth knowledge of the values that are used or are valid for the chosen partitioning column.
    > -   Negative values are not valid for partition bounds of numeric columns and will be converted to 0 at runtime.
    > -   The low bound must be lower than the high bound. The order is checked according to the type of the partition column. Example: for string-like columns, '90' <= DOC\_ID < '100' is not valid, whereas '090' <= DOC\_ID < '100' is valid.
    > -   \(SAP HANA smart data integration only\) Values entered in the bounds for ABAP ODP remote tables must match the ABAP internal format: for example, enter "20210714" if the date is "July 14, 2021".
    > -   \(SAP HANA smart data access only\): Only single-level range partitions are supported by SAP HANA . For more information, see [Range Partitioning](https://help.sap.com/viewer/6b94445c94ae495c83a19646e7c3fd56/latest/en-US/c338627bbb571014ae7d9533861b600f.html).


    
    </td>
    </tr>
    </table>
    
4.  Load a new snapshot of data to start the partitioning immediately, or alternatively create a schedule to load new snapshot later \(or wait until your next schedule run will occur\).

    > ### Note:  
    > Partitions can be updated or deleted using the corresponding menu. But for remote tables connected via SAP HANA smart data access, you must first remove the replicated data before you can delete the partitions.




<a name="loioa218d2715fd54b71a0b2060f4f97cf20__section_onq_yn2_ttb"/>

## Editing Existing Partitions for Your Remote Tables

Whenever it’s necessary, you can update the existing partitions using the menu *Partitions* \> *Edit*.

> ### Example:  
> For example, you want to include a new year in your partitions, or you need to fine granular the existing partitions.

> ### Note:  
> Changes will be reflected only after a new data load via a snapshot replication, a scheduled replication or a real-time initial replication.

> ### Restriction:  
> For remote tables connected via SAP HANA smart data access, you must first remove the replicated data before you can change the partitions.



<a name="loioa218d2715fd54b71a0b2060f4f97cf20__section_smb_b42_ttb"/>

## Deleting Existing Partitions for Your Remote Tables

You can delete an existing partition using the menu *Partitions* \> *Delete*.

> ### Restriction:  
> For remote tables connected via SAP HANA smart data access, you must first remove the replicated data before you can change the partitions.



<a name="loioa218d2715fd54b71a0b2060f4f97cf20__section_sxz_hs2_ttb"/>

## Monitoring Your Partitions

Once the partitioning task is completed, messages with information on partitions is created. You have different places to monitor the partitioned data loads:

-   In the task logs that are created: one log is created per partition and contains detailed information.
-   In the *Remote Query Monitor* by displaying the SQL Statement: The SELECT statements sent by SAP HANA smart data integration to the remote source are listed. The partition information is part of the WHERE clause of the particular statement. For more information, see [Monitoring Remote Queries](monitoring-remote-queries-806d7f0.md).

> ### Note:  
> If your defined ranges don’t cover all the data, additional partitions are created in the background . For example, if rows have been inserted or modified since your last snapshot and they now don’t match any of the defined ranges. An additional partition called 'Others' is created to cover this data.



<a name="loioa218d2715fd54b71a0b2060f4f97cf20__section_hky_dqr_qpb"/>

## Examples of Partitioning

Let's take an example to understand how the partitioning is done. The following partitions for column Calyear, a 4-digit numeric field which can include NULL values, are defined in the UI:

1.  Partition 1: 2000 <= Calyear < 2005
2.  Partition 2: 2005 <= Calyear < 2010
3.  Partition 3: 2010 <= Calyear < 2011

The replica table is partitioned accordingly. An "Others" partition could be added for data, which is not covered by the defined partitions:

Partitions for replica table:

1.  Partition 1: 2000 <= Calyear < 2005
2.  Partition 2: 2005 <= Calyear < 2010
3.  Partition 3: 2010 = Calyear
4.  Partition 4: Others

The partition ranges are also used by SAP HANA smart data integration data load runtime as filters in the SELECT statements sent to the remote source. Usually, the filters are exactly the same as the partition ranges, with the exception of ABAP ODP Extractors. In this case, the filters are as follows:

SAP HANA smart data integration data load runtime for ABAP ODP Extractors:

1.  Partition 1: 0000 <= Calyear <= 1999
2.  Partition 2: 2000 <= Calyear <= 2004
3.  Partition 3: 2005 <= Calyear <= 2009
4.  Partition 4: 2010 = Calyear
5.  Partition 5: 2011 <= Calyear <= 9999
6.  Partition 6: Calyear = NULL

