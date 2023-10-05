<!-- loiod9ef2c91f6d647e584bad51999e441cd -->

# Set Key Columns to Uniquely Identify Records

Set one or more columns as keys to uniquely identify records in an entity. Each value in a key column \(or each combination of values, when two or more key columns are set\) must be unique.

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

See [Creating a Fact](creating-a-fact-30089bd.md).



</td>
<td valign="top">

You may set one or more key attributes for a *Fact*, but none are required.



</td>
<td valign="top">

A *Fact* can point to a:

-   *Dimension* - One attribute in the \(source\) *Fact* must be mapped to each \(target\) *Dimension* key column so that all target key columns are mapped.
-   *Text Entity* - An attribute in the \(source\) *Fact* must be mapped to the \(target\) *Text Entity* identifier key column.



</td>
</tr>
<tr>
<td valign="top">

*Dimension*

See [Creating a Dimension](creating-a-dimension-5aae0e9.md).



</td>
<td valign="top">

You must set one or more key attributes for a *Dimension*:

-   One or more identifier columns
-   Validity Start Date - if time-dependency is required \(see [Enable Time-Dependency for a Dimension or Text Entity](enable-time-dependency-for-a-dimension-or-text-entity-11b2ff4.md)\)



</td>
<td valign="top">

A *Dimension* can point to a:

-   *Dimension* - One attribute in the \(source\) *Dimension* must be mapped to each \(target\) *Dimension* key column so that all target key columns are mapped.
-   *Text Entity* - An attribute in the \(source\) *Dimension* must be mapped to the \(target\) *Text Entity* identifier key column.
-   *Hierarchy* - The key attribute in the \(source\) *Dimension* must be mapped to the \(target\) *Hierarchy* child attribute key column.



</td>
</tr>
<tr>
<td valign="top">

*Text Entity*

See [Create a Text Entity for Attribute Translation](create-a-text-entity-for-attribute-translation-b25726d.md).



</td>
<td valign="top">

You must set two or three key attributes for a *Text Entity*:

-   Identifier
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

See [Creating an External Hierarchy](creating-an-external-hierarchy-dbac7a8.md).



</td>
<td valign="top">

You must set exactly one key attribute for a *Hierarchy*:

-   Child attribute of the parent-child hierarchy structure



</td>
<td valign="top">

A *Hierarchy* will generally not point to other entities.



</td>
</tr>
<tr>
<td valign="top">

*Hierarchy with Directory*

See [Creating a Hierarchy with Directory](creating-a-hierarchy-with-directory-36c39ee.md).



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

