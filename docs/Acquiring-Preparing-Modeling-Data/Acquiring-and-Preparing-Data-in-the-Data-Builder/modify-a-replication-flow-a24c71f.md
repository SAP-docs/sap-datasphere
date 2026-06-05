<!-- loioa24c71f3ba7548909534d4cb52cefbfc -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Modify a Replication Flow

You can modify an existing replication flow after it has been created. The changes you can make depend on the current status of the replication flow and the kind of updates you want to make.

> ### Tip:  
> This topic explains how to modify replication flow settings in the Data Builder and monitoring views. For monitoring-related information, see [Working With Existing Replication Flow Runs](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/da62e1ee746448e8bc043e1be4377cbe.html "You can pause a replication flow run and resume it later, or stop it completely when it's no longer needed. You can also schedule, monitor premium outbound volume, and configure email notifications for replication flow failures. For more information on how to make changes to an existing replication flow in the Data Builder, see .") :arrow_upper_right:.



<a name="loioa24c71f3ba7548909534d4cb52cefbfc__section_m1q_mtw_mdc"/>

## Adding Columns

For target objects in the local repository \(SAP Datasphere\), you can no longer use mappings to add columns to your target structure after the replication flow has been saved.

Instead, you can:

1.  Add the required columns manually in the table editor.
2.  Select the target object in the Data Builder.
3.  Choose *Additional Options* → *Map to Existing Target Object.* 
4.  Redeploy and run the replication flow again.

For other target types, you can still use mappings to add columns to the target structure.

If the target table already exists, make sure that the same structural changes are manually applied in the target before running the replication flow again.



<a name="loioa24c71f3ba7548909534d4cb52cefbfc__section_syb_stw_mdc"/>

## Modifying an Active Replication Flow

You can make certain changes to a replication flow with status*Active*without stopping it first.

This can be useful for replication flows containing many objects, where stopping and restarting the entire flow would require additional effort.

You can:

-   Add or remove replication objects
-   Change the delta interval
-   Change source or target thread limits
-   Change delta load run behavior



### Adding or Remove Replication Objects

To remove an object:

1.  Choose *Remove* next to the object.
2.  Deploy the replication flow again.

    Existing target data for the removed object remains unchanged.


To add objects:

1.  Choose <span class="FPA-icons-V3"></span> \(Add source objects\).
2.  Select the required objects.
3.  Deploy the replication flow again.

    > ### Note:  
    > When transporting replication flow changes using cTMS export and import, adding or removing replication objects supports live patching. To apply these changes without stopping the active replication flow, enable the *User Rights* checkbox during cTMS export.




### Changing the Delta Interval

1.  Open the replication flow.
2.  Choose *Edit Run Settings.* 
3.  Under *Delta Load Run*, select one of the following options:
    -   *At Delta Interval*
    -   *At Schedule Time*


With *At Delta Interval*, the replication flow runs as a long-running flow. The runtime continuously retries delta processing based on the configured delta interval.

*With At Schedule Time*, the replication flow processes the available delta records and then completes the run. SAP Datasphere becomes responsible for triggering the next delta execution.

You can configure this setting in the replication flow properties panel or in the monitoring view by editing the *Run Settings*

> ### Note:  
> Changing the *Delta Load Run* setting does not require redeployment.



### Changing Source Thread Limits

1.  Choose <span class="FPA-icons-V3"></span> \(Browse source settings\) or <span class="FPA-icons-V3"></span> \(Browse target settings\) 
2.  Update the thread limit.
3.  Save the changes.
4.  Deploy the replication flow again.



### Changes That Require Stopping the Replication Flow

To change the following settings, you must:

1.  Stop the replication flow
2.  Make the required changes
3.  Deploy the replication flow
4.  Run the replication flow again

This applies to:

-   Load type
-   Delete All Before Loading
-   Projections
-   Filters

> ### Note:  
> If you install the data product corresponding to an active replication flow via SAP Business Data Cloud, you don't need to stop the run: Reinstalling the data product will alter the existing table and apply the changes by redeploying the replication flow. An initial load will then happen, taking into consideration the new changes.



## Renaming a Target Object

You can rename an existing target object:

1.  Open the replication flow in the replication flow editor.
2.  Select the replication object you want to rename.
3.  Click *...* \> *Rename Target Object*.
4.  Update the technical name as desired.

    > ### Note:  
    > If you rename the object with a name that already exists for another object in the space, it will reuse the definition of this existing object.

5.  \[Optional\] You can select *Copy Columns from Source Object* if you want to do so.

    > ### Note:  
    > By default, the new target object will inherit columns from the old target object. If you select this option, columns will be copied from the source instead.

6.  Click *Rename*.
7.  Save and Redeploy



## Switching From or To The Delta Only Load Type

You can switch the load type of an existing replication flow to or from Delta Only to another supported load type. Note that when you switch from one load type to another, you need to redeploy so that the changes can be applied. The replication flow will run with the new load type as if it were just created from scratch.



<a name="loioa24c71f3ba7548909534d4cb52cefbfc__section_smp_xtw_mdc"/>

## Exporting and Importing a Replication Flow

You can export a replication flow and import it into another space \(see [Importing and Exporting Objects in CSN/JSON Files](../Creating-Finding-Sharing-Objects/importing-and-exporting-objects-in-csn-json-files-f8ff062.md)\).

> ### Note:  
> For you to be able to work with an imported replication flow, a suitable connection has to be available in the space to which you imported the replication flow. \(Connection information is space-dependent and consequently not part of the information that gets exported.\)



<a name="loioa24c71f3ba7548909534d4cb52cefbfc__section_pn3_1xf_xdc"/>

## Changing the Content Type \(ABAP-Based Source Systems Only\)

When you have created your replication flow, you have chosen a content type \(*Template Type* or *Native Type*\) to load your data and you now want to change it.

For more information, see [Creating a Replication Flow](creating-a-replication-flow-25e2bd7.md)

> ### Restriction:  
> -   You can't change the content type for replication flows created before wave 2025.04.
> -   Your replication flow can't be in status "Running".
> -   You must consider the impact on other replication flows that use the same source objects.
> -   You must be certain about the existing column data types in the existing target. Otherwise, the replication flow deployment or run will fail due to a column data type mismatch between the source and target.
> -   Changing the content type selection will affect the source column data types \(date, time, and timestamp\) for all existing replication objects in the replication flow.

When changing the content type, you must convert some data types to ensure that they are supported by the selected content type:


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

