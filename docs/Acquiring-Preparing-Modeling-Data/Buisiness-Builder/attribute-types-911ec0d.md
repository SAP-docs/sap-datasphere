<!-- loio911ec0d8ae544d7197eccac52d4989ae -->

# Attribute Types

There are different types of attributes to be used in fact models and consumption models.

**Attribute Types**


<table>
<tr>
<th valign="top">

Attribute Type



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

Dimension Source Attribute



</td>
<td valign="top">

References an attribute from a dimension source in the consumption model.



</td>
</tr>
<tr>
<td valign="top">

Calculated Attribute



</td>
<td valign="top">

A calculated attribute is based on a formula which is specified as an SQL expression and must match the chosen data type. The calculation evaluates on rows - access to values in other rows \(cell-reference\) is not possible.

An automatic validation takes place to provide immediate feedback.

For more information on syntax and available functions, please refer to the [SAP HANA SQL Functions Reference](https://help.sap.com/viewer/4fe29514fd584807ac9f2a04f6754767/2.0.05/en-US/20a61f29751910149f99f0300dd95cd9.html) and [Operators Reference](https://help.sap.com/viewer/4fe29514fd584807ac9f2a04f6754767/2.0.05/en-US/20a380977519101494ceddd944e87527.html).



</td>
</tr>
<tr>
<td valign="top">

Fact Source Attribute Mapping/Fact Source Attribute



</td>
<td valign="top">

Allows mapping of common attributes across the fact sources in the source model. Fact sources that do not provide an applicable attribute may default to NULL or to a constant value. You only have to map fact sources when your consumption model contains more than one fact source. If your consumption model contains only one fact source, the attribute type is called *Fact Source Attribute*.



</td>
</tr>
</table>

