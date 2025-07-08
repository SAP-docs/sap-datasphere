<!-- loio1fd3f07ea9a545598dfa27aebd4b492b -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Collect Unassigned Fact Records for Inclusion in Aggregations and Visualizations

The *Missing Hierarchy Nodes* data validation rule can generate files to create an `unassigned` hierarchy node to collect records in a fact that point to nodes that are missing from an associated *Hierarchy with Directory*, and make them available for inclusion in your aggregations and visualizations.

> ### Note:  
> This procedure and the views it generates will only collect unassigned records for the fact from which the data validation rule is run. If multiple facts use the same dimension and hierarchy with directory, then you should complete this procedure for each fact that has unassigned records.

1.  Open your entity with a semantic usage of fact.
2.  Run the data validation including the *Missing Hierarchy Nodes* rule.
3.  Click *Details* to open the dialog and then click *Download CSN* to download the `.csn` file containing the generated views.
4.  Go to the *Data Builder* start page and click <span class="FPA-icons-V3"></span> \(Import\)** \> *Import Objects from CSN/JSON File* to import the generated views into your space.

    For more information, see [Importing Objects from a CSN/JSON File](Creating-Finding-Sharing-Objects/importing-objects-from-a-csn-json-file-23599e6.md).

5.  Review and modify the generated views as appropriate:


    <table>
    <tr>
    <th valign="top">

    View
    
    </th>
    <th valign="top">

    Purpose
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Business Name: <code>Validation Results for Missing Hierarchy Nodes in <i class="varname">&lt;hierarchy&gt;</i></code>

    Technical Name: <code><i class="varname">&lt;hierarchy&gt;</i>_VALIDATION</code>
    
    </td>
    <td valign="top">
    
    Lists missing nodes identified by the rule.

    \[optional\] Open this view and use the *Data Viewer* to see the list of missing nodes \(see [Viewing Object Data](viewing-object-data-b338e4a.md)\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Business Name: <code>Unassigned Nodes in <i class="varname">&lt;hierarchy&gt;</i></code>

    Technical Name: <code><i class="varname">&lt;hierarchy&gt;</i>_MISSING</code>
    
    </td>
    <td valign="top">
    
    Places these missing records in a root `Unassigned` hierarchy node.

    \[optional\] To improve performance, you can persist the data in this view \(see [Persist Data in a Graphical or SQL View](persist-data-in-a-graphical-or-sql-view-9bd12cf.md)\). We strongly recommend that you schedule persistence regularly to ensure that recent records are assigned promptly.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Business Name: <code>Enhanced <i class="varname">&lt;hierarchy&gt;</i></code>

    Technical Name: <code><i class="varname">&lt;hierarchy&gt;</i>_ENHANCED</code>
    
    </td>
    <td valign="top">
    
    Unions the records for your hierarchy with directory and those that are `Unassigned` \(and collected in <code><i class="varname">&lt;hierarchy&gt;</i>_MISSING</code>\) to ensure that all records canbe included in your aggregations and visualizations.

    \[required\] You must modify your dimension, which has an association to <code><i class="varname">&lt;hierarchy&gt;</i></code>, and ensure that it points instead to this view.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Business Name: <code>Enhanced <i class="varname">&lt;dimension&gt;</i></code>

    Technical Name: <code><i class="varname">&lt;dimension&gt;</i>_ENHANCED</code>
    
    </td>
    <td valign="top">
    
    \[if <code><i class="varname">&lt;dimension&gt;</i></code> is shared from another space\] Encapsulates the shared dimension and replaces it as the link between the fact and the hierarchy.

    \[required\] You must modify your fact so that its association points to this dimension.
    
    </td>
    </tr>
    </table>
    
6.  Save and deploy your changes.
7.  Review your analytic model or SAP Analytics Cloud story to ensure that your aggregations and visualizations now display correctly with a suitable `Unassigned` category.

    > ### Note:  
    > If, over time, you modify your fact records to point to existing hierarchy nodes \(or provide new hierarchy nodes for the values in your fact records\), then the value of your `unassigned` node will be reduced accordingly.


