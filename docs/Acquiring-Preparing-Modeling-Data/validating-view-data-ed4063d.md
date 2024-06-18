<!-- loioed4063dc7f53436d806ea48f2fd3949a -->

# Validating View Data

Data must be complete and consistent if it is to provide accurate analytics. This new validation framework provides initial validation rules to check the consistency of your view key columns and hierarchy nodes.

This topic contains the following sections:

-   [Run a Data Validation](validating-view-data-ed4063d.md#loioed4063dc7f53436d806ea48f2fd3949a__section_intro)
-   [Key Validation Rules](validating-view-data-ed4063d.md#loioed4063dc7f53436d806ea48f2fd3949a__section_keys)
-   [Hierarchy Validation Rules](validating-view-data-ed4063d.md#loioed4063dc7f53436d806ea48f2fd3949a__section_hierarchies)



<a name="loioed4063dc7f53436d806ea48f2fd3949a__section_intro"/>

## Run a Data Validation

The *Data Validation Status* button in the view properties panel shows the status of the last data validation, and the *Validated On* field shows the date and time of the last run.

To validate data \(or review the results of a previous validation\):

1.  Click the *Data Validation Status* button to open the *Data Validation* panel.

    Alternatively, if the *Data Preview* panel is already open, click the *Data Validation* tab.

2.  If the panel is empty \(or if you want to re-run the validation\), click *Validate*.

    The time required for data validation depends on the number of records and the complexity of calculations required. You will receive a notification when validation is complete.

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
</table>



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
</table>

