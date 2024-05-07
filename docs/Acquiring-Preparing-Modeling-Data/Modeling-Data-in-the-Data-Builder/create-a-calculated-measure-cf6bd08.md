<!-- loiocf6bd0884d6b4b7b8ace669488941719 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Calculated Measure

A calculated measure references other measures and allows the combination of measures.



## Procedure

1.  You are in the editor of your analytic model. You can create a new calculated measure by clicking the background of the canvas and choosing <span class="FPA-icons-V3"></span> Add Measure in the properties panel. Choose *Calculated Measure*.

2.  Edit the following properties:


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Desription
    
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
    
3.  Define the properties of your calculated measure:


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

    > ### Example:  
    > To calculate the price, the expression could be `Amount / Quantity`.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Exception Aggregation
    
    </td>
    <td valign="top">
    
    The exception aggregation determines how a measure is aggregated with regard to one or more dimensions.A dimension is needed for exception aggregation in order to define the granularity with which the aggregation rule is applied. For more information, see [Aggregation and Exception Aggregation](aggregation-and-exception-aggregation-88ca394.md).
    
    </td>
    </tr>
    </table>
    

