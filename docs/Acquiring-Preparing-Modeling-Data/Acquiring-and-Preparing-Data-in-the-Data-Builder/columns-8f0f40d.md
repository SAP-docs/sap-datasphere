<!-- loio8f0f40df2ed34035b8b5837897205ee6 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Columns

Columns appear in tables and views with a *Semantic Usage* of *Relational Dataset*.

Columns are displayed in the *Columns* section of tables and views.

> ### Note:  
> In the graphical view and sql view editors, you can click the *Edit Columns* button in the *Columns* list to open it in a dialog.

Columns have the following properties:


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

You can change the data type of a column. For more information, see [Modifying Objects That Have Dependent Objects](../Creating-Finding-Sharing-Objects/modifying-objects-that-have-dependent-objects-f315863.md) 

For a list of available data types and their supported data type conversions, see [Column Data Types](column-data-types-7b1dc6e.md).

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

Change Type

</td>
<td valign="top">

This column will track the type of last change made to a record. When a record is inserted or updated corresponding change types are used \(for example "I" or "U"\). When an existing record is deleted other specific change types are used \(for example "D"\). Note that deleting a record will not physically delete it, so that the changes can be propagated to the different objects that consume it in delta mode. It is however filtered out when accessing the Local Table \(using the Active Records Table\). Also, note that the change types provided by the different SAP Datasphere apps vary and may depend on the actual source that is connected. The handling of the different change types is implemented internally by SAP Datasphere apps that consume the Delta Capture Table with no need for consideration in modeling. For more information on records deletion, see [Load or Delete Local Table Data](load-or-delete-local-table-data-870401f.md) .

</td>
</tr>
<tr>
<td valign="top">

Change Date

</td>
<td valign="top">

The column will track the last date and time of the last change to an individual record. Current UTC timestamp. 

</td>
</tr>
</table>

