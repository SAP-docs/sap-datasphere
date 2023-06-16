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

See [Creating a Local Table](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/2509fe4d86aa472b9858164b55b38077.html "Create a table to contain data by defining its column structure. Tables created in SAP Datasphere can be filled with data from a CSV file or via a data flow. You can also import tables from a connection or a CSN file.") :arrow_upper_right:



</td>
<td valign="top">

The definition of a local table contains the structure of the table only, and does not have dependencies on any other objects.



</td>
</tr>
<tr>
<td valign="top">

Remote Tables

See [Import Remote Tables](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/fd04efbac29c44fb8cfeaf2166b3d882.html "Import remote tables from a connection into your space directly from the Data Builder start page or the Repository Explorer.") :arrow_upper_right:



</td>
<td valign="top">

The definition of a remote table contains information about its connection. Before importing a remote table, you must create the relevant connection with an identical technical name in the receiving space.



</td>
</tr>
<tr>
<td valign="top">

Views

See [Creating a Graphical View](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/27efb479c4814252964d3fbc6ca2dfc3.html "Create a view to query sources in an intuitive graphical interface. You can drag and drop sources from the Source Browser, join them as appropriate, add other operators to remove or create columns and filter or aggregate data, and specify measures and other aspects of your output structure in the output node.") :arrow_upper_right: and [Creating an SQL View](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/81920e4d583f45fd8761c662d3c8abab.html "Create a view to query sources in a powerful SQL editor. You can choose between writing a standard SQL query using SELECT statements and operators such as JOIN and UNION, or use SQLScript to produce a table function. You can drag sources from the Source Browser, and specify measures and other aspects of your output structure in the side panel.") :arrow_upper_right:



</td>
<td valign="top">

The definition of a view contains the definitions of all its sources and any used data access controls. When you export a view, these objects are exported too.



</td>
</tr>
<tr>
<td valign="top">

Data Flows

See [Creating a Data Flow](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/e30fd1417e954577baae3246ea470c3f.html "Create a data flow to move and transform data in an intuitive graphical interface. You can drag and drop sources from the Source Browser, join them as appropriate, add other operators to remove or create columns, aggregate data, and do Python scripting, before writing the data to the target table.") :arrow_upper_right:



</td>
<td valign="top">

The definition of a data flow contains the definitions of all its sources and its target table. When you export a data flow, these objects are exported too.



</td>
</tr>
<tr>
<td valign="top">

Intelligent Lookups

See [Creating an Intelligent Lookup](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/8f29f801faea4d48816d0339777f9d16.html "Create an intelligent lookup to merge data from two entities even if there are problems joining them. Intelligent lookup offers a business-centric, interactive data harmonization environment for subject matter experts.") :arrow_upper_right:



</td>
<td valign="top">

The definition of an intelligent lookup contains the definitions of its input and lookup entities. When you export an intelligent lookup, these entities are exported too.



</td>
</tr>
<tr>
<td valign="top">

Analytic Models

See [Creating an Analytic Model](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/e5fbe9e2cb93484dab8b1963145e565f.html "Create an analytic model as a basis for consumption in SAP Analytics Cloud.") :arrow_upper_right:



</td>
<td valign="top">

The definition of an analytic model contains the definitions of its fact and dimension sources. When you export an analytic model, these entities are exported too.



</td>
</tr>
<tr>
<td valign="top">

E/R Models

See [Creating an Entity-Relationship Model](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/a91c042549fb497384e756d5f5c71fde.html "Create an E/R model to import, visualize, edit, and deploy multiple data entities (tables and views) together. You can use an E/R model to better understand a subset of the entities in your space, and to communicate this information to other stakeholders.") :arrow_upper_right:



</td>
<td valign="top">

The definition of an E/R model does not include the objects that it visualizes as dependencies. These visualized objects must be selected manually.



</td>
</tr>
<tr>
<td valign="top">

Data Access Controls

