<!-- loio0afeeed6b56a40f5a02581032ec39420 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a "Hierarchy" Data Access Control

Users with the *DW Space Administrator* role \(or equivalent privileges\) can create data access controls in which criteria are defined as hierarchy values. Each user can only see the records that match the hierarchy values she is authorized for in the permissions entity, along with any of their descendents.



<a name="loio0afeeed6b56a40f5a02581032ec39420__context_hn2_r4h_fzb"/>

## Context

Before creating your data access control, you must have identified the following entities:

-   A permissions entity containing the following columns:
    -   User ID column - Containing user ids in the format required by your identity provider \(email addresses, logon names, or other identifiers\). 

        > ### Note:  
        > If a user has no entries in the permissions entity, then they will not have access to any records in the protected view.

    -   Criterion column - A column containing the criterion data. This criterion data is organized into a hierarchy via an external entity with a semantic usage of *Hierarchy*.

-   An entity with a semantic usage of *Hierarchy* containing parent-child relationships for the records in the permissions entity.

    > ### Note:  
    > Only external hierarchies with a single pair of parent-child columns are supported. Level-based hierarchies, dimensions with internal hierarchies, and entities with a semantic usage of *Hierarchy with Directory* cannot be used, and the data in your hierarchy must respect the following rules:
    > 
    > -   A single root node with a parent value of `null`
    > -   No nodes with multiple parents
    > -   No circular relationships


For example:

-   The `Geo Permissions` table is used as a permissions entity, and contains the following records:


    <table>
    <tr>
    <th valign="top">

    User ID
    
    </th>
    <th valign="top">

    Geo Criteria
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    `bob@acme.com`
    
    </td>
    <td valign="top">
    
    Europe
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `jim@acme.com`
    
    </td>
    <td valign="top">
    
    France
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `ann@acme.com`
    
    </td>
    <td valign="top">
    
    Paris
    
    </td>
    </tr>
    </table>
    
-   The `Geo Hierarchy` table has a semantic usage of *Hierarchy* and contains the following records:


    <table>
    <tr>
    <th valign="top">

    Child Geo Location
    
    </th>
    <th valign="top">

    Parent Geo Location
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    World
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Europe
    
    </td>
    <td valign="top">
    
    World
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    France
    
    </td>
    <td valign="top">
    
    Europe
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Paris
    
    </td>
    <td valign="top">
    
    France
    
    </td>
    </tr>
    </table>
    
-   The `Geo Hierarchy` data access control uses the `Geo Permissions` table as a permissions entity and, when it is applied to a view, ensures that the following users will only have access to records with the appropriate geo location values:
    -   `bob` - `Europe`, `France`, or `Paris`.
    -   `jim` - `France` or `Paris`.
    -   `ann` - `Paris`.




<a name="loio0afeeed6b56a40f5a02581032ec39420__steps_a2r_r4h_fzb"/>

## Procedure

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
    
    Structure
    
    </td>
    <td valign="top">
    
    Select *Hierarchy*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Permissions Entity
    
    </td>
    <td valign="top">
    
    Select the table or view containing your user ids and criteria.
    
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
    
    Criterion Column
    
    </td>
    <td valign="top">
    
    Select the column containing the authorized nodes from the permissions entity.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Hierarchy Entity
    
    </td>
    <td valign="top">
    
    Select the entity with a semantic usage of *Hierarchy* that defines the parent-child hierarchy relationships between the records in the permissions entity.
    
    </td>
    </tr>
    </table>
    
4.  Click *Save* and then *Deploy* to deploy your data access control and make it available for use.

    For information about attaching a data access control to a view, see [Apply a Data Access Control](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/8f79fc80d6134a89a03837a205d340cd.html "You can apply one or more data access controls to a view to control the data that users will see based on the specified criteria.") :arrow_upper_right:.


