<!-- loioa24c71f3ba7548909534d4cb52cefbfc -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Modify a Replication Flow

You can modify an existing replication flow after it has been created. The changes you can make depend on the current status of the replication flow and the kind of updates you want to make.

> ### Tip:  
> This topic explains how to modify replication flow settings in the Data Builder and monitoring views. For monitoring-related information, see [Working With Existing Replication Flow Runs](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/da62e1ee746448e8bc043e1be4377cbe.html "You can pause a replication flow run and resume it later, or stop it completely when it's no longer needed. You can also schedule, monitor premium outbound volume, and configure email notifications for replication flow failures. For more information on how to make changes to an existing replication flow in the Data Builder, see .") :arrow_upper_right:.



## Add an Object to a Replication Flow

You can add more objects to an existing replication flow, so that additional data will be replicated going forward:

> ### Note:  
> If your replication flow runs at a delta interval, you can deploy your changes at anytime. If it runs at a scheduled time or is part of a task chain, you must wait until the status is *Completed* and deploy your changes before the next scheduled run begins.

1.  Open the replication flow in its editor.
2.  Choose <span class="FPA-icons-V3"></span> \(Add source objects\).
3.  Select the objects that you want to add.
4.  Choose *Add Selection*.
5.  Select a *Load Type* and set other properties as appropriate.
6.  Click *Deploy* to deploy your changes.

    > ### Note:  
    > Changes that are not deployed are not taken into account when transporting the replication flow to another tenant.


At the next delta interval or scheduled run, the new object will perform an initial load and/or begin tracking changes for future delta loads.



## Remove an Object from a Replication Flow

You can remove objects from an existing replication flow, so that data for these objects will no longer be replicated:

> ### Note:  
> If your replication flow runs at a delta interval, you can deploy your changes at anytime. If it runs at a scheduled time or is part of a task chain, you must wait until the status is *Completed* and deploy your changes before the next scheduled run begins.

1.  Open the replication flow in its editor.
2.  Choose *Remove* next to the object that you want to remove.
3.  Click *Deploy* to deploy your changes.

    > ### Note:  
    > Changes that are not deployed are not taken into account when transporting the replication flow to another tenant.


Existing data in the target object remains unchanged.



<a name="loioa24c71f3ba7548909534d4cb52cefbfc__section_m1q_mtw_mdc"/>

## Add a Column to an Object

You can add columns to an existing replication object. Adding a column to a replication object changes the target schema and will cause any data already replicated to the target object to be deleted and for replication from the source object to start again.

> ### Note:  
> If your replication flow runs at a delta interval, you can deploy your changes at anytime. If it runs at a scheduled time or is part of a task chain, you must wait until the status is *Completed* and deploy your changes before the next scheduled run begins.

1.  Open the replication flow in its editor.
2.  Add the required column to the target object using the table editor.
3.  Choose *Additional Options* → *Map to Existing Target Object.* 
4.  Click *Deploy* to deploy your changes.

    > ### Note:  
    > Changes that are not deployed are not taken into account when transporting the replication flow to another tenant.


> ### Note:  
> For target objects in the local repository \(SAP Datasphere\), you can no longer use mappings to add columns to your target structure after the replication flow has been saved. For other target types, you can still use mappings to add columns to the target.
> 
> If the target table already exists, make sure that the same changes are applied in the target before running the replication flow again.



## Rename a Target Object

You can rename the target object of a replication object:

> ### Note:  
> If your replication flow runs at a delta interval, you can deploy your changes at anytime. If it runs at a scheduled time or is part of a task chain, you must wait until the status is *Completed* and deploy your changes before the next scheduled run begins.

1.  Open the replication flow in its editor.
2.  Select the replication object that you want to rename.
3.  Choose *Rename Target Object*.
4.  Enter a new technical name.
5.  \[Optional\] Select *Copy Columns from Source Object.* 
6.  Click *Rename.* 
7.  Click *Deploy* to deploy your changes.

    > ### Note:  
    > Changes that are not deployed are not taken into account when transporting the replication flow to another tenant.


