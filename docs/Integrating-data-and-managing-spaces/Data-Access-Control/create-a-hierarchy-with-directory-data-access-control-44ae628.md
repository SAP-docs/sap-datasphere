<!-- loio44ae6289f96949f48781959f9d284578 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a "Hierarchy with Directory" Data Access Control

Users with the *DW Space Administrator* role \(or equivalent privileges\) can create data access controls in which criteria are defined as hierarchy values in a hierarchy with directory. Each user can only see the records that match the hierarchy values she is authorized for in the permissions entity, along with any of their descendants.



<a name="loio44ae6289f96949f48781959f9d284578__section_prerequisites"/>

## Prerequisites

To create data access controls, you must have a scoped role that grants you access to the space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Data Builder* \(`-R------`\) - To access the *Data Builder*.
-   *Data Warehouse Data Access Control* \(`CRUD----`\) - To create, read, update, and delete data access controls.

The *DW Space Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 



<a name="loio44ae6289f96949f48781959f9d284578__section_permissions_entity"/>

## Prepare a Permissions Entity and a Hierarchy with Directory Entity

Before creating your data access control, you must have identified the following entities:

-   An entity with a semantic usage of *Hierarchy with Directory* defining one or more hierarchies that are referenced in the permissions entity records \(see [Create a Hierarchy with Directory](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/36c39eee184c485a80ebce9d0fec49ec.html "Select a Semantic Usage of Hierarchy with Directory to indicate that your entity contains one or more parent-child hierarchies and has an association to a directory dimension containing a list of the hierarchies.") :arrow_upper_right:\).
-   A permissions entity containing the following columns:
    -   Permission ID column - Which should be marked as a key.
    -   User ID column - Containing user ids in the format required by your identity provider \(email addresses, logon names, or other identifiers\). If you are using SAML authentication, this column must contain values in the form defined as your *User Attribute* / `IdpUserID` \(see [Enabling a Custom SAML Identity Provider](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/9b26536159354aea9024a99cbbe60b4e.html "By default, SAP Cloud Identity Authentication is used by SAP Datasphere. SAP Datasphere also supports single sign-on (SSO), using your identity provider (IdP).") :arrow_upper_right:\). 

        > ### Note:  
        > If a user has no entries in the permissions entity, then they will not have access to any records in the protected view.

    -   Restriction Column - Each restriction per user must have a unique name, and one or more criteria can belong to each restriction. All criteria belonging to a restriction act together as an `AND` condition. If you have more than one restriction per user then all restrictions act together as an `OR` condition.
    -   Root Node Type Column - The node type values used here must be among those specified in the list of *Node Type Values* field in the hierarchy with directory.
    -   Target Node Type Column - The node type values used here must be among those specified in the list of *Node Type Values* in the hierarchy with directory, and each of these node types must be selected via the *Select Node Types* dialog so that all the necessary columns must appear in the list of selected criteria in the data access control.
    -   Hierarchy Identifiers Column - The key values used here must be among those specified in the foreign key columns used in the association from the hierarchy with directory to its directory entity.
    -   Root Values Column - The key values used here must be among those in the node type value columns defined for the given root node type in the hierarchy with directory and, in the case of compound keys, values for each key column must be provided. For example, if a `City` has `City`, `State`, and `Country` key columns then all three values must be provided.


In this example:


<table>
<tr>
<th valign="top">

Permission ID

</th>
<th valign="top">

User ID Column

</th>
<th valign="top">

Restriction Column

</th>
<th valign="top">

Target Node Type Column

</th>
<th valign="top">

Root Node Type Column

</th>
<th valign="top">

Root Values Column

</th>
<th valign="top">

Hierarchy Identifiers Column

</th>
</tr>
<tr>
<td valign="top">

`1`

</td>
<td valign="top">

`bob@acme.com`

</td>
<td valign="top">

`0`

</td>
<td valign="top">

`Employee`

</td>
<td valign="top">

`City`

</td>
<td valign="top">

`Paris\IDF\France`

</td>
<td valign="top">

`1\1`

</td>
</tr>
<tr>
<td valign="top">

`2`

</td>
<td valign="top">

`bob@acme.com`

</td>
<td valign="top">

`0`

</td>
<td valign="top">

`CostCenter`

</td>
<td valign="top">

`Organization`

</td>
<td valign="top">

`Sales`

</td>
<td valign="top">

`1\2`

</td>
</tr>
<tr>
<td valign="top">

`3`

</td>
<td valign="top">

`bob@acme.com`

</td>
<td valign="top">

`1`

</td>
<td valign="top">

`Employee`

</td>
<td valign="top">

`City`

</td>
<td valign="top">

`Los Angeles\CA\USA`

</td>
<td valign="top">

`1\1`

</td>
</tr>
</table>

