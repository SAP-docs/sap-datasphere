<!-- loioaab52739c2ae48fa8a5c26fd0e9afd26 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Count Distinct Measure

A count distinct measure counts unique occurrences of attributes.



<a name="loioaab52739c2ae48fa8a5c26fd0e9afd26__context_fm2_v1q_kdc"/>

## Context

The count distinct measures considers only booked values.



## Procedure

1.  You are in the editor of your analytic model. You can create a new count distinct measure by clicking the background of the canvas and choosing <span class="FPA-icons-V3"></span> Add Measure in the properties panel. Choose *Count Distinct Measure*.

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
    
3.  Define the properties of your count distinct measure:


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
    
    Dimensions
    
    </td>
    <td valign="top">
    
    Select the dimensions for which this measure shall be applied.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Formatting
    
    </td>
    <td valign="top">
    
    You can change the format of a measure in an analytic model. You can change the scale \(Thousand, Million, Billion, Percent\) and the number of decimal places.

    > ### Example:  
    > A value of a measure with the formatting settings Scale: Unformatted and Decimal Places: 3 will be displayed as 200, 200.000$
    > 
    > A value of a measure with the formatting settings Scale: Million, Decimal Places: 2 will be displayed as 200.00Million$


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Settings
    
    </td>
    <td valign="top">
    
    Decide whether your measure should be an *Auxiliary Measure*.An auxiliary measure can be used for further calculation but it will be hidden in the story in SAP Analytics Cloud.
    
    </td>
    </tr>
    </table>
    

