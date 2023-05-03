<!-- loio9bd12cf116ae40e09cdba8b60cf75e11 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Persist View Data

Improve the performance while working with views by persisting the view data, and scheduling regular updates to keep your data up-to-date.

By default a view is run every time it is accessed and, if the view is complex or a large amount of data is processed, this may impact the performance of other views or dashboards built on top of it. You can improve performance by persisting the view data and you can schedule regular updates to keep the data fresh.

> ### Note:  
> If your view consumes remote tables, check for additional and potential limitations. See [Integrating Data via Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/eb85e157ab654152bd68a8714036e463.html "Connections provide access to data from a wide range of sources, cloud as well as on-premise sources, SAP as well as Non-SAP sources, and partner tools. They allow space members to use objects from the connected source to acquire, prepare and access data from those sources in SAP Datasphere. To connect to different sources, SAP Datasphere provides different connection types.") :arrow_upper_right:.
> 
> While persisting complex views, see [View Persistency and Memory Consumption](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/e3d04951a4a344c28b25b2b1b13bf3d8.html "You want to persist a complex view and consider how it affects the memory consumption.") :arrow_upper_right:.



When opening your view, in the *Properties* panel, under *Persistency*, you can see if your view has been made persisted or not.

> ### Note:  
> You can monitor persisted views in the *Data Integration Monitor*, under the tab *View Persistency Monitor*. You can access it directly by clicking <span class="SAP-icons"></span> \(Open Monitor\). For more information, see [Adding and Monitoring Persisted Views](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/9af04c990f294fd28c00f46763dd8b0d.html "In the Data Integration Monitor, you can add and monitor, and schedule persisted views. Persisted views are available locally and can be used directly to improve performance when accessing your data, for your models or stories, for example. You can monitor the existing persisted views to keep control of your data sizing and free up memory space.") :arrow_upper_right:.


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

See how you currently access your view.

-   *Persisted*: The view is persisted can be used immediately.
-   *Virtual*: The view is accessed directly, no intermediate persistency is used. Or the view was persisted and has now been turned into virtual to free up memory space, for example.



</td>
</tr>
<tr>
<td valign="top">

*Status*



</td>
<td valign="top">

Get the status of the persisted view.

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

See when the persisted view was last updated.



</td>
</tr>
</table>

You can perform actions on data by clicking *View Persistency Actions*:

-    *Load New Snapshot*: Load new data to update or create the persisted view.

-    *Remove Persisted Data*: Remove the data that have been persisted in the view and switch the access back to virtual.




<a name="loio9bd12cf116ae40e09cdba8b60cf75e11__section_x5n_rkq_2rb"/>

## Schedule View Persistency Tasks

Define, edit or delete scheduling options for your persisted views.

For more information, see [Schedule a Data Integration Task](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/7c11059ed3314e1fb753736b7867512c.html "You can schedule or unschedule data integration tasks such as remote table replication, persisting views, or data flow execution. You may also pause and then later resume execution of scheduled tasks.") :arrow_upper_right:.



<a name="loio9bd12cf116ae40e09cdba8b60cf75e11__section_f2z_cf5_rnb"/>

## Persistency and Deployement

When you deploy a persisted view, you need to consider the following cases:

-   If you update or redeploy a persisted view, you need the right permission level \(Data Integration - Update\). For more information, see [Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/862b88eed50244049d41361ba3290456.html#loio1c4bf1ee5cdf4333807b22568ce0d874). Note that after a redeployment, the persistency might be deleted and the data access could be changed back to virtual for views with structural changes. This will happen as soon as the underlying database object is recreated as part of the deployment. This can be seen in the *Data Access* status in the *View Builder* or in the *Data Integration Monitor* \> *View Persistency Monitor*. The update of the persistency has to be triggered again.
-   If the view uses other views that were changed but not yet deployed, they are deployed as well. If these views are persisted, the persistency is deleted as well.
-   If the view uses other views that were not changed, these views are not touched by the deployment and therefore the persistency is still available
-   If you update or redeploy a view while view persistency is running, view persistency will fail. In this case, try again to persist the view or wait until the next scheduled run.
-   If the persisted view is consuming a view for which a data access control has changed \(a data access control is added or removed, or its assignment has changed\), then the persistency of your parent view is removed when the underlying view is redeployed.



<a name="loio9bd12cf116ae40e09cdba8b60cf75e11__section_ylk_gf5_rnb"/>

## Persistency and Data Access Control

While defining *Data Access Control* in your view, you need to consider the impact on the persistency. For more information, see [View Persistency and Data Access Control](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/7a4a983611cc4efb9415e6f3db310eaa.html "When Data Access Control is defined, it can impact the View Persistency. Depending on where the Data Access Control is set, it might prevent you from persisting a view.") :arrow_upper_right:.