> ### Note:  
> -   Compound keys are separated by a backslash \(`\`\) character.
> -   To improve readability, the root values, which would normally be numerical key values, are presented as text values.

Based on these three records `bob` will have access to records which meet the following conditions:

-   \(Restriction 0\):
    -   Any `Employee` in the `City` of `Paris\IDF\France` belonging to hierarchy `1\1` and
    -   Any `CostCenter` in the `Organization` `Sales` belonging to hierarchy `1\2`.

-   \(Restriction 1\):
    -   Any `Employee` in the `City` of `Los Angeles\CA\USA` belonging to hierarchy `1\1`.




<a name="loio44ae6289f96949f48781959f9d284578__section_create_dac"/>

## Create a "Hierarchy with Directory" Data Access Control

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Data Builder*\), select a space if necessary, and click *New Data Access Control* to open the editor. 
2.  Complete the properties in the *General Section*:


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
    
    Business Name
    
    </td>
    <td valign="top">
    
    Enter a descriptive name to help users identify the object. This name can be changed at any time.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Technical Name
    
    </td>
    <td valign="top">
    
    Displays the name used in scripts and code, synchronized by default with the *Business Name*. 

    To override the default technical name, enter a new one in the field. Technical names can contain only alphanumeric characters and underscores.

    > ### Note:  
    > Once the object is saved, the technical name can no longer be modified.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Package
    
    </td>
    <td valign="top">
    
    Select the package to which the object belongs. 

    Packages are used to group related objects in order to facilitate their transport between tenants.

    > ### Note:  
    > Once a package is selected, it cannot be changed here. Only a user with the DW Space Administrator role \(or equivalent privileges\) can modify a package assignment in the *Packages* editor.

    For more information, see [Creating Packages to Export](../Transporting-Content-Between-Tenants/creating-packages-to-export-24aba84.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Owner
    
    </td>
    <td valign="top">
    
    Enter the name of the person responsible for your data access control.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Status
    
    </td>
    <td valign="top">
    
    \[read-only\] Displays the deployment and error status of the object.

    For more information, see [Saving and Deploying Objects](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/7c0b560e2cb94eea86219d78d87f9623.html "When you save an object, it is stored in the SAP Datasphere repository, which contains the design-time definitions of all your objects. When you deploy an object, you are creating a run-time version for use in the SAP Datasphere database.") :arrow_upper_right:.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Deployed On
    
    </td>
    <td valign="top">
    
    \[read-only\] Displays the date and time of the last deployment.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Structure
    
    </td>
    <td valign="top">
    
    Select *Hierarchy with Directory*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Permissions Entity
    
    </td>
    <td valign="top">
    
    Select the table or view containing your user ids and criteria.

    The permissions entity must match the structure selected in the *Structure* field. Click the *Open in New Tab* button to the right of the field to open the entity in its own editor.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Identifier Column
    
    </td>
    <td valign="top">
    
    Select a column containing user ids in the format required by your identity provider \(email addresses, logon names, or other identifiers\).
    
    </td>
    </tr>
    </table>
    
3.  Complete the properties in the *Criteria* section:


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
    
    Restriction Column
    
    </td>
    <td valign="top">
    
    Select the permissions entity column that contains the restriction names. 

    Each restriction per user must have a unique name, and one or more criteria can belong to each restriction. All criteria belonging to a restriction act together as an `AND` condition. If you have more than one restriction per user then all restrictions act together as an `OR` condition.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Root Node Type Column
    
    </td>
    <td valign="top">
    
    Select the permissions entity column that contains the types of the nodes at or under which the target nodes are found in the hierarchy. 

    The node type values used here must be among those specified in the list of *Node Type Values* field in the hierarchy with directory.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Target Node Type Column
    
    </td>
    <td valign="top">
    
    Select the permissions entity column that contains the types of the nodes which contain the values that are used as the criteria mapped to the protected object.

    The node type values used here must be among those specified in the list of *Node Type Values* in the hierarchy with directory, and each of these node types must be selected via the *Select Node Types* dialog so that all the necessary columns must appear in the list of selected criteria in the data access control.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Hierarchy Identifiers Column
    
    </td>
    <td valign="top">
    
    Select the permissions entity column that contains the key or keys identifying the hierarchy in the hierarchy with directory. 

    The key values used here must be among those specified in the foreign key columns used in the association from the hierarchy with directory to its directory entity.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Root Values Column
    
    </td>
    <td valign="top">
    
    Select the permissions entity column that contains the key values for the root node types, at or under which we will list the values of target nodes, which will be used as the criteria mapped to the protected object. 

    The key values used here must be among those in the node type value columns defined for the given root node type in the hierarchy with directory and, in the case of compound keys, values for each key column must be provided. For example, if a `City` has `City`, `State`, and `Country` key columns then all three values must be provided.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Compound Key Values Separator
    
    </td>
    <td valign="top">
    
    Specify the symbol or string used to separate compound key values for identifying hierarchies and root node values. 

    If compound keys are not used in your hierarchy with directory, then this separator will be ignored.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Hierarchy Entity
    
    </td>
    <td valign="top">
    
    Select the entity with a semantic usage of *Hierarchy with Directory* that defines the parent-child hierarchy relationships between the records in the permissions entity. 

    ...
    
    </td>
    </tr>
    </table>
    
4.  Click *Select Node Types* to select the target node types whose key columns you want to add to the list of *Criteria*, all of which must be mapped to any protected objects.

    > ### Note:  
    > Each target node type that you select will add one criteria for each of its node type columns to the list.
    > 
    > For example, if a `City` node type has node type columns `City`, `Region`, and `Country` \(which are concatenated to give a compound key `City\Region\Country`\), then three entries will be able to the *Criteria* list.
    > 
    > If any node type column is used as a key column by multiple node types, then it will only be added once to the *Criteria* list.

5.  Click *Save* and then *Deploy* to deploy your data access control and make it available for use. 

    For information about attaching a data access control to a view, see [Apply a Data Access Control to a Graphical or SQL View](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/8f79fc80d6134a89a03837a205d340cd.html "You can apply one or more data access controls to a view to control the data that users will see based on the specified criteria.") :arrow_upper_right:.

    > ### Note:  
    > You can use the *View as User* tool in the *Data Viewer* panel to review the effects of the data access controls you apply by checking the records that another user will be allowed to see \(see [Viewing Object Data](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/b338e4aa7e7e494eb68c383720ebfd3a.html "You can, at any time, view the data contained in (or output by) your tables, views, and other Data Builder objects. When working in the graphical view editor, you can view the data output by each node in the diagram.") :arrow_upper_right:\).

6.  The tools in the editor toolbar help you work with your object throughout its lifecycle: 


    <table>
    <tr>
    <th valign="top">

    Tool
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Save\)
    
    </td>
    <td valign="top">
    
    Save your changes to the design-time repository. You can use *Save As* to create a copy of the object. 

    See [Saving and Deploying Objects](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/7c0b560e2cb94eea86219d78d87f9623.html "When you save an object, it is stored in the SAP Datasphere repository, which contains the design-time definitions of all your objects. When you deploy an object, you are creating a run-time version for use in the SAP Datasphere database.") :arrow_upper_right:.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="SAP-icons-V5"></span> \(Deploy\)
    
    </td>
    <td valign="top">
    
    Deploy your changes to make them available in the run-time environment.

    See [Saving and Deploying Objects](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/7c0b560e2cb94eea86219d78d87f9623.html "When you save an object, it is stored in the SAP Datasphere repository, which contains the design-time definitions of all your objects. When you deploy an object, you are creating a run-time version for use in the SAP Datasphere database.") :arrow_upper_right:.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Export\)
    
    </td>
    <td valign="top">
    
    Export the object to a CSN/JSON file. 

    See [Exporting Objects to a CSN/JSON File](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/391610123f1f4a12abb12cbf77a3294d.html "Export the definitions of your tables, views, and other objects to a CSN/JSON file, which can be imported into another space or tenant.") :arrow_upper_right:.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Impact and Lineage Analysis\)
    
    </td>
    <td valign="top">
    
    Open the *Impact and Lineage Analysis* graph for the object. 

    See [Impact and Lineage Analysis](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/9da4892cb0e4427ab80ad8d89e6676b8.html "The Impact and Lineage Analysis diagram helps you to understand the lineage (or data provenance) of a selected object or one or more of its columns, along with its impacts - the objects that depend on it and that will be impacted by any changes that are made to it.") :arrow_upper_right:.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Status
    
    </td>
    <td valign="top">
    
    \[read-only\] Displays the status of the object. 

    See [Saving and Deploying Objects](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/7c0b560e2cb94eea86219d78d87f9623.html "When you save an object, it is stored in the SAP Datasphere repository, which contains the design-time definitions of all your objects. When you deploy an object, you are creating a run-time version for use in the SAP Datasphere database.") :arrow_upper_right:.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Versions
    
    </td>
    <td valign="top">
    
    Open the *Version History* dialog for the object. 

    See [Reviewing and Restoring Object Versions](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/4f717cc0d90e4453a072b37f6b043593.html "Each time you deploy your object, a new version is created in the repository. You can review previous versions of an object at any time and choose to restore a previous version.") :arrow_upper_right:.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Details
    
    </td>
    <td valign="top">
    
    Toggles the display of the *Properties* panel.
    
    </td>
    </tr>
    </table>
    

