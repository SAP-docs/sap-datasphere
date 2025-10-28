<!-- loioa2d060ee364440dab656557ba42c20b4 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Reference Date Variable

Add a reference date variable to your analytic model.



## Context

When the analytic model has associations to a time-dependent dimension or text table, you can define a reference date variable. With a reference data variable, you can filter the data using a specific date. This allows SAP Analytics Cloud users to enter a date of their choice for their story and show dimension members based on that date. For more information on time-dependent dimensions, see [Enable Time-Dependency for a Dimension or Text Entity](enable-time-dependency-for-a-dimension-or-text-entity-11b2ff4.md).



## Procedure

1.  You are in the editor of your analytic model. You can create a new reference date variable by clicking the background of the canvas and choosing <span class="FPA-icons-V3"></span> Add Variable in the properties panel. Choose *Standard Variable*.

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
    > If you change the technical name after saving the model, this might affect existing stories or dependent analytic models.


    
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
    
    Sub Type
    
    </td>
    <td valign="top">
    
    Choose sub type *Reference Date*.
    
    </td>
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

    -   *Manual Input*

    -   *Derive Value*: Derived variables are hidden in the data preview or in an SAP Analytics Cloud story. See [Derived Variables](derived-variables-82f40f7.md).

    -   *Dynamic Default*: You get a derived value in the parameter dialog list when opening the analytic preview, and in the variable prompt for an SAP Analytics Cloud story. See [Dynamic Default](dynamic-default-2262a45.md).


    
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


    For more information, see [Derived Variables](derived-variables-82f40f7.md).
    
    </td>
    </tr>
    </table>
    

