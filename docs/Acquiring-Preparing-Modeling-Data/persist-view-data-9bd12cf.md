<!-- loio9bd12cf116ae40e09cdba8b60cf75e11 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Persist View Data

Improve the performance while working with views by persisting the view data, and scheduling regular updates to keep your data up-to-date.

By default a view is run every time it is accessed and, if the view is complex or a large amount of data is processed, this may impact the performance of other views or dashboards built on top of it. You can improve performance by persisting the view data and you can schedule regular updates to keep the data fresh.

> ### Note:  
> If your view consumes remote tables, check for additional and potential limitations. See [Integrating Data via Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/eb85e157ab654152bd68a8714036e463.html "Connections provide access to data from a wide range of remote systems, cloud as well as on-premise, SAP as well as Non-SAP, and partner tools. They allow users assigned to a space to use objects from the connected remote system as source to acquire, prepare and access data from those sources in SAP Datasphere. In addition, you can use certain connections to define targets for replication flows.") :arrow_upper_right:.
> 
> While persisting complex views, see [Persisted Views and Memory Consumption](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/e3d04951a4a344c28b25b2b1b13bf3d8.html "You want to persist a complex view and consider how it affects the memory consumption.") :arrow_upper_right:.



When opening your view, in the *Properties* panel, under *Data Persistence*, you can see if your view has been made persisted or not.

> ### Note:  
> You can monitor persisted views in the *Data Integration Monitor*, under *Views*. You can access it directly by clicking <span class="SAP-icons-V5"></span> \(Views Monitor\). For more information, see [Persisting and Monitoring Views](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/9af04c990f294fd28c00f46763dd8b0d.html "From Data Integration Monitor > > Views , you can monitor views that have been created in the Data Builder. You can persist these views (direct run or via a schedule) to make them available locally to improve the performance when accessing your data. You can monitor the existing persisted views to keep control of your data sizing and free up memory space.") :arrow_upper_right:.


<table>
<tr>
<th valign="top">

Information

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Data Access*

</td>
<td valign="top">

Shows how you currently access your view.

-   *Persisted*: The view is persisted can be used immediately.
-   *Partially Persisted*: Not all view data has been persisted. If your view contains an input parameter, only records that match the input parameter default value are persisted.
-   *Virtual*: The view is accessed directly, no intermediate persistency is used. Or the view was persisted and has now been turned into virtual to free up memory space, for example.



</td>
</tr>
<tr>
<td valign="top">

*Status*

</td>
<td valign="top">

Shows the status of the persisted view.

-   *Available*: The persisted view is available and can be used.
-   *Loading*: The persisted view is currently creating or updating. You might need to refresh your screen until the loading is completed to get the final status. Until then the virtual access or the old persisted data is used if the view is accessed.
-   *Error*: Something goes wrong during the load of the data to the persisted table. The old persisted data is used or if the view was not successfully loaded before, the data is still accessed via virtual access \(status is virtual\). You need to fix the error to be able to complete the persisted view creation or update.



</td>
</tr>
<tr>
<td valign="top">

*Last updated*

</td>
<td valign="top">

Shows when the persisted view was last updated.

</td>
</tr>
</table>

You can perform actions on data by clicking *Data Persistence*:

-   *Start Data Persistence*: Start a new data persistence to update or create the persisted view.

    > ### Note:  
    > You can set up a view as persisted even if it has been created on top of remote data.

-   *Remove Persisted Data*: Remove the data that have been persisted in the view and switch the access back to virtual.




<a name="loio9bd12cf116ae40e09cdba8b60cf75e11__section_x5n_rkq_2rb"/>

## Schedule Data Persistence Tasks

Schedule Data Persistence

From this menu, you can :

-   *Create Schedule*: Select the relevant persisted view and create a simple or recurring schedule for your view. You define your scheduling options and thus ensure that you always have an up-to-date persisted view.

    *Edit Schedule*: Your scheduling options need to be updated? You can adapt them to your needs at any time from this menu.

-   *Delete Schedule*: You don't need to schedule a Data Persistence task anymore? Then you can simply delete it from this menu.
-   *Assign Schedule To Me*: Become the owner of the schedule.
-   *Pause Schedule*: Pause the scheduled task
-   *Resume Schedule*: Resume the pause scheduled task

> ### Note:  
> You need to authorize SAP to run the recurring scheduled tasks on your behalf. You can do so via the message that is displayed at the top of the monitor, or in your profile settings under *Schedule Consent Settings*.

For more information, see [Schedule a Data Integration Task (Simple Schedule)](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/7c11059ed3314e1fb753736b7867512c.html "You can schedule or unschedule data integration tasks such as remote data replication, data persistence, data flow, replication flow, or task chains runs. You may also pause and then later resume the run of scheduled tasks.") :arrow_upper_right:.



## Persisted Views and Input Parameters

Data persistence can be run in case a view contains a parameter only if the following prerequisites are met:

-   The view contains one single input parameter,
-   The input parameter has a default value maintained.

If a view contains several input parameters, or if the input parameter has no default value, the view can’t be persisted.

Once persisted, the view takes the data access value *Partially Persisted* because only records that match the input parameter default value are persisted.



<a name="loio9bd12cf116ae40e09cdba8b60cf75e11__section_f2z_cf5_rnb"/>

## Persisted Views and Deployement

When you deploy a persisted view, you need to consider the following cases:

-   If you update or redeploy a persisted view, you need the right permission level \(Data Integration - Update\). For more information, see [Privileges and Permissions](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right:. Note that after a redeployment, the data persistence might be deleted and the data access could be changed back to virtual for views with structural changes. This will happen as soon as the underlying database object is recreated as part of the deployment. This can be seen in the *Data Access* status in the *View Builder* or in the *Data Integration Monitor* \> *Views*. The update of the data persistence has to be triggered again.
-   If the view uses other views that were changed but not yet deployed, they are deployed as well. If these views are persisted, the persistence is deleted as well.
-   If the view uses other views that were not changed, these views are not touched by the deployment and therefore the persistence is still available
-   If you update or redeploy a view while you are persisting data, the persistence will fail. In this case, try again to persist the view or wait until the next scheduled run.
-   If the persisted view is consuming a view for which a data access control has changed \(a data access control is added or removed, or its assignment has changed\), then the persistence of your parent view is removed when the underlying view is redeployed.



<a name="loio9bd12cf116ae40e09cdba8b60cf75e11__section_ylk_gf5_rnb"/>

## Persisted Views and Data Access Control

While defining *Data Access Control* in your view, you need to consider the impact on the persistency. For more information, see [Persisted Views and Data Access Control](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/7a4a983611cc4efb9415e6f3db310eaa.html "When Data Access Control is defined, it can impact the data persistence. Depending on where the Data Access Control is set, it might prevent you from persisting a view.") :arrow_upper_right:.

