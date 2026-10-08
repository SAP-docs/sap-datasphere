<!-- loio73068ac8e1934615b419d8c6c4095a9a -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Copy Spaces and their Contents

You can copy related spaces and the *Data Builder* objects they contain into new spaces. When selecting a space to copy you can also select some or all of its source spaces \(which share data to it\), and some or all of its consumer spaces \(to which it shares data\), in order to create a new stack of spaces sharing data between them, independently of the original spaces.



<a name="loio73068ac8e1934615b419d8c6c4095a9a__prereq_okr_vnr_mdc"/>

## Prerequisites

To copy a space and its contents, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`C-------`\) - To create spaces.
-   *User* \(`-R------`\) - To initialize the space for assigning users.
-   *Role* \(`-RU-----`\) - To add the new space to all scoped roles that the original space belongs to.
-   *Spaces* \(`-------M`\) - To update all spaces and space properties.
-   *Space Files* \(`-------M`\) - To view objects and data in all spaces.

The *DW Administrator* global role, for example, grants these privileges. For more information, see [Privileges and Permissions](../Managing-Users-and-Roles/privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](../Managing-Users-and-Roles/standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

> ### Note:  
> A space cannot be copied if it:
> 
> -   Is used as storage by an associated SAP Analytics Cloud tenant and any SAP Analytics Cloud objects are exposed for consumption \(see [Exposing Objects for Consumption in SAP Datasphere](https://help.sap.com/docs/SAP_ANALYTICS_CLOUD/fc70db459bea4083bb50c51c87ff9cf0/0bf207d4b49c4adeb70c36e023eecf9f.html)\)
> -   Contains *Business Builder* objects \(see [Modeling Data in the Business Builder (Deprecated)](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/3829d46c48a44f1e94915054bd76b7b9.html "Users with a modeler role can use the Business Builder editors to combine, refine, and enrich Data Builder objects and expose lightweight, tightly-focused perspectives for consumption by SAP Analytics Cloud and Microsoft Excel.") :arrow_upper_right:\).
> -   Contains *Marketplace* data products \(see [Installing Marketplace Data Products](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/92c35efd6a4945a1a78250539aee9a51.html "Use the catalog Data Products (Marketplace) collection to view data products for use in your modeling and other projects.") :arrow_upper_right:\).

> ### Note:  
> This feature is not supported for file spaces \(spaces with a storage type of *SAP HANA Data Lake Files*\).



## Context

This feature is available for all spaces, but can be particularly useful for copying the preparation and model spaces created when installing SAP Business Data Cloud intelligent content, if you want to extend them by adding custom fields. These spaces generally have the following structure:

-   The Ingestion space contains data product tables, which are shared to the Preparation space.
-   The Preparation space contains views that consume the data product tables, and these views are shared to the Model space.
-   The Model space contains analytic models that consume the views and are exposed for consumption in SAP Analytics Cloud.

Copying the model and preparation spaces together ensures that the copied model space correctly consumes views from the copied preparation space. The copied preparation space will continue to consume data product tables from the ingestion space, which cannot be copied.

When you copy the model and preparation spaces, the copied objects are removed from their protective namespaces and become editable \(see [Namespaces](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/7094f24d272c4ae4893b726095ab969e.html "Content managed by SAP and partners and delivered through SAP Business Data Cloud is protected by namespaces. Any object whose technical name is preceded by a namespace and a dot (for example, sap.s4h.Entity) cannot be edited.") :arrow_upper_right:\). You can then extend the copied content by adding custom fields or other extensions \(see [Extending Intelligent Content](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/3c158685865d4b408938a148e828e21f.html "The data products installed via SAP Business Data Cloud as part of intelligent content do not include any extensions defined in your source system. However, you can update the data products in SAP Datasphere to include any required custom fields, and adjust the delivered views and analytic models to consume them.") :arrow_upper_right:\).



## Copy Spaces

1.  In the side navigation area, select ![](../images/Space_Management_a868247.png) \(*Space Management*\), locate your space tile, and select *Edit* to open it.
2.  Click <span class="FPA-icons-V3"></span> \(More\) *Copy* to open the *Copy Spaces* wizard.
3.  In the *Selected Spaces* step, review the space selected to copy, including disk usage, connections, users, and models, and then click *Next Step*.
4.  In the *Consumer and Source Spaces* step, you can select to copy additional spaces:

    -   Consumer spaces - Any spaces to which the selected space shares data and any spaces that they, in turn, share data to.

        Select any consumer spaces that you want to copy.

    -   Source spaces - Any spaces that share data to the selected space and any spaces that share data to them.

        Select any source spaces that you want to copy.

        > ### Note:  
        > If you select one source that contains a namespace, then you must select all sources in that level that contain that namespace.


    > ### Note:  
    > These related spaces must be directly connected to the space you chose to copy. It is not possible to copy spaces that are isolated from others.

    Then click *Next Step*.

5.  In the *Spaces to Copy* step, review the list of the spaces to copy. By default, the copied space names and IDs have the word `Copy` appended to them. If needed, you can modify these names and IDs. Review the following properties:

    ****


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
    
    *Deploy Copied Objects*
    
    </td>
    <td valign="top">
    
    Select to have the contents of the spaces deployed to the new spaces.

    By default, the contents are copied to the new spaces, but are not deployed.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Copy Data Product Access Agreements*
    
    </td>
    <td valign="top">
    
    Select to copy the existing access agreements that granted access to the data product to the original spaces and have the new access agreements grant that same access to the copied spaces.

    If you do not select this option, in the next step you must make a new access request to obtain access to the data products in the copied spaces.
    
    </td>
    </tr>
    </table>
    
6.  If you did not select the *Copy Data Product Access Agreements* checkbox, in the *Access Requests* step request access to data products for your new spaces:

    ****


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
    
    *Purpose and Context*
    
    </td>
    <td valign="top">
    
    Add a comment to specify the context for using the data product. Optionally, you can add any relevant links and specify an end date for when you no longer need access to the data product. Leaving the end date empty means that access to the data product will never expire.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Data Product*
    
    </td>
    <td valign="top">
    
    Review the terms and conditions for all data products that you are requesting access to, and select the checkbox that you have read and acknowledge them.
    
    </td>
    </tr>
    </table>
    
7.  Click *Copy Spaces.* 

    You will receive separate notifications when each space is deployed, when objects are created and deployed in the new space, and when the copy is complete. 




## Results

The following actions are performed:

-   New spaces are configured exactly as the original spaces but have new *IDs* and *Space Names*.
-   The following objects are copied:

    -   All *Data Builder* objects.
    -   All connections \(credentials need to be re-entered unless the connection is a shared UCL connection\).

    > ### Note:  
    > Replication task schedules are not copied and must be recreated manually.

-   New access requests are automatically created and approved for any data products installed in the original spaces to allow them to be installed in the new spaces, see [Obtaining Access to Data Products](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/998fb5f447d04021baf497375261c9d1.html "You can request access for data products that you discover in the catalog.") :arrow_upper_right:.
-   Any objects installed in the original spaces are copied to the new spaces.
-   When copying intelligent content spaces, any objects protected by a namespace in the original space are removed from the namespace in the new space, so that a technical name such as `SAP.Sales_View` is converted to `SAP_Sales_View`.
-   The new spaces are added as scopes to all scoped roles that the original spaces belong to, but no users are added to the new spaces, by default. For information about adding users to spaces, see [Create a Scoped Role to Assign Privileges to Users in Spaces](../Managing-Users-and-Roles/create-a-scoped-role-to-assign-privileges-to-users-in-spaces-b5c4e0b.md).



## Troubleshooting

In case the copy cannot complete, you will receive a notification. Click on it to get a log of all the actions done by the copy.

To undo a partially failed copy, delete any spaces that have been copied in reverse order \(see the order in the log or in the intermediate notifications received\) and then try to copy again.

