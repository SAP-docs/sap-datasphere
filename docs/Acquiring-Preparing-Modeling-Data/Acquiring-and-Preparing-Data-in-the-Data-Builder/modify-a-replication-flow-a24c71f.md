<!-- loioa24c71f3ba7548909534d4cb52cefbfc -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Modify a Replication Flow

Whether and how you can change the settings for a replication flow depends on several factors.

> ### Tip:  
> This text explains the options for editing the replication flow itself \(in the *Data Builder*\). For monitoring-related information, see [Working With Existing Replication Flow Runs](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/da62e1ee746448e8bc043e1be4377cbe.html "You can pause a replication flow run and resume it at a later point in time, or you can stop it completely.") :arrow_upper_right:.



<a name="loioa24c71f3ba7548909534d4cb52cefbfc__section_m1q_mtw_mdc"/>

## Adding Columns

For target objects in the local repository \(SAP Datasphere\), you can no longer use the mapping function to add columns to your target structure after you save the replication flow. However you can still add columns manually using the table editor, then select the relevant target object in the *Data Builder* and choose *Additional Options* \> *Map to Existing Target Object*. Then deploy and run the replication flow again.

For other target objects, you can use the mapping function to add columns to your target structure. Make sure to redeploy the replication flow when you're done and \(if the target table already exists\) manually implement the same changes in the target table structure before running the replication flow.



<a name="loioa24c71f3ba7548909534d4cb52cefbfc__section_syb_stw_mdc"/>

## Changing an Active Replication Flow

You can make the following changes to a replication flow with status *Active* without having to stop the replication flow first. This can helpful, for example, if your replication flow contains a lot of objects so that stopping and restarting it would cause disproportionate effort.

-   Add or remove individual replication objects:

    -   If you don't want an object to be replicated anymore, choose the *Remove* button to the right of the object, then deploy the flow once again. Any data for the removed objects that already exists in the target \(from previous runs\) remains as-is.

    -   To add one or more objects, choose <span class="FPA-icons-V3"></span> \(Add source objects\), select the relevant objects as usual, and then deploy the flow once again.

        > ### Note:  
        > When you add one or more objects, these objects start getting replicated directly after you save your changes.


-   Change the delta interval: In the *Data Builder*, go to the properties panel for the flow and change the values in the *Delta Load Interval* section as required, then deploy the flow once again. The change takes effect after the next delta with the previous interval value is completed. Example: You have an active replication flow with a delta interval of one hour. The next delta is due in 30 minutes. If you change the delta interval to 20 minutes, the next delta will still start in 30 minutes, and the following one 20 minutes after completion of the first one.

-   Change the source or target thread limit: Choose <span class="FPA-icons-V3"></span> \(Browse source settings\) or <span class="FPA-icons-V3"></span> \(Browse target settings\), respectively, change the value as required, save your change, and deploy the flow again.


To change the load type, delete all before loading setting, projections, or filters for a replication flow, you need to stop the replication flow, make the required changes, deploy the replication flow, and then run it again.

> ### Note:  
> If you install the data product corresponding to an active replication flow via SAP Business Data Cloud, you don't need to stop the run: Reinstalling the data product will alter the existing table and apply the changes by redeploying the replication flow. An initial load will then happen, taking into consideration the new changes.



<a name="loioa24c71f3ba7548909534d4cb52cefbfc__section_smp_xtw_mdc"/>

## Exporting and Importing a Replication Flow

You can export a replication flow and import it into another space \(see [Importing and Exporting Objects in CSN/JSON Files](../Creating-Finding-Sharing-Objects/importing-and-exporting-objects-in-csn-json-files-f8ff062.md)\).

> ### Note:  
> For you to be able to work with an imported replication flow, a suitable connection has to be available in the space to which you imported the replication flow. \(Connection information is space-dependent and consequently not part of the information that gets exported.\)



<a name="loioa24c71f3ba7548909534d4cb52cefbfc__section_pn3_1xf_xdc"/>

## Changing the Content Type \(ABAP-Based Source Systems Only\)

When you have created your replication flow, you have choosen a content type \(*Template Type* or *Native Type*\) to load your data and you now want to change it.

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



<a name="loioa24c71f3ba7548909534d4cb52cefbfc__section_a3s_yx1_y2c"/>

## Renaming a Target Object

You can rename an existing target object:

1.  Open the replication flow in the replication flow editor.
2.  Select the replication object you want to rename.
3.  Click *...* \> *Rename Target Object*.
4.  Update the techincal name as desired.

    > ### Note:  
    > If you rename the object with a name that already exists for another object in the space, it will reuse the definition of this existing object.

5.  \[Optional\] You can select *Copy Columns from Source Object* if you want to do so.

    > ### Note:  
    > By default, the new target object will inherit columns from the old target object. If you select this option, columns will be copied from the source instead.

6.  Click *Rename*.
7.  Save and Redeploy

