<!-- loio0c30366f83ed4cbaadbf266f7d281ed4 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Calculated Structure Member

With a calculated structure member, you can create calculations across all measures of an analytic model.



<a name="loio0c30366f83ed4cbaadbf266f7d281ed4__context_ngd_12c_rgc"/>

## Context

Calculated members can be calculations of existing restricted structure members or other calculated structure members. It is not possible to reference measures in the expression of a calculated structure member.



## Procedure

1.  You are in the editor of your analytic model. You can create a new structure member by clicking the background of the canvas and choosing <span class="FPA-icons-V3"></span> Add Structure Member in the properties panel. Choose *Calculated Structure Member*.

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
    
3.  Define the properties of your calculated structure member:

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
    
    Enter your expression in the formula editor.The expression field contains the formula to calculate the measure.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Settings
    
    </td>
    <td valign="top">
    
    Decide whether the structure member should be *Auxiliary*. An auxiliary structure member can be used for further calculation but it will be hidden in the story in SAP Analytics Cloud.
    
    </td>
    </tr>
    </table>
    

