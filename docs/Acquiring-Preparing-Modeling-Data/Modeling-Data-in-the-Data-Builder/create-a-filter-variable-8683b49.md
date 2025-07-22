<!-- loio8683b49e60c643f4947da11b5aa31585 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Filter Variable

Add a filter variable to your analytic model.



## Context

A filter variable refers to an attribute. When a story is opened, the variable dialog shows a filter for the attribute.



## Procedure

1.  You are in the editor of your analytic model. You can create a new filter variable by clicking the background of the canvas and choosing <span class="FPA-icons-V3"></span> Add Variable in the properties panel. Choose *Filter Variable*.

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
    
3.  Define the properties of your variable:


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
    
    Dimension
    
    </td>
    <td valign="top">
    
    Choose the dimension for which the variable should be created.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Variable filled by
    
    </td>
    <td valign="top">
    
    Choose how the variable should be filled:

    -   *Manual Input*

    -   *Derive Value*: Derived variables are hidden in the data preview or in an SAP Analytics Cloud story. See [Derived Variables](derived-variables-82f40f7.md).

    -   *Dynamic Default*: You get a derived value in the parameter dialog list when opening the analytic preview, and in the variable prompt for an SAP Analytics Cloud story. See [Dynamic Default](dynamic-default-2262a45.md).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Filter Type
    
    </td>
    <td valign="top">
    
    Choose the *Filter Type*.

    The filter can be

    -   a single value: The user should enter a single value to filter on. You can optionally specify a default value.

    -   multiple single values: Allows the user to enter more than one value \(or range of values\) to filter on. You can also define default values with multiple rows.

    -   an interval: Allows the user to enter an interval of values to filter on.

    -   a range of values: Allows the user to enter a range of values to filter on. You can also define several value ranges.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Mandatory
    
    </td>
    <td valign="top">
    
    You can select *Mandatory*, if the user has to enter a value in the prompt in the preview or the story in SAP Analytics Cloud.
    
    </td>
    </tr>
    </table>
    

