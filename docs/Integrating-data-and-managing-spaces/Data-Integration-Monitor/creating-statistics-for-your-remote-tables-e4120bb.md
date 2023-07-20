<!-- loioe4120bbb98e44994aa1e0b32ff3f209d -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating Statistics for Your Remote Tables

Create statistics for your remote tables to improve federated query execution.

SAP Datasphere is using SAP HANA smart data integration and SAP HANA smart data access to connect to remote data sources. Objects from remote data sources are made available with so-called SAP HANA virtual tables, which are created when deploying remote tables in SAP Datasphere.

To ensure the best possible performance when accessing your remote tables and provide efficient query execution plans, you can create statistics for your remote tables. SAP Datasphere uses the SAP HANA SQL Optimizer that relies on accurate data statistics for virtual tables in SAP HANA and help you take decisions. For more info, see [SAP HANA SQL Optimizer](https://help.sap.com/viewer/9de0171a6027400bb3b9bee385222eff/latest/en-US/d2948cc2209a407ea2b686c29e72ca50.html).

> ### Restriction:  
> -   Your remote table must be in "remote" data access only.
> 
> -   You can’t create statistics if your remote table is connected via an SAP HANA smart data integration Cloud Data Integration \(CDI\) or an SAP HANA smart data integration ABAP adapters to the following sources:
>     -   SAP HANA smart data integration Cloud Data Integration \(CDI\) adapter
>         -   Cloud Data Integration \(CDI\)
> 
>         -   SAP Marketing Cloud
>         -   SAP S/4HANA Cloud
> 
>     -   SAP HANA smart data integration ABAP adapter:
>         -   SAP ABAP
>         -   SAP BW
>         -   SAP ECC
>         -   SAP S/4HANA On-Premise

Statistics can be created from the *Remote Query Monitor*.

1.  From the *Remote Query Monitor*, select *Remote Query Monitor* \> ** \> *Remote Table Statistics*.

    > ### Note:  
    > By default, the remote tables in data access remote are displayed. However, you can use the drop down list and display all remote tables if you need to see logs related to previous actions on remote tables with data access "replicated".

2.  Select the remote table for which you need to create statistics for, and choose *Statistics* \> *Create Statistics*. Or select the remote table, click <span class="FPA-icons"></span> to navigate to the details screen, and click the button *Create Statistics*.

You can create three types of data statistics object:


<table>
<tr>
<th valign="top">

Statistics type



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

*RECORD COUNT*



</td>
<td valign="top">

Creates a data statistics object that helps the query optimizer calculate the number of records \(rows\) in a table data source. The*RECORD COUNT* type is a table-wide statistic.



</td>
</tr>
<tr>
<td valign="top">

*SIMPLE*



</td>
<td valign="top">

Creates a data statistics object that helps the query optimizer calculate basic statistics, such as min, max, null count, count, and distinct count.



</td>
</tr>
<tr>
<td valign="top">

*HISTOGRAM*



</td>
<td valign="top">

Creates a data statistics object that helps the query optimizer estimate the data distribution.



</td>
</tr>
</table>

Statistics are created for each column of the table and can only be created if the data access is "Remote". Only one data statistics object at a time is allowed per remote table.

> ### Note:  
> Creating statistics can cause a significant workload on the source system. RECORD COUNT is the simplest statistics object, and complexity increases for SIMPLE and HISTOGRAM, which causes heavier workload.

You can update data statistics objects: when you choose the menu *Create Statistics* on a remote table for which data statistics are already available, the windows *Create Statistics* opens, and the existing type of statistics line is marked as active. You can then choose to create another type of statistics or update the existing ones.

You can delete the data statistics objects with the menu *Delete Statistics*.

