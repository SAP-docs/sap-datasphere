<!-- loioed4063dc7f53436d806ea48f2fd3949a -->

# Validating View Data

Data must be complete and consistent if it is to provide accurate analytics. This new validation framework provides initial validation rules to check the consistency of your view key columns and hierarchy nodes.

This topic contains the following sections:

-   [Run a Data Validation](validating-view-data-ed4063d.md#loioed4063dc7f53436d806ea48f2fd3949a__section_intro)
-   [Key Validation Rules](validating-view-data-ed4063d.md#loioed4063dc7f53436d806ea48f2fd3949a__section_keys)
-   [Hierarchy Validation Rules](validating-view-data-ed4063d.md#loioed4063dc7f53436d806ea48f2fd3949a__section_hierarchies)
-   [Data Type Validation Rules](validating-view-data-ed4063d.md#loioed4063dc7f53436d806ea48f2fd3949a__section_data_types)



<a name="loioed4063dc7f53436d806ea48f2fd3949a__section_intro"/>

## Run a Data Validation

The *Data Validation Status* button in the view properties panel shows the status of the last data validation, and the *Validated On* field shows the date and time of the last run.

To validate data \(or review the results of a previous validation\):

1.  Click the *Data Validation Status* button to open the *Data Validation* panel.

    Alternatively, if the *Data Preview* panel is already open, click the *Data Validation* tab.

2.  If the panel is empty \(or if you want to re-run the validation\), click *Validate*.

    If the view has one or more remote sources, you can run validations if this is supported by the connection adapter. In this case, a warning is displayed and you can choose to continue with the validation, cancel, or open the *View Analyzer* to determine whether one or more sources should be replicated \(see [Exploring Views with View Analyzer](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/8921e5acf2ad4c8a98073edae4c214c7.html "Use the View Analyzer to explore graphical or SQL views and the entities they consume.") :arrow_upper_right:\).

    > ### Note:  
    > If individual validation rules cannot be run against remote sources they will provide this information in place of a result.

    The time required for data validation depends on the number of records and the complexity of calculations required. If validation is taking too long, you can click *Cancel Validation* in the panel toolbar. You will receive a notification when validation is complete.

3.  Review the validation results.

    There is one result for each rule and it shows the following information:


    <table>
    <tr>
    <th valign="top">

    Column
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Category
    
    </td>
    <td valign="top">
    
    Displays the name of the validation rule category.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Rule
    
    </td>
    <td valign="top">
    
    Displays the name of the validation rule.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Object
    
    </td>
    <td valign="top">
    
    Displays the name of the object being validated.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Message
    
    </td>
    <td valign="top">
    
    Displays the number of records that are not consistent with the rule. Click *Details* to see further information.
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > Some validation rules may be unavailable if:
    > 
    > -   Your view or any of its sources is protected by a data access control.
    > -   Your view or any of its sources contains input parameters.
    > -   Any of your view's sources is not replicated to SAP Datasphere.

4.  For rules with errors, click the *Details* link to get further information.

    The *Details* dialog explains the rule and lets you copy SQL \(or SQLScript\) code to generate a list of invalid records.

5.  In the *Details* dialog, click *Copy SQL* \(or *Copy SQLScript*\) to get the code necessary to generate the full list of records that are not consistent with the rule.
6.  Create a new SQL view, select the appropriate language, paste the code into it, and preview the data to see these failing records \(see [Creating an SQL View](creating-an-sql-view-81920e4.md)\).



<a name="loioed4063dc7f53436d806ea48f2fd3949a__section_keys"/>

## Key Validation Rules

The following rules are available in the *Keys* category:


<table>
<tr>
<th valign="top">

Rule

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Unique Key Values

</td>
<td valign="top">

Each record must have unique primary key values.

For example, if an object has primary key columns `ID` and `Language` and a record has primary key values of `1` and `EN`, then no other record may have this combination of values.

</td>
</tr>
<tr>
<td valign="top">

No Null Key Values

</td>
<td valign="top">

No record may have null primary key values.

For example, if an object has primary key columns `ID` and `Language` no record may have null values in these columns.

</td>
</tr>
<tr>
<td valign="top">

Referential Integrity

</td>
<td valign="top">

No fact record may contain a value in a foreign key column if the value is not present in the mapped key column of the associated dimension.

For example, if the `Sales` fact has a foreign key column `Product ID` with an association to a `Products` dimension, then all the values in that column must be found in the primary key column of the dimension.

> ### Note:  
> This validation rule is only available in views with a semantic usage "Fact" and for associations from the fact to dimensions.



</td>
</tr>
<tr>
<td valign="top">

Unique Target Values

</td>
<td valign="top">

No dimension, text entity, or hierarchy, which is the target of an association from the view may contain records that do not provide unique values for identifying records.

For example, if an object has an association to a "Products" dimension, then the target columns mapped in the "Products" dimension must contain values uniquely identifying each record \(even if these columns are not marked as keys\).

</td>
</tr>
</table>

For information about working with keys, see [Set Key Columns to Uniquely Identify Records](Modeling-Data-in-the-Data-Builder/set-key-columns-to-uniquely-identify-records-d9ef2c9.md).



<a name="loioed4063dc7f53436d806ea48f2fd3949a__section_hierarchies"/>

## Hierarchy Validation Rules

The following rules are available in the *Hierarchies* category:


<table>
<tr>
<th valign="top">

Rule

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

No Multiple Parents

</td>
<td valign="top">

No hierarchy node may have multiple parents.

For example, if a hierarchy node `A` has a parent node `B`, then it may not have any other parent.

</td>
</tr>
<tr>
<td valign="top">

No Circular Hierarchies

</td>
<td valign="top">

No hierarchy node may have circular parent-child relationships.

For example, if a hierarchy node `A` has a parent node `B`, then it may not also have node `B` as a direct child or other descendant.

</td>
</tr>
<tr>
<td valign="top">

Missing Hierarchy Nodes

</td>
<td valign="top">

Available only in views with a *Semantic Usage* of *Fact* that have an association to a dimension that is, in turn, associated to a *Hierarchy with Directory*.

Each hierarchy defined in the hierarchy with directory must provide nodes for all appropriate foreign key values used in records in the fact.

For example, if a fact contains records with the `DE` country code but that code is not present in a hierarchy defined in an associated hierarchy with directory, then any data allocated to `DE` will not appear in aggregations that are viewed using this hierarchy.

This rule can generate files to collect missing nodes and allocate them to an "Unassigned" root node \(see [Collect Unassigned Fact Records for Inclusion in Aggregations and Visualizations](collect-unassigned-fact-records-for-inclusion-in-aggregations-and-visualizations-1fd3f07.md)\).

</td>
</tr>
</table>

For information about working with hierarchies, see:

-   [Create an External Hierarchy for Drill-Down](Modeling-Data-in-the-Data-Builder/create-an-external-hierarchy-for-drill-down-dbac7a8.md)
-   [Create a Hierarchy with Directory](Modeling-Data-in-the-Data-Builder/create-a-hierarchy-with-directory-36c39ee.md)
-   [Add a Hierarchy to a Dimension](Modeling-Data-in-the-Data-Builder/add-a-hierarchy-to-a-dimension-218b7e6.md)



<a name="loioed4063dc7f53436d806ea48f2fd3949a__section_data_types"/>

## Data Type Validation Rules

The following rules are available in the *Data Types* category:


<table>
<tr>
<th valign="top">

Rule

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Consistent Data Types

</td>
<td valign="top">

All columns must have appropriate data types.

For example, if a column `A` is specified as having a data type `Date`, and SAP HANA Cloud determines that the data type must be `String(10)`, then this inconsistency may cause run-time errors or wrong data to be returned.

</td>
</tr>
</table>

For information about working with data types, see [Column Data Types](Acquiring-and-Preparing-Data-in-the-Data-Builder/column-data-types-7b1dc6e.md).