> ### Note:  
> If the new target object name already exists in the space, the existing object definition is reused.



## Change Delta Load Run Setting

Configure how delta changes are processed for a replication flow. You can choose whether delta processing runs continuously at the configured delta interval or only when triggered by a schedule or task chain.

1.  Open the replication flow in its editor.
2.  Select *Edit Run Settings*.
3.  Under *Delta Load Run*, select one of the following options:
    -   *At Delta Interval*: The replication flow runs continuously and queries for delta changes based on the specified delta interval.
    -   *At Scheduled Time*: The replication flow processes the available delta changes and then the run completes. The next run begins at the next scheduled time.

4.  Click *Save* to confirm your changes.



## Change Source and Target Thread Limits

You can change the maximum number of threads that can be used when reading data from the source system:

1.  Open the replication flow in its editor.
2.  Select *Edit Run Settings*.
3.  Update the *Source Thread Limit* and *Target Thread Limit* values.
4.  Save the changes.
5.  Click *Deploy* to deploy your changes.

    > ### Note:  
    > Changes that are not deployed are not taken into account when transporting the replication flow to another tenant.




## Change the Load Type of an Object

You can change the load type of replication objects in a running replication flow:

1.  Open the replication flow in its editor.
2.  Select the replication object whose load type you want to change.
3.  In the properties panel, select the required load type.
4.  Click *Deploy* to deploy your changes.

    > ### Note:  
    > Changes that are not deployed are not taken into account when transporting the replication flow to another tenant.




<a name="loioa24c71f3ba7548909534d4cb52cefbfc__section_pn3_1xf_xdc"/>

## Changing the Content Type \(ABAP-Based Source Systems Only\)

When working with ABAP-based source systems, you can switch between *Template Type* and *Native* \(See [Creating a Replication Flow](creating-a-replication-flow-25e2bd7.md)\).

> ### Restriction:  
> -   You can't change the content type for replication flows created before wave 2025.04.
> -   You must consider the impact on other replication flows that use the same source objects.
> -   You must be certain about the existing column data types in the existing target. Otherwise, the replication flow deployment or run will fail due to a column data type mismatch between the source and target.
> -   Changing the content type selection will affect the source column data types \(date, time, and timestamp\) for all existing replication objects in the replication flow.

1.  Open the replication flow in its editor.
2.  Change the content type.


    <table>
    <tr>
    <th valign="top">

    Data Types
    
    </th>
    <th valign="top">

    Native Type
    
    </th>
    <th valign="top">

    Template Type
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Date
    
    </td>
    <td valign="top">
    
    String \(length = native content length\)
    
    </td>
    <td valign="top">
    
    Date
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Time

    > ### Note:  
    > Time is not supported if your target is a local table \(file\). See [Unsupported Data Types in a Replication Flow](unsupported-data-types-in-a-replication-flow-6c770bb.md)


    
    </td>
    <td valign="top">
    
    String \(length = native content length\)
    
    </td>
    <td valign="top">
    
    Time
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Boolean
    
    </td>
    <td valign="top">
    
    String \(length = native content length\)
    
    </td>
    <td valign="top">
    
    Boolean
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Timestamp
    
    </td>
    <td valign="top">
    
    Decimal \(Precision = abapLength, scale = abapDecimals\)
    
    </td>
    <td valign="top">
    
    Timestamp
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Raw
    
    </td>
    <td valign="top">
    
    Binary
    
    </td>
    <td valign="top">
    
    String/Binary
    
    </td>
    </tr>
    </table>
    
3.  Review any required data type conversions.
4.  Click *Deploy* to deploy your changes.

    > ### Note:  
    > Changes that are not deployed are not taken into account when transporting the replication flow to another tenant.


When changing the content type, you must convert some data types to ensure that they are supported by the selected content type:

