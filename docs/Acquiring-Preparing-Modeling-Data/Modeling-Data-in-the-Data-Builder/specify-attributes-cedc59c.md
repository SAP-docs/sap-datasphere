<!-- loiocedc59c994cf488bb6b43b105e72c4d3 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Specify Attributes

Attributes are all columns that are not identified as measures, and can contain identifiers, master data, and other data that is used in support of analytics. Attributes appear in tables and views with any *Semantic Usage* except *Relational Dataset*.

Attributes are used in:

-   Analytical datasets - to contain the keys of associated dimensions. For example, *Product ID* or *Store ID*
-   Dimensions - to contain categories for analyzing data and the keys for identifying them. For example, *Country*, *Sales Organization*, *Customer*.
-   Text entities - to contain texts in multiple languages and the keys for identifying them.
-   Hierarchies - to define parent-child relationships between dimension members.

Attributes are displayed in the *Attributes* section of tables and views.

> ### Note:  
> In the graphical view and sql view editors, you can click the *Edit Columns* button in the *Attributes* list to open it in a dialog.

Attributes have the following properties:


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

Key

</td>
<td valign="top">

Select the checkbox to specify that the column is a primary key column. Key columns cannot be null. 

> ### Note:  
> To set or remove an attribute as a primary key column in a view editor side panel, hover over it and click <span class="FPA-icons"></span> \(Menu\)** \> *Set as Key* or *Remove as Key*.



</td>
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

Semantic Type

</td>
<td valign="top">

Select the appropriate semantic type to understand the value in the column. 

Choose from the following:

-   *None* - \[default\] No semantic meaning.
-   *Currency Code* - The column specifies the currency for one or more measures with the semantic type *Amount with Currency*. Attributes with this semantic type can be selected in the *Measures* list *Unit Column*.
-   *Unit of Measure* - The column specifies the unit for one or more measures with the semantic type *Quantity with Unit*. Attributes with this semantic type can be selected in the *Measures* list *Unit Column*.
-   *Text* - The column contains text. Attributes with this semantic type can be selected in the *Attributes* list *Label Column*.
-   *Business Date...*, *Fiscal...*, *Calendar...*, *System Date...* - The column contains a date or fiscal or calendar period.
-   *Language* - The column contains a language code.
-   *Geolocation...* - The column contains geo data.

For more information, see [Specify Semantic Types for Measures and Attributes](specify-semantic-types-for-measures-and-attributes-f7272c0.md).

</td>
</tr>
<tr>
<td valign="top">

Label Column

</td>
<td valign="top">

Select an attribute with a semantic type of *Text* to act as the label for the column. 

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

\[deprecated\] Deselect the checkbox to hide the column from users in SAP Analytics Cloud. 

You can now control the visibility of columns in SAP Analytics Cloud by choosing to include or exclude them in your analytic model \(see [Creating an Analytic Model](creating-an-analytic-model-e5fbe9e.md)\).

> ### Note:  
> To control the visibility of a column in a view editor side panel, hover over it and click <span class="FPA-icons"></span> \(Menu\)** \> *Hide in Story* or *Show in Story*.



</td>
</tr>
</table>

In certain contexts, further actions are available in the *Attributes* list:

-   \[dimensions\] Create hierarchies as appropriate \(see [Add a Hierarchy to a Dimension](add-a-hierarchy-to-a-dimension-218b7e6.md)\).
-   \[graphical or SQL views\] Set any filters that you want to prompt users in SAP Analytics Cloud to specify a value for the attribute \(see [Create a Story Filter \(Deprecated\)](create-a-story-filter-deprecated-8dfc684.md)\).

