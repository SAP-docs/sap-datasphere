<!-- loio501594bf2afb4e49ab5ce254e35e3504 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create an "Operator and Values" Data Access Control

Users with the *DW Space Administrator* role \(or equivalent privileges\) can create data access controls in which criteria are defined as operator and value pairs. Each user can only see the records that fulfill the operator-value pairs she is authorized for in the permissions entity, including support for complex `AND` and `OR` combinations.



## Context

Before creating your data access control, you must have prepared a permissions entity with the following columns:

-   Permission ID column - Which should be marked as a key.
-   User ID column - Containing user ids in the format required by your identity provider \(email addresses, logon names, or other identifiers\). If you are using SAML authentication, this column must contain values in the form defined as your *User Attribute* / `IdpUserID` \(see [Enabling a Custom SAML Identity Provider](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/9b26536159354aea9024a99cbbe60b4e.html "By default, SAP Cloud Identity Authentication is used by SAP Datasphere. SAP Datasphere also supports single sign-on (SSO), using your identity provider (IdP).") :arrow_upper_right:\).

    > ### Note:  
    > If a user has no entries in the permissions entity, then they will not have access to any records in the protected view.

-   Restriction Column - Each restriction per user must have a unique name, and one or more criteria can belong to each restriction. All criteria belonging to a restriction act together as an `AND` condition. If you have more than one restriction per user then all restrictions act together as an `OR` condition.
-   Criterion Column - The criteria name must contain only alphanumeric characters and underscores and appears in the *Mappings* area when a user applies the data access control to their view. It does not need to exactly match a column name, but should guide the user to the column to which it should be mapped.
-   Operator Column - The following operators are supported:
    -   `ALL` \(or `*`\) - Provides access to all records. No values required.
    -   `EQ` \(or `=`\) - Equal to *First Value*.
    -   `NE` \(or `<>` or `!=`\) - Not equal to *First Value*.
    -   `GT` \(or `>`\) - Greater than *First Value*.
    -   `GE` \(or `>=`\) - Greater than or equal to *First Value*.
    -   `LT` \(or `<`\) - Less than *First Value*.
    -   `LE` \(or `<=`\) - Less than or equal to *First Value*.
    -   `CP` \(or `LIKE`\) - Contains pattern *First Value*. Optionally *Second Value* can be set to an escape character.

        See [LIKE Predicate](https://help.sap.com/docs/HANA_SERVICE_CF/7c78579ce9b14a669c1f3295b0d8ca16/20fa17f375191014a4d8d8cbfddfe340.html) in the *SAP HANA Platform* documentation.

    -   `BT` \(or `BETWEEN`\) - Between *First Value* and *Second Value*.

-   First Value Column - This value acts as the first argument or lower bound of the operator.
-   Second Value Column - This value acts as the second argument or upper bound of the operator.

For example:


<table>
<tr>
<th valign="top">

Permission ID

</th>
<th valign="top">

User ID

</th>
<th valign="top">

Restriction

</th>
<th valign="top">

Criterion

</th>
<th valign="top">

Operator

</th>
<th valign="top">

First Value

</th>
<th valign="top">

Second Value

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

`Code`

</td>
<td valign="top">

`BT`

</td>
<td valign="top">

`CA`

</td>
<td valign="top">

`CZ`

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

`Type`

</td>
<td valign="top">

`EQ`

</td>
<td valign="top">

`1`

</td>
<td valign="top">

 

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

`Class`

</td>
<td valign="top">

`CP`

</td>
<td valign="top">

`ERR%`

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

`4`

</td>
<td valign="top">

`ann@acme.com`

</td>
<td valign="top">

`0`

</td>
<td valign="top">

`Admin`

</td>
<td valign="top">

`ALL`

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
</table>

Based on these three records:

-   `bob` will have access to records with a:
    -   \(restriction 0\) - `Code` between `CA` and `CZ`, and having a `Type` equal to `1`, or
    -   \(restriction 1\) - `Class` beginning with `ERR`.

-   `ann` \(restriction 0\) - will have access to all records thanks to the `ALL` operator.

    > ### Note:  
    > A criterion with an `ALL` operator can have any name and can be mapped to any column in a view.




## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Data Builder*\), select a space if necessary, and click *New Data Access Control* to open the editor.

2.  Complete the properties in the *General* section:


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
    
    Structure
    
    </td>
    <td valign="top">
    
    Select *Operator and Values*.
    
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
    
    Criterion Column
    
    </td>
    <td valign="top">
    
    Select the permissions entity column that contains the criteria names. 

    The criteria name must contain only alphanumeric characters and underscores and appears in the *Mappings* area when a user applies the data access control to their view. It does not need to exactly match a column name, but should guide the user to the column to which it should be mapped.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Operator Column
    
    </td>
    <td valign="top">
    
    Select the permissions entity column that contains operators.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    First Value Column
    
    </td>
    <td valign="top">
    
    Select the permissions entity column that contains the lower bound values to apply to the operators. 

    This value acts as the first argument or lower bound of the operator.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Second Value Column
    
    </td>
    <td valign="top">
    
    Select the permissions entity column that contains the upper bound values to apply to the operators. 

    This value acts as the second argument or upper bound of the operator.
    
    </td>
    </tr>
    </table>
    
4.  Use the Available Criteria table to control which criteria should be applied.

    All available criteria are listed in the table and are all selected to be applied by default. To remove a criterion, deselect it in the list.

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
    

