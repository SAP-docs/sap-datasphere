<!-- loio58fcee02df8044119777cf060000aca8 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Non-Cumulative Measure

With non-cumulative measures, you can model cases where measure values describe a state that is not changing every day.



## Context

For example the measure can describe items in stock in a warehouse, or the bank balance of an account. To achieve that, only the starting stock/opening balance is stored, and the changes to it.



## Procedure

1.  You are in the editor of your analytic model. You can create a new non-cumulative measure by clicking the background of the canvas and choosing <span class="FPA-icons-V3"></span> Add Measure in the properties panel. Choose *Non-Cumulative Measure*.

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
    
3.  Select the source measure. You can only use a fact source measure as source measure. It provides the basis for the calculation. 

4.  Define the non-cumulative properties. These properties apply to all the non-cumulative measures in the analytic model.


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
    
    Record Type Field
    
    </td>
    <td valign="top">
    
    Choose the column of the fact source that contains the record type of the measure value. The column needs to be of type *Integer* and may only contain the following values: `0` \(delta\), `1` \(reference point\), or `2` \(delta included in reference point\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Time Dimension
    
    </td>
    <td valign="top">
    
    Select a dimension source for the time dimension. As a precondition, the attribute in the fact source has to have data type *Date* and the attribute has to have an associated time dimension. This time dimension is used to calculate the exception aggregation for a given time interval. The data in the time dimension is used to fill up data for dates without a movement.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Earliest Reporting Start Date and Latest Reporting End Date \(optional\)
    
    </td>
    <td valign="top">
    
    You can set a time interval to improve performance of the calculation of the non-cumulative. Choose dates which are likely to be used by any imaginable, meaningful report for looking at the data.
    
    </td>
    </tr>
    </table>
    
    For more information, see [Non-Cumulative Measures](non-cumulative-measures-5899088.md).

5.  Define further properties of your non-cumulative measure:


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
    
    Exception Aggregation
    
    </td>
    <td valign="top">
    
    You can define an exception aggregation to define how the time dimension is to be aggregated.Allowed values are FIRST, LAST, MAX, MIN, SUM, AVERAGENULL, COUNTNULL, FIRST OF DIMENSION, AVERAGE OF DIMENSION, and LAST OF DIMENSION.
    
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
    <td valign="top" rowspan="2">
    
    Settings
    
    </td>
    <td valign="top">
    
    You can choose to set missing values to zero, so that Null values are converted to zero.Null values mainly appear for added dates before the first movement. This setting changes if those values will be filled up with null or 0. It will affect the calculation, e.g. these values will be taken into account for calculating the average.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Decide whether your measure should be an *Auxiliary Measure*.An auxiliary measure can be used for further calculation but it will be hidden in the story in SAP Analytics Cloud.
    
    </td>
    </tr>
    </table>
    

