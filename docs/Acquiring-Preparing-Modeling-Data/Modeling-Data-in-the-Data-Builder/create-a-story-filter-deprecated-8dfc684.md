<!-- loio8dfc684eb4934177b169f11e3a72f9f5 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Story Filter \(Deprecated\)

Add a story filter to a view column to prompt users to filter on it when they consume your view in SAP Analytics Cloud.



## Context

> ### Note:  
> Story filters are deprecated and are not supported by entities with a *Semantic Usage* of *Fact*. You should instead, create a filter variable in your analytic model to trigger the display of the *Set Variables* dialog in SAP Analytics Cloud \(see [Add a Variable](add-a-variable-cdd8fa0.md)\).

Story filters that you add to your view will trigger the display of the *Set Variables* dialog when an SAP Analytics Cloud user creates a story with your view as a data source \(see [Setting Story Variables](https://help.sap.com/viewer/00f68c2e08b941f081002fd3691d86a7/release/en-US/305dcf7053634875a408a9d9832c8b8f.html)\).

> ### Note:  
> In order to add story filters, you must:
> 
> -   Set the *Semantic Usage* to *Analytical Dataset*.
> -   Enable the *Expose for Consumption* switch.



## Procedure

1.  Select the output node of your view to display its properties in the side panel and scroll down to the *Attributes* section.

2.  Hover over the column which you want to set the filter on, then click <span class="FPA-icons-V3"></span> \(Menu\)** \> *Add Story Filter* to open the filter properties in the side panel.

3.  Set the following properties as appropriate.


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
    
    Type
    
    </td>
    <td valign="top">
    
    Select the type of value that you want to allow or require the user to filter on. You can choose from:

    -   *Single* - The user should enter a single value to filter on. You can optionally specify a default value.
    -   *Range* -The user should enter *From* and *To* values to specify the range to filter on. You can optionally specify default values.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Mandatory
    
    </td>
    <td valign="top">
    
    Requires the user to enter a value.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Multiple Entries
    
    </td>
    <td valign="top">
    
    Allows the user to enter more than one value \(or range of values\) to filter on.
    
    </td>
    </tr>
    </table>
    
4.  Click the view name in the breadcrumbs at the top of the side panel to return to the view properties.

    The column displays a filter icon to show that it contains a story filter.

    > ### Note:  
    > To edit or remove the filter, hover over the column and click <span class="FPA-icons-V3"></span> \(Menu\)** \> *Edit Story Filter* or *Remove Story Filter*.


