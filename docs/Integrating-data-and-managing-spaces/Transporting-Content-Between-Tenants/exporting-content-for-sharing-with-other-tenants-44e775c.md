<!-- loio44e775c3b7d24d2483caaf02c598bc21 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Exporting Content for Sharing with Other Tenants

Users with the Administrator or Space Administrator role can export content from one or more spaces for sharing with other tenants.



## Context

You can share content across tenants from one or more landscapes and set access rights for each sharing destination, for example, to allow other tenants to update a package and export it again.

Each tenant can store up to 300 MB of exported content for free in the *My Content* area.

The following object types can be exported and imported via the <span class="FPA-icons"></span> \(*Transport*\) app:


<table>
<tr>
<th valign="top">

Object Type



</th>
<th valign="top">

Details



</th>
</tr>
<tr>
<td valign="top">

Local Tables



</td>
<td valign="top">

The definition of a local table contains the structure of the table only, and does not have dependencies on any other objects.



</td>
</tr>
<tr>
<td valign="top">

Remote Tables



</td>
<td valign="top">

The definition of a remote table contains information about its connection. Before importing a remote table, you must create the relevant connection with an identical technical name in the receiving space.



</td>
</tr>
<tr>
<td valign="top">

Views



</td>
<td valign="top">

The definition of a view contains the definitions of all its sources and any used data access controls. When you export a view, these objects are exported too.



</td>
</tr>
<tr>
<td valign="top">

Data Flows



</td>
<td valign="top">

The definition of a data flow contains the definitions of all its sources and its target table. When you export a data flow, these objects are exported too.



</td>
</tr>
<tr>
<td valign="top">

Intelligent Lookups



</td>
<td valign="top">

The definition of an intelligent lookup contains the definitions of its input and lookup entities. When you export an intelligent lookup, these entities are exported too.



</td>
</tr>
<tr>
<td valign="top">

Analytic Models



</td>
<td valign="top">

The definition of an analytic model contains the definitions of its fact and dimension sources. When you export an analytic model, these entities are exported too.



</td>
</tr>
<tr>
<td valign="top">

E/R Models



</td>
<td valign="top">

The definition of an E/R model does not include the objects that it visualizes as dependencies. These visualized objects must be selected manually.



</td>
</tr>
<tr>
<td valign="top">

Data Access Controls



</td>
<td valign="top">

The definition of a data access control contains the definition of its permissions entity. When you export a data access control, the permissions entity is exported too.



</td>
</tr>
<tr>
<td valign="top">

Task Chains



</td>
<td valign="top">

The definition of a task chain contains the definition of all the objects that it automates. When you export a task chain, these objects are exported too.



</td>
</tr>
</table>

> ### Note:  
> Only local and remote tables, views, data flows, and E/R models can be selected for exporting in SAP Datasphere tenants provisioned prior to version 2021.03. While objects created in SAP Datasphere tenants provisioned prior to version 2021.03 can be transported to tenants provisioned after that date, transport of objects in the other direction is not possible.



## Procedure

1.  In the side navigation area, click <span class="FPA-icons"></span> \(*Transport*\)** \> **<span class="FPA-icons"></span> \(*Export*\) and then click :heavy_plus_sign:.

2.  On the *Choose content* page, expand the *SPACE* folder to show your spaces, select the objects you want to export, and then click *Next*.

    You can select a space to include all its objects, or expand it to select individual objects within it.

    You can select objects from any space of which you are a member, and select objects from more than one space.

    If an object depends on other objects, then they will also be selected. For example, when you select a view, all its sources and any used data access controls will be selected.

    > ### Note:  
    > If an object selected for export depends on one or more objects that have been shared from other spaces \(see [Sharing Tables and Views To Other Spaces](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/internal/en-US/64b318f8afd74bb78467cf56eb44294f.html "Share a Data Builder table or view to another space to allow that space&apos;s members to use it as a source for their objects.") :arrow_upper_right:\), then you must be a member of each of those spaces in order to include all the necessary objects in your package.
    > 
    > If you are not a member of one or more sharing spaces, then you can still export your package \(no error will be displayed\), but it will fail to import correctly unless all the missing objects are already present in the target tenant.
    > 
    > You can review all the dependencies of your object by using the *Impact and Lineage Analysis* tool \(see [Impact and Lineage Analysis](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/internal/en-US/9da4892cb0e4427ab80ad8d89e6676b8.html "The Impact and Lineage Analysis diagram helps you to understand the lineage (or data provenance) of a selected object, along with its impacts - the objects that depend on it and that will be impacted by any changes that are made to it.") :arrow_upper_right:\).

3.  On the *Set package properties* page, complete the properties, and then click *Next*.


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

    Name/ Description


    
    </td>
    <td valign="top">

    Enter a clear name to identify the package.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Details


    
    </td>
    <td valign="top">

    Enter more detailed information about the contents of the package, including terms and conditions, if appropriate.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Category


    
    </td>
    <td valign="top">

    Select *My Content*.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Location


    
    </td>
    <td valign="top">

    By default, the package is exported to the *My Content* folder. To export to a subfolder, click *Browse* and select or create a new folder.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Sharing


    
    </td>
    <td valign="top">

    Select the sharing destinations for the export and their permissions on the content \(see [Adding Sharing Destinations](adding-sharing-destinations-562e996.md)\)


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Terms and Conditions


    
    </td>
    <td valign="top">

    Enable this switch to require users to accept terms and conditions before importing the content.


    
    </td>
    </tr>
    </table>
    
4.  On the *Review and export* page, review the overview of your package.

    If there are any problems, select the warning icon <span class="SAP-icons"></span>   to see how to fix them.

5.  Click *Export* to export your package.

    You can check the progress of your export in the *Notifications* list. You'll also receive a message when it is complete, and you can check the *Export Summary* to see the status of all the objects in the package.

    When the export completes successfully, the package becomes available in the *My Content* section of the *Content Network* for the tenants you added.

    You can edit the content, share it with other tenants, or delete it from the *Manage Packages* page \(see [Managing Exported Content](managing-exported-content-638bf6a.md)\).


