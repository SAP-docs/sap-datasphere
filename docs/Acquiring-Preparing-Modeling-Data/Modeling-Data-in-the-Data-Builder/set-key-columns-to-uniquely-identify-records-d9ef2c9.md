<!-- loiod9ef2c91f6d647e584bad51999e441cd -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Set Key Columns to Uniquely Identify Records

Set one or more columns as keys to uniquely identify records in an entity. Key columns cannot contain null values and each value \(or set of combined values for multi-column compound keys\) must be unique.

This topic contains the following sections:

-   [Set Columns as Keys](set-key-columns-to-uniquely-identify-records-d9ef2c9.md#loiod9ef2c91f6d647e584bad51999e441cd__section_set_keys)
-   [Keys and Associations](set-key-columns-to-uniquely-identify-records-d9ef2c9.md#loiod9ef2c91f6d647e584bad51999e441cd__section_required_keys)
-   [Compound Keys and Representative Keys](set-key-columns-to-uniquely-identify-records-d9ef2c9.md#loiod9ef2c91f6d647e584bad51999e441cd__section_compound_keys)



<a name="loiod9ef2c91f6d647e584bad51999e441cd__section_set_keys"/>

## Set Columns as Keys

To set a column as a key, select the checkbox in its *Key* column. You can set one column as a key or, if necessary, set multiple columns to define a compound key \(see [Compound Keys and Representative Keys](set-key-columns-to-uniquely-identify-records-d9ef2c9.md#loiod9ef2c91f6d647e584bad51999e441cd__section_compound_keys)\).

Key columns cannot contain null values and each value \(or set of combined values for multi-column compound keys\) must be unique. To validate the data in your key columns, see "Key Validation Rules" in [Validating View Data](../validating-view-data-ed4063d.md). 



<a name="loiod9ef2c91f6d647e584bad51999e441cd__section_required_keys"/>

## Keys and Associations

It is important to set the necessary keys for your entity, based on its *Semantic Usage*, and to be aware of the requirements for mapping to these keys when creating associations:


<table>
<tr>
<th valign="top">

Semantic Usage

</th>
<th valign="top">

Keys Required

</th>
<th valign="top">

Mapping Keys When Creating Associations

</th>
</tr>
<tr>
<td valign="top">

*Fact*

See [Create a Fact to Contain Measurable Data](create-a-fact-to-contain-measurable-data-30089bd.md).

</td>
<td valign="top">

You may set one or more key attributes for a *Fact*, but none are required.

</td>
<td valign="top">

A *Fact* can point to a:

-   *Dimension* - One attribute in the \(source\) *Fact* must be mapped to each \(target\) *Dimension* key column so that all target key columns are mapped.
-   *Text Entity* - One attribute in the \(source\) *Fact* must be mapped to each \(target\) *Text Entity* identifier key column.



</td>
</tr>
<tr>
<td valign="top">

*Dimension*

See [Create a Dimension to Categorize Data](create-a-dimension-to-categorize-data-5aae0e9.md).

</td>
<td valign="top">

You must set one or more key attributes for a *Dimension*:

-   One or more identifier columns
-   Validity Start Date - if time-dependency is required \(see [Enable Time-Dependency for a Dimension or Text Entity](enable-time-dependency-for-a-dimension-or-text-entity-11b2ff4.md)\)



</td>
<td valign="top">

A *Dimension* can point to a:

-   *Dimension* - One attribute in the \(source\) *Dimension* must be mapped to each \(target\) *Dimension* key column so that all target key columns are mapped.
-   *Text Entity* - One attribute in the \(source\) *Dimension* must be mapped to each \(target\) *Text Entity* identifier key column.
-   *Hierarchy* - Each key attribute in the \(source\) *Dimension* must be mapped to a \(target\) *Hierarchy* child attribute key column.



</td>
</tr>
<tr>
<td valign="top">

*Text Entity*

See [Create a Text Entity for Attribute Translation](create-a-text-entity-for-attribute-translation-b25726d.md).

</td>
<td valign="top">

You must set two or more key attributes for a *Text Entity*:

-   One or more identifiers
-   Language Identifier
-   Validity Start Date - if time-dependency is required \(see [Enable Time-Dependency for a Dimension or Text Entity](enable-time-dependency-for-a-dimension-or-text-entity-11b2ff4.md)\)



</td>
<td valign="top">

A *Text Entity* must not point to other entities.

</td>
</tr>
<tr>
<td valign="top">

*Hierarchy*

See [Create an External Hierarchy for Drill-Down](create-an-external-hierarchy-for-drill-down-dbac7a8.md).

</td>
<td valign="top">

You must set one or more key attributes for a *Hierarchy*:

-   Child attributes of the parent-child hierarchy structure



</td>
<td valign="top">

A *Hierarchy* will generally not point to other entities.

</td>
</tr>
<tr>
<td valign="top">

*Hierarchy with Directory*

See [Create a Hierarchy with Directory](create-a-hierarchy-with-directory-36c39ee.md).

</td>
<td valign="top">

You must set exactly two key attributes for a *Hierarchy with Directory*:

-   Child attribute of the parent-child hierarchy structure
-   Hierarchy name attribute



</td>
<td valign="top">

A *Hierarchy with Directory* must point to:

-   A *Dimension* acting as its directory - The hierarchy name attribute in the \(source\) hierarchy entity must be mapped to the primary key column in the \(target\) dimension.
-   Any non-leaf *Dimension* providing nodes to the hierarchy - The appropriate node type values columns in the \(source\) hierarchy must be mapped to the key columns in the \(target\) *Dimension*.



</td>
</tr>
<tr>
<td valign="top">

*Relational Dataset*

</td>
<td valign="top">

You may set one or more key attributes for a *Relational Dataset*, but none are required.

</td>
<td valign="top">

A *Relational Dataset* can point to any other entity and should generally follow the rules for dimensions.

</td>
</tr>
</table>

See also [Create an Association to Define a Semantic Relationship Between Entities](create-an-association-to-define-a-semantic-relationship-between-entities-66c6998.md).



<a name="loiod9ef2c91f6d647e584bad51999e441cd__section_compound_keys"/>

## Compound Keys and Representative Keys

If you set more than one key column to uniquely identify records in a dimension, you should, in addition, specify a representative key, which is the column containing the most granular level of data. Specifying a representative key allows analytic tools to correctly consume the dimension.

For example, in the `Cost Center` table, both the `Controlling Area` and `Cost Center` column are set as key columns and the `Cost Center` column is set as the representative key:


<table>
<tr>
<th valign="top">

Controlling Area

</th>
<th valign="top">

Cost Center

</th>
<th valign="top">

Name

</th>
</tr>
<tr>
<td valign="top">

1

</td>
<td valign="top">

1000

</td>
<td valign="top">

Development

</td>
</tr>
<tr>
<td valign="top">

1

</td>
<td valign="top">

1001

</td>
<td valign="top">

Support

</td>
</tr>
<tr>
<td valign="top">

1

</td>
<td valign="top">

1002

</td>
<td valign="top">

Sales

</td>
</tr>
<tr>
<td valign="top">

1

</td>
<td valign="top">

1003

</td>
<td valign="top">

Training

</td>
</tr>
<tr>
<td valign="top">

2

</td>
<td valign="top">

2000

</td>
<td valign="top">

Development

</td>
</tr>
</table>

To define a compound key and set its representative key:

1.  Open your table or view and set its *Semantic Usage* to *Dimension*.
2.  Set two or more columns as keys.
3.  In the *Attributes* section toolbar, click <span class="SAP-icons-V5"></span> \(Edit Compound Key\) to open the *Compound Key* dialog.
4.  Select a key in the *Key Columns* section and click *Add* to identify it as the representative key and move it to the *Representative Key* section.
5.  \[optional\] Reorder keys in the *Key Column\(s\)* section by clicking <span class="FPA-icons-V3"></span> \(Move Up\) and <span class="SAP-icons-V5"></span> \(Move Down\).

    The *Compound Key* field shows the order of the key columns, with the representative key shown last and in bold.

6.  Click *Close* to complete the definition of the compound key.

> ### Note:  
> When you define a compound key for a dimension and want to provide translations of the dimension members, you must map all key columns to the text entity and identify the representative key column in the text entity as well. You can only provide translations for the representative key column. Other key columns in the compound key cannot be translated.

