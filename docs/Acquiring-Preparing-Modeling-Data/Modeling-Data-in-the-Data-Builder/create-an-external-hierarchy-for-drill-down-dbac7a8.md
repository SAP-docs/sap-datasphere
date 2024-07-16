<!-- loiodbac7a862b3744d8a71d268644aac389 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create an External Hierarchy for Drill-Down

Select a *Semantic Usage* of *Hierarchy* to indicate that your entity contains parent-child relationships for members in a dimension.



## Procedure

1.  Open the table or view containing the hierarchy information and set the following properties:


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
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Semantic Usage
    
    </td>
    <td valign="top">
    
    Choose *Hierarchy*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Parent Column / Child Column
    
    </td>
    <td valign="top">
    
    Select the parent and child columns that represent the hierarchy. The child column must be a key column and the parent and child columns must have the same data type.

    If your dimension has more than one key column, then you should click <span class="FPA-icons-V3"></span> \(Add\) to add an additional line for each key column.
    
    </td>
    </tr>
    </table>
    
2.  Set attributes as keys to indicate that the data they contain can uniquely identify records.

    > ### Note:  
    > You must set one or more key attributes for a *Hierarchy*:
    > 
    > -   Child attributes of the parent-child hierarchy structure

    To set an attribute as a key column, select the checkbox in the *Key* column or hover over the attribute in the side panel and click <span class="FPA-icons-V3"></span> \(Menu\)** \> *Set as Key*.

3.  Click <span class="FPA-icons-V3"></span> \(Save\)** \> *Save* to save your entity or click <span class="SAP-icons-V5"></span> \(Deploy\) to save and deploy it immediately.

    For more information, see [Saving and Deploying Objects](../saving-and-deploying-objects-7c0b560.md).


