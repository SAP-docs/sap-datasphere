<!-- loio1896990bd2124b9090f1bfd0a607bb92 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Restricted Structure Member

With a restricted structure member, you can restrict available dimensions.



<a name="loio1896990bd2124b9090f1bfd0a607bb92__context_wrf_r2c_rgc"/>

## Context

This restriction will thus be applied to all measures in the resulting query when the structure member is part of the drill down.



## Procedure

1.  You are in the editor of your analytic model. You can create a new structure by clicking the background of the canvas and choosing <span class="FPA-icons-V3"></span> Add Structure Member in the properties panel. Choose *Restricted Structure Member*.

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
    
3.  Define the properties of your restricted structure member:

    > ### Note:  
    > Structure members do not reference a real measure, as it applies to all measures automatically.

    > ### Note:  
    > When you create a structure member, an empty restriction member *Measure\_Value* is created, which is a restricted structure member without any restriction applied. This can automatically be used in formulas, and is also available for the drill down. It represents the unrestricted measure value of the given cell.


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
    
    Expression
    
    </td>
    <td valign="top">
    
    Enter your expression in the formula editor. An atomic expression usually has the format`<dimension> <operator> <value> (e.g. Country = 'Germany').`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Constant Selection
    
    </td>
    <td valign="top">
    
    You can choose to set constant selection for all dimensions or just for selected dimensions. A structure member with constant selection will not be impacted by filters or drill-downs on the constant dimensions.Enabling constant selection is useful for comparing a single value with several different values.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Settings
    
    </td>
    <td valign="top">
    
    Decide whether the structure member should be *Auxiliary*.An auxiliary structure member can be used for further calculation but it will be hidden in the story in SAP Analytics Cloud.
    
    </td>
    </tr>
    </table>
    