See [Securing Data with Data Access Controls](../Data-Access-Control/securing-data-with-data-access-controls-a032e51.md)



</td>
<td valign="top">

The definition of a data access control contains the definition of its permissions entity. When you export a data access control, the permissions entity is exported too.



</td>
</tr>
<tr>
<td valign="top">

Task Chains

See [Creating a Task Chain](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/d1afbc2b9ee84d44a00b0b777ac243e1.html "Group multiple tasks into a task chain and run them manually once, or periodically, through a schedule. You can create linear task chains in which one task is run after another. Or, you can create task chains in which individual tasks are run in parallel and successful continuation of the entire task chain run depends on whether ANY or ALL parallel tasks are completed successfully. In addition, when creating or editing a task chain, you can also set up email notification for deployed task chains to notify selected users of task chain completion.") :arrow_upper_right:



</td>
<td valign="top">

The definition of a task chain contains the definition of all the objects that it automates. When you export a task chain, these objects are exported too.



</td>
</tr>
<tr>
<td valign="top">

Business Entities / Business Entity Versions

See [Creating a Business Entity](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/c912cdc1537d4efbb24b08327ea68918.html "You use business entities to build your consumption model for analysis and reporting.") :arrow_upper_right:



</td>
<td valign="top">

The definition of a business entity contains all its versions \(which are also listed separately\), along with the definition of its source data entity and any authorization scenarios. When you export a business entity \(or one of its versions\), these objects are exported too.



</td>
</tr>
<tr>
<td valign="top">

Fact Models

See [Creating a Fact Model](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/5bbd14a328b549b2b53fce830ea25c15.html "Fact models are reusable models you can use to streamline the creation of other models within the same business context.") :arrow_upper_right:



</td>
<td valign="top">

The definition of a fact model contains all its versions \(which are also listed separately\), along with the definition of all its source fact models and business entities. When you export a fact model \(or one of its versions\), these objects are exported too.



</td>
</tr>
<tr>
<td valign="top">

Consumption Models

See [Creating a Consumption Model](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/337fa99de4a44700ba49e2214a1f3349.html "Consumption models are the basis to consume your data.") :arrow_upper_right:



</td>
<td valign="top">

The definition of a consumption model contains all its perspectives \(which are also listed separately\), along with the definition of all its source fact models and business entities. When you export a consumption model \(or one of its perspectives\), these objects are exported too.

You can deselect individual perspectives to exclude them from export. When overwriting a consumption model during an import, any perspectives excluded from the package will be deleted.



</td>
</tr>
<tr>
<td valign="top">

Authorization Scenarios

See [Creating an Authorization Scenario](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/167c05c673dc4715baba8d5d305abb1e.html "Authorization scenarios help you control data access for business entities leveraging data access controls.") :arrow_upper_right:



</td>
<td valign="top">

The definition of an authorization scenario contains the definition of its data access control. When you export an authorization scenario, the data access control is exported too.



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
    > If an object selected for export depends on one or more objects that have been shared from other spaces \(see [Sharing Tables and Views To Other Spaces](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/64b318f8afd74bb78467cf56eb44294f.html "Share a Data Builder table or view to another space to allow that space&apos;s members to use it as a source for their objects.") :arrow_upper_right:\), then you must be a member of each of those spaces in order to include all the necessary objects in your package.
    > 
    > If you are not a member of one or more sharing spaces, then you can still export your package \(no error will be displayed\), but it will fail to import correctly unless all the missing objects are already present in the target tenant.
    > 
    > You can review all the dependencies of your object by using the *Impact and Lineage Analysis* tool \(see [Impact and Lineage Analysis](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/9da4892cb0e4427ab80ad8d89e6676b8.html "The Impact and Lineage Analysis diagram helps you to understand the lineage (or data provenance) of a selected object, along with its impacts - the objects that depend on it and that will be impacted by any changes that are made to it.") :arrow_upper_right:\).

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


