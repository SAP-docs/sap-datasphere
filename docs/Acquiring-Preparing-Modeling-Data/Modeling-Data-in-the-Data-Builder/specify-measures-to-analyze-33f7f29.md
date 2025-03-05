<!-- loio33f7f291538a44a293a89f6f1cf1fa81 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Specify Measures to Analyze

Measures appear in tables and views with a *Semantic Usage* of *Fact* and are columns containing numerical values that you want to analyze. Each *Fact* must contain at least one measure.

Typical measures include:

-   Gross Sales
-   Quantity
-   Price
-   Hours
-   Distance

Measures are displayed in the *Measures* section of tables and views.

> ### Note:  
> In the graphical view and SQL view editors, you can click the *Edit Columns* button in the *Measures* list to open it in a dialog.

By default, all columns in a fact are identified as attributes, and you must convert one or more into measures:

-   In the graphical or SQL view editor:
    -   To convert a numerical attribute into a measure, hover over it and click <span class="FPA-icons-V3"></span> \(Menu\)** \> *Change to Measure*, or drag the attribute token and drop it into the *Measures* list.

    -   To convert a measure into an attribute, hover over it and click <span class="FPA-icons-V3"></span> \(Menu\)** \> *Change to Attribute*, or drag the measure token and drop it into the *Attributes* list.


-   In the local or remote table editor:
    -   To convert an attribute into a measure, select it in the *Attributes* list and click *Change to Measure*.

    -   To convert a measure into an attribute, select it in the *Measures* list and click *Change to Attribute*.



Measures have the following properties:


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
<tr>
<td valign="top">

Data Type

</td>
<td valign="top">

Select the type of data that the column will contain. 

For a list of available data types and their supported data type conversions, see [Column Data Types](../Acquiring-and-Preparing-Data-in-the-Data-Builder/column-data-types-7b1dc6e.md).

</td>
</tr>
<tr>
<td valign="top">

Aggregation

</td>
<td valign="top">

Select the default aggregation type for the column. 

Choose from the following:

-   *SUM* - \[default\] Calculate the total value for all rows.
-   *COUNT* - Calculate the number of distinct values.
-   *MIN* - Calculate the minimum value.
-   *MAX* - Calculate the maximum value.
-   *NONE* - Perform no aggregation.

> ### Note:  
> To modify the default aggregation type of a column in a view editor side panel, hover over it and click <span class="FPA-icons-V3"></span> \(Menu\)** \> *Change Aggregation* \> **<Aggregation\>**.



</td>
</tr>
<tr>
<td valign="top">

Semantic Type

</td>
<td valign="top">

Select the appropriate semantic type to understand the value in the column. 

Choose from the following:

-   *None* - \[default\] No semantic meaning.
-   *Amount with Currency* - The column contains monetary values. To complete the definition, select an attribute with the semantic type *Currency Code* in the *Unit Column*.
-   *Quantity with Unit* - The column contains a physical values. To complete the definition, select an attribute with the semantic type *Unit of Measure* in the *Unit Column*.



</td>
</tr>
<tr>
<td valign="top">

Unit Column

</td>
<td valign="top">

Select an attribute with a semantic type of *Currency Code* or *Unit of Measure* to complete the semantic definition of the column. 

</td>
</tr>
<tr>
<td valign="top">

Default Value

</td>
<td valign="top">

Enter an appropriate default value for the column. 

> ### Note:  
> This property is only displayed in the table editor.



</td>
</tr>
<tr>
<td valign="top">

Not Null

</td>
<td valign="top">

Select this option to indicate that the column must contain a value. 

> ### Note:  
> This property is only displayed in the table editor.



</td>
</tr>
<tr>
<td valign="top">

Show

</td>
<td valign="top">

Deselect the checkbox to hide the column from users working in analytic models. 

Users working in analytic models can, for each measure and attribute, choose whether to include or exclude it in the data exposed to SAP Analytics Cloud \(see [Creating an Analytic Model](creating-an-analytic-model-e5fbe9e.md)\). Dimension attributes that are made available to the analytic model user and excluded by her to optimize the model can still be displayed in SAP Analytics Cloud tables as non-navigable properties \(see [Exclude Non-Navigable Dimension Attributes](exclude-non-navigable-dimension-attributes-4d96a8a.md)\). 

> ### Note:  
> To control the visibility of a column in a view editor side panel, hover over it and click <span class="FPA-icons-V3"></span> \(Menu\)** \> *Hide in Story* or *Show in Story*.



</td>
</tr>
</table>

