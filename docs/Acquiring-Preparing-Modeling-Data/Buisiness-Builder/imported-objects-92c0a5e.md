<!-- loio92c0a5ee5eb24865b60f1b070c6c14e0 -->

# Imported Objects



Overview of metadata mapping and the deployment status after model transfer


<table>
<tr>
<th valign="top" colspan="2">

SAP BW/4HANA

</th>
<th valign="top" colspan="2">

SAP Datasphere

</th>
</tr>
<tr>
<th valign="top">

Model

</th>
<th valign="top">

Sub-Model

</th>
<th valign="top">

Data Builder

</th>
<th valign="top">

Business Builder

</th>
</tr>
<tr>
<td valign="top" rowspan="5">

InfoObject

</td>
<td valign="top">

Master Data

</td>
<td valign="top">

Remote table

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Text

</td>
<td valign="top">

Remote table

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

InfoObject

</td>
<td valign="top">

View with prefix DL

</td>
<td valign="top">

Dimension

</td>
</tr>
<tr>
<td valign="top">

InfoObject with text

</td>
<td valign="top">

Additional view with prefix TA

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Hierarchy and dependent objects, e.g. texts, hierarchy nodes, hierarchy node texts

</td>
<td valign="top">

Remote table\(s\) and view\(s\) for hierarchy and dependent objects with suffix, e.g. H, HT, NT

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

CompositeProvider

</td>
<td valign="top">

Fact

</td>
<td valign="top">

Remote table

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

InfoProvider

</td>
<td valign="top">

View with prefix DL \(with associations to dimension views\) \(fact\)

</td>
<td valign="top">

Fact \(with associations to dimensions\)

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Query

</td>
<td valign="top">

Query \(Restricted Key Figure, Calculated Key Figure, Filter\)

</td>
<td valign="top">

Analytic Model

</td>
<td valign="top">

Consumption Model

</td>
</tr>
<tr>
<td valign="top">

Query \(visible part of query for consumption\)

</td>
<td valign="top">



</td>
<td valign="top">

Perspective for consumption in stories in SAP Analytics Cloud

</td>
</tr>
</table>

