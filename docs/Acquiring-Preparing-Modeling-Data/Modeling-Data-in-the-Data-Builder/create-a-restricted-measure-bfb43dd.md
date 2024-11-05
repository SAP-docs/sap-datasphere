<!-- loiobfb43ddc98bc4162bc4196faf3e5d8c6 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Restricted Measure

With a restricted measure, you can restrict available dimensions.



## Procedure

1.  You are in the editor of your analytic model. You can create a new restricted measure by clicking the background of the canvas and choosing <span class="FPA-icons-V3"></span> Add Measure in the properties panel. Choose *Restricted Measure*.

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
    
3.  Define the properties of your restricted measure:


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
    
    Source Measure
    
    </td>
    <td valign="top">
    
    Select the source measure.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Aggregation Type
    
    </td>
    <td valign="top">
    
    When the source measure is a fact source measure the standard aggregation can be overridden by changing the *Aggregation Type*.
    
    </td>
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
    
    Exception Aggregation
    
    </td>
    <td valign="top">
    
    The exception aggregation determines how a measure aggregated with regard to one or more dimensions.A dimension is needed for exception aggregation in order to define the granularity with which the aggregation rule is applied. For more information, see [Aggregation and Exception Aggregation](aggregation-and-exception-aggregation-88ca394.md).Exception aggregation is only supported for restricted measures if the source measure is a fact source measure. You can use the exception aggregation to calculate the stock for a given time. You can also define no restrictions for the restricted measure, and just use it for the exception aggregation.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Constant Selection
    
    </td>
    <td valign="top">
    
    You can choose to set constant selection for all dimensions or just for selected dimensions. A measure with constant selection will not be impacted by filters or drill-downs on the constant dimensions.Enabling constant selection is useful for comparing a single value with several different values. For example, you could create a restricted measure for sales in 2022, and then compare sales in 2022 with sales for all other years in the same table. See also the blog post [Restricted Measures with Constant Selection in SAP Analytics Cloud](https://blogs.sap.com/2021/02/02/feature-highlight-restricted-measures-with-constant-selection-in-sap-analytics-cloud/) \(published February 2, 2021\) for examples.
    
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
    

