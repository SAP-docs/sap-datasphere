<!-- loio098ada182bbe43febadbd6374105a173 -->

# Process Source Changes in the Graphical View Editor

If one or more of the source tables of your view transform is modified, then the next time you open the *Graphical View Editor*, you can view any changes by viewing the relevant validation messages.



<a name="loio098ada182bbe43febadbd6374105a173__steps_awd_5fj_nyb"/>

## Procedure

1.  If a source change has generated warnings or errors in your graphical view transform, you can view any changes by viewing the relevant validation messages.

2.  The following validation messages may be displayed:


    <table>
    <tr>
    <th valign="top">

    Change in Source
    
    </th>
    <th valign="top">

    Impact
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Add Column
    
    </td>
    <td valign="top">
    
    Columns added to source tables or views are excluded by default for the view transform:

    -   An information message listing all new columns is displayed on the source.
    -   The new columns are excluded in a projection node directly after the source. If no projection node was previously present, then one is added.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Change Business Name
    
    </td>
    <td valign="top">
    
    Changes to the business name and other business properties of a source table or its columns are automatically propagated to dependent objects:

    -   An information message specifying the source object changes or listing all changed columns is displayed on the source.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Change Column Data Type
    
    </td>
    <td valign="top">
    
    Changes column data types in source tables generate warnings:

    -   An information message listing all columns with changed data types is displayed on the source.
    -   An information message listing all columns with changed data types present in the output node *Columns* list is displayed on the output node.
    -   If output columns with changed data types are used by any dependent objects of this view, then a warning message listing those views is displayed on the output node.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Delete Column
    
    </td>
    <td valign="top">
    
    Deletions of columns in source tables generate errors if the columns are used by the view transforms:

    -   An information message listing all deleted columns is displayed on the source.
    -   An error message is displayed on any intermediate node \(join, union, filter, calculated columns, aggregation\) in which a deleted column was used.
    -   A warning message listing all deleted columns that were previously present in the output node *Columns* list is displayed on the output node.
    -   If deleted output columns were used by any dependent objects of this view, then a warning message listing those views is displayed on the output node.


    
    </td>
    </tr>
    </table>
    
3.  Review all information and warning messages to ensure that they do not adversely impact the output of your graphical view transform.

4.  Review and resolve any error messages on intermediate nodes.

5.  Click the *Back* button to return to the *Transformation Flow Editor*, and then save and deploy the transformation flow.


