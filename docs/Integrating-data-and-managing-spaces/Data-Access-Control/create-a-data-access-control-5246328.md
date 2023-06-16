<!-- loio5246328ec59045cb9c2aa693daee2557 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Data Access Control

Space administrators can create data access controls to define criteria on which data can be displayed to users.



## Context

Each data access control uses a table or view that contains permission information.

This permissions entity must have at least two columns as follows:

-   A column containing user ids in the format required by your identity provider \(email addresses, logon names, or other identifiers\). This column must be selected as the *Identifier Column* in your data access control.
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
    
        Select a table or view containing user ids and one or more filter criteria. 

    For more information, see [Select a Table or View to Define Permissions](select-a-table-or-view-to-define-permissions-ffcae43.md).


    
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
    <tr>
    <td valign="top">
    
        Criteria


    
    </td>
    <td valign="top">
    
        Lists the columns containing filter criteria selected for use in your data access control. 

    > ### Note:  
    > When you apply your data access control to a view, you must map each column of the list to an appropriate column in the view.


    
    </td>
    </tr>
    </table>
    
3.  The following tools are available in the data access control editor toolbar:


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
    
        <span class="FPA-icons"></span> \(Save\)


    
    </td>
    <td valign="top">
    
        Save your changes to the design-time repository.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        <span class="SAP-icons"></span> \(Deploy\)


    
    </td>
    <td valign="top">
    
        Deploy your changes to make them available in the run-time environment. 

    For more information, see [Saving and Deploying Objects](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/7c0b560e2cb94eea86219d78d87f9623.html "When you save an object, it is stored in the SAP Datasphere repository, which contains the design-time definitions of all your objects. When you deploy an object, you are creating a run-time version for use in the SAP Datasphere database.") :arrow_upper_right:.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        <span class="FPA-icons"></span> \(Impact and Lineage Analysis\)


    
    </td>
    <td valign="top">
    
        Open the *Impact and Lineage Analysis* graph for the object. 

    For more information, see [Impact and Lineage Analysis](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/9da4892cb0e4427ab80ad8d89e6676b8.html "The Impact and Lineage Analysis diagram helps you to understand the lineage (or data provenance) of a selected object, along with its impacts - the objects that depend on it and that will be impacted by any changes that are made to it.") :arrow_upper_right:.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        Status


    
    </td>
    <td valign="top">
    
        \[read-only\] Displays the status of the object. 

    For more information, see [Saving and Deploying Objects](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/7c0b560e2cb94eea86219d78d87f9623.html "When you save an object, it is stored in the SAP Datasphere repository, which contains the design-time definitions of all your objects. When you deploy an object, you are creating a run-time version for use in the SAP Datasphere database.") :arrow_upper_right:.


    
    </td>
    </tr>
    </table>
    



## Results

Once your data access control is deployed, it is ready to be used:

-   For information about applying a data access control to a data layer view, see [Apply a Data Access Control](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/8f79fc80d6134a89a03837a205d340cd.html "You can apply one or more data access controls to a view to control the data that users will see based on the specified criteria.") :arrow_upper_right:.

-   For information about using a data access control to create authorization scenarios in the business layer, see [Authorization Scenario](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/46d8c42e1b1f421c9735a7cbc6fdba60.html "Authorization scenarios allow modelers to define which data is relevant to a user&apos;s context. They are made available through business entities and can be used in consumption models for specific use-cases.") :arrow_upper_right:.


