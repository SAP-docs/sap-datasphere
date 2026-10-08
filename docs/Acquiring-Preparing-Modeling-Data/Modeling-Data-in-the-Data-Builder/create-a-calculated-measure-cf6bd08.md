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
    
    The exception aggregation determines how a measure is aggregated with regard to one or more dimensions.[Aggregation and Exception Aggregation](aggregation-and-exception-aggregation-88ca394.md).
    
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
    </table>
    
    > ### Note:  
    > When you create a calculated measure based on a dimension then you should include the dimension on which the calculation is based on in the analytic model. Otherwise the calculated measure will show no data.


