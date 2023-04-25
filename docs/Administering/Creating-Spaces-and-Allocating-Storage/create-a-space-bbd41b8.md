<!-- loiobbd41b82ad4d4d9ba91341545f0b37e7 -->

# Create a Space

Create a space, allocate storage, and assign one or more members to allow them to start acquiring and preparing data.



<a name="loiobbd41b82ad4d4d9ba91341545f0b37e7__context_owz_zmt_vrb"/>

## Context

> ### Note:  
> Only administrators can create spaces, allocate storage, and set the space priority and statement limits. The remaining space properties can be managed by the space administrators that the administrator assigns as members to the space.



## Procedure

1.  In the side navigation area, click ![](../images/Space_Management_a868247.png) \(*Space Management*\), and click *Create*.

2.  In the *Create Space* dialog, enter the following properties, and then click *Create*:


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

    Space Name


    
    </td>
    <td valign="top">

    Enter the business name of the space. Can contain a maximum of 30 characters, and can contain spaces and special characters.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Space ID


    
    </td>
    <td valign="top">

    Enter the technical name of the space. Can contain a maximum of 20 uppercase letters or numbers and must not contain spaces or special characters other than `_` \(underscore\). Unless advised to do so, must not contain prefix \_SYS and should not contain prefixes: DWC\_, SAP\_ \(See [Rules for Technical Names](rules-for-technical-names-982f9a3.md)\).


    
    </td>
    </tr>
    </table>
    
    The space is created and its property sheet opens.

3.  In the *General Settings* section, review the following properties:


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

    Space ID


    
    </td>
    <td valign="top">

    Enter the technical name of the space. Can contain a maximum of 20 uppercase letters or numbers and must not contain spaces or special characters other than `_` \(underscore\). Unless advised to do so, must not contain prefix \_SYS and should not contain prefixes: DWC\_, SAP\_ \(See [Rules for Technical Names](rules-for-technical-names-982f9a3.md)\).


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Space Name


    
    </td>
    <td valign="top">

    Enter the business name of the space. Can contain a maximum of 30 characters, and can contain spaces and special characters.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Space Status


    
    </td>
    <td valign="top">

    \[read-only\] Displays the status of the space. Newly-created spaces are always active.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Space Type


    
    </td>
    <td valign="top">

    \[read-only\] Displays the type of the space. You can only create spaces of type SAP Datasphere.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Created By


    
    </td>
    <td valign="top">

    \[read-only\] Displays the user that created the space.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Created On


    
    </td>
    <td valign="top">

    \[read-only\] Displays the date and time when the space was created.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Deployment Status


    
    </td>
    <td valign="top">

    \[read-only\] Displays the deployment status of the space. Newly-created spaces are deployed, but when you make changes, you need to save and re-deploy them before they are available to space members.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Deployed On


    
    </td>
    <td valign="top">

    \[read-only\] Displays the date and time when the space was last deployed.


    
    </td>
    </tr>
    </table>
    
4.  \[optional\] Use the *Storage Assignment* properties to allocate disk and in-memory storage to the space and to choose whether it will have access to the SAP HANA data lake.

    For more information, see [Allocate Storage to a Space](allocate-storage-to-a-space-f414c3d.md).

5.  \[optional\] Use the properties in the *Workload Management* section to prioritize between spaces for resource consumption and set limits to the amount of memory and threads that a space can consume.

    For more information, see [Set a Priority and Statement Limits for a Space](set-a-priority-and-statement-limits-for-a-space-d66ac1e.md).

6.  Use the list in the *Members* section to add users as members of the space.

    You must assign at least one member in order to use the space:

    -   **DW Space Administrator** - Can manage all aspects of spaces of which they are a member \(except the *Storage Assignment* and *Workload Management* properties\) and can create data access controls and use the *Content Network*.
    -   **DW Integrator** - Can create and edit connections and database users, and associate HDI containers in spaces of which they are a member.
    -   **DW Modeler** - Can create and edit objects in the *Data Builder* and *Business Builder* and view data in all objects in spaces of which they are a member.
    -   **DW Viewer** - Can view objects in spaces of which they are a member and view data output by views that are exposed for consumption in these spaces.

    For more information, see [Assign Members to Your Space](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/9d59fe511ae644d98384897443054c16.html "As a Space Administrator, you can assign users as members of your space.") :arrow_upper_right:.

7.  \[optional\] Use the remaining sections to further configure the space.

    -   *Data Access*/*Data Consumption*: Modify the following property, if appropriate:


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

        Expose for Consumption by Default


        
        </td>
        <td valign="top">

        Choose the default setting for the *Expose for Consumption* property for views created in this space.


        
        </td>
        </tr>
        </table>
        
    -   *Data Access*/*Database Users* - Use the list in the *Database Users* section to create users who can connect external tools and read from and write to the space. See [Create a Database User](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/798e3fd6707940c3bd2219b2d1ebaac2.html "Users with the DW Space Administrator or DW Integrator role (space administrators and integrators) can create database users, granting them privileges to read from and/or write to an Open SQL schema with restricted access to the space schema.") :arrow_upper_right:.
    -   *Data Access*/*HDI Containers* - Use the list in the *HDI Containers* section to associate HDI containers to the space. See [Prepare Your Project for Exchanging Data with Your Space](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/a94e1637db484a5c8ec2da83cfa75156.html "To allow your SAP Datasphere space to read from and, if appropriate, write to the HDI container, you must configure your project to build on your SAP Datasphere tenant and define the appropriate roles.") :arrow_upper_right:.
    -   *Connections* - Follow the link in the *Connections* section to create connections to source systems in the space. See [Create a Connection](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/c2165842082c43fc85bad9f0c97572bb.html "Create a connection to allow the members of the space to use the connected source for data modeling and data access in SAP Datasphere.") :arrow_upper_right:.
    -   *Time Data*/*Time Tables and Dimensions* - Click the button in the *Time Tables and Dimensions* section to generate time data in the space. See [Create Time Data and Dimensions](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/c5cfce4d22b04650b2fd6078762cdeb9.html "Create a time table and dimension views in your space to provide standardized time data for your analyses. The time table contains a record for each day in the specified period (by default from 1900 to 2050), and the dimension views allow you to work with this date data at a granularity of day, week, month, quarter, and year, and to drill down and up in hierarchies.") :arrow_upper_right:.
    -   *Auditing*/*Space Audit Settings* - Use the properties in the *Space Audit Settings* section to enable audit logging for the space. See [Enable or Disable Audit Logging](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/266553976e1c4db9aaa28a75e2308b77.html "You can enable audit logs for your space so that read and change actions (policies) are recorded. Administrators can then analyze who did what and when in the database.") :arrow_upper_right:.

8.  Either click *Save* to save your space \(and click *Deploy* later\), or directly click *Deploy* to save and deploy your space to the database in one click.


