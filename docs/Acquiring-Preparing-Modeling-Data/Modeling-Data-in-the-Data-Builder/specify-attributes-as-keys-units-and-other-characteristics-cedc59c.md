<!-- loiocedc59c994cf488bb6b43b105e72c4d3 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Specify Attributes as Keys, Units, and Other Characteristics

Attributes are all columns that are not identified as measures, and can contain identifiers, master data, and other data that is used in support of analytics. Attributes appear in tables and views with any *Semantic Usage* except *Relational Dataset*.

Attributes are used in:

-   Facts - to contain the keys of associated dimensions. For example, *Product ID* or *Store ID*.
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
> To set or remove an attribute as a primary key column in a view editor side panel, hover over it and click <span class="FPA-icons-V3"></span> \(Menu\)** \> *Set as Key* or *Remove as Key*.



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
-   *Text* - The column contains text. Attributes with this semantic type can be selected in the *Attributes* list *Text / Association*.
-   *Business Date...*, *Fiscal...*, *Calendar...*, *System Date...* - The column contains a date or fiscal or calendar period.
-   *Language* - The column contains a language code.
-   *Geolocation...* - The column contains geo data.

For more information, see [Specify Semantic Types for Measures and Attributes](specify-semantic-types-for-measures-and-attributes-f7272c0.md).

</td>
</tr>
<tr>
<td valign="top">

Text / Association

</td>
<td valign="top">

Specifies the purpose of the attribute when your entity is consumed by an analytic model. 

This property can contain:

-   An association pointing to a dimension \(see [Create an Association to a Dimension](create-an-association-to-define-a-semantic-relationship-between-entities-66c6998.md#loio66c6998af9974dac8f54a46515777560__section_dimension)\)
-   A text association pointing to a text entity \(see [Create an Association to a Text Entity](create-an-association-to-define-a-semantic-relationship-between-entities-66c6998.md#loio66c6998af9974dac8f54a46515777560__section_text)\)
-   An attribute with a semantic type of *Text*

It is automatically filled when you create an association or a text association and map the attribute as the source of the association. If you want to specify an attribute with a semantic type of *Text* to act as a label for the column, then you must manually select the attribute here.

> ### Note:  
> In cases where multiple associations and/or text associations are defined on a single attribute, you can manually choose which association \(or local text attribute\) should be used by the analytic model by making the appropriate selection here.



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
> To control the visibility of a column in a view editor side panel, hover over it and click <span class="FPA-icons-V3"></span> \(Menu\)** \> *Hide in Story* or *Show in Story*.



</td>
</tr>
</table>

In certain contexts, further actions are available in the *Attributes* list:

-   \[dimensions\] Create hierarchies as appropriate \(see [Add a Hierarchy to a Dimension](add-a-hierarchy-to-a-dimension-218b7e6.md)\).
-   \[graphical or SQL views\] Set any filters that you want to prompt users in SAP Analytics Cloud to specify a value for the attribute \(see [Create a Story Filter \(Deprecated\)](create-a-story-filter-deprecated-8dfc684.md)\).

