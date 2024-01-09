<!-- loio5246328ec59045cb9c2aa693daee2557 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Data Access Control 

Users with the *DW Space Administrator* role \(or equivalent privileges\) can create data access controls in which criteria are defined as single values. Each user can only see the records that match any of the single values she is authorized for in the permissions entity.



## Context

Before creating your data access control, you must have prepared a permissions entity with the following columns:

-   User ID column - Containing user ids in the format required by your identity provider \(email addresses, logon names, or other identifiers\). This column must be selected as the *Identifier Column* in your data access control.

    > ### Note:  
    > If a user has no entries in the permissions entity, then they will not have access to any records in the protected view.

-   One or more columns containing filter criteria \(country or region names or ids, department names or ids, or any other criteria to control how your data is exposed to users\). These columns must be selected as *Criteria* columns in your data access control.



## Procedure

1.  In the side navigation area, click <span class="SAP-icons"></span> \(*Data Access Controls*\), select a space if necessary, and click *New Data Access Control* to open the editor.

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
    
3.  Select your permissions entity:

    1.  Click the *Permissions Entity* field to open the *Select Permissions Entity* dialog.

    2.  In the *Data Objects* list, select the table or view containing your user logins and columns with filter criteria.

    3.  In the *Available Columns* list, select one or more columns containing the criteria on which you want to control the display of data.

        These columns will be listed in the *Criteria* section. When you assign a data access control to a view, these columns must be mapped to columns in the view to enforce filtering by these criteria.

    4.  Click *OK* to confirm the selection.


4.  Click *Save* and then *Deploy* to deploy your data access control and make it available for use.

    For information about attaching a data access control to a view, see [Apply a Data Access Control](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/8f79fc80d6134a89a03837a205d340cd.html "You can apply one or more data access controls to a view to control the data that users will see based on the specified criteria.") :arrow_upper_right:.


