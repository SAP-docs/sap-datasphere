<!-- loio8a2978ed34de4d0d975ebdd1bbf96ac4 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Standard Variable

Add a standard variable to your analytic model.



## Context

A standard variable is used in a fact source to map it to input parameters of the fact.



## Procedure

1.  You are in the editor of your analytic model. You can create a new standard variable by clicking the background of the canvas and choosing <span class="FPA-icons-V3"></span> Add Variable in the properties panel. Choose *Standard Variable*.

2.  Edit the following properties:


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
    </table>
    
3.  Define the properties of your standard variable:


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
    
    Data Type
    
    </td>
    <td valign="top">
    
    Select the data type.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Variable filled by
    
    </td>
    <td valign="top">
    
    Choose how the variable should be filled:

    -   Manual Input

    -   Derive Value. Derived variables are hidden in the data preview or in an SAP Analytics Cloud story.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Properties for derive value
    
    </td>
    <td valign="top">
    
    If you want to derive the value, you need to

    1.  Define a lookup entity \(a view\).

    2.  Select the column from which the value is to be derived.

    3.  Map the parameter of the lookup entity. If it has no input parameter, you can set a constant value or create a variable.



    
    </td>
    </tr>
    </table>
    

