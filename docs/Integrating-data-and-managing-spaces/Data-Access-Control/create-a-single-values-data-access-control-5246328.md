<!-- loio5246328ec59045cb9c2aa693daee2557 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a "Single Values" Data Access Control

Users with the *DW Space Administrator* role \(or equivalent privileges\) can create data access controls in which criteria are defined as single values. Each user can only see the records that match any of the single values she is authorized for in the permissions entity.



<a name="loio5246328ec59045cb9c2aa693daee2557__section_prerequisites"/>

## Prerequisites

To create data access controls, you must have a scoped role that grants you access to the space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Data Builder* \(`-R------`\) - To access the *Data Builder*.
-   *Data Warehouse Data Access Control* \(`CRUD----`\) - To create, read, update, and delete data access controls.

The *DW Space Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 



<a name="loio5246328ec59045cb9c2aa693daee2557__section_permissions_entity"/>

## Prepare a Permissions Entity

Before creating your data access control, you must have prepared a permissions entity with the following columns:

-   User ID column - Containing user ids in the format required by your identity provider \(email addresses, logon names, or other identifiers\). If you are using SAML authentication, this column must contain values in the form defined as your *User Attribute* / `IdpUserID` \(see [Enabling a Custom SAML Identity Provider (Legacy Custom IdP)](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/9b26536159354aea9024a99cbbe60b4e.html "By default, SAP Cloud Identity is used by SAP Datasphere. SAP Datasphere also supports single sign-on (SSO), using your custom identity provider.") :arrow_upper_right:\). This column must be selected as the *Identifier Column* in your data access control.

    > ### Note:  
    > If a user has no entries in the permissions entity, then they will not have access to any records in the protected view.

-   One or more columns containing filter criteria \(country or region names or ids, department names or ids, or any other criteria to control how your data is exposed to users\). These columns must be selected as *Criteria* columns in your data access control.



<a name="loio5246328ec59045cb9c2aa693daee2557__section_create_dac"/>

## Create a "Single Values" Data Access Control

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Data Builder*\), select a space if necessary, and click *New Data Access Control* to open the editor.
2.  Complete the following properties:


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
    
    Select *Single Values*.
    
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
    
3.  Select your permissions entity:
    -   Click the *Permissions Entity* field to open the *Select Permissions Entity* dialog.
    -   In the *Data Objects* list, select the table or view containing your user logins and columns with filter criteria.
    -   In the *Available Columns* list, select one or more columns containing the criteria on which you want to control the display of data.

        These columns will be listed in the *Criteria* section. When you assign a data access control to a view, these columns must be mapped to columns in the view to enforce filtering by these criteria.

    -   Click *OK* to confirm the selection.

4.  Click *Save* and then *Deploy* to deploy your data access control and make it available for use. 

    For information about attaching a data access control to a view, see [Apply a Data Access Control to a Graphical or SQL View](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/8f79fc80d6134a89a03837a205d340cd.html "You can apply one or more data access controls to a view to control the data that users will see based on the specified criteria.") :arrow_upper_right:. 

    > ### Note:  
    > You can use the *View as User* tool in the *Data Viewer* panel to review the effects of the data access controls you apply by checking the records that another user will be allowed to see \(see [Viewing Object Data](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/b338e4aa7e7e494eb68c383720ebfd3a.html "You can, at any time, view the data contained in (or output by) your tables, views, and other Data Builder objects. When working in the graphical view editor, you can view the data output by each node in the diagram.") :arrow_upper_right:\).

5.  The tools in the editor toolbar help you work with your object throughout its lifecycle: 


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
    

