<!-- loioc65e37c5918148e89206a542ee3bb660 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a View Transform

Create a view transform that uses SQL syntax to combine and transform data as part of your transformation flow. You can drag and drop source tables from the *Repository*, join them as appropriate, add other operators to remove or create columns and filter or aggregate data.



## Procedure

1.  Create a new *View Transform* by clicking the *Define View Transform* button.

2.  The system displays the *View Transform Editor*. Add a source table. For more information, see [Add a Source Table](add-a-source-table-ec702fe.md).

3.  Optional: Drag additional source tables from the repository and drop them onto a source table to create a join or union. For more information, see [Create a Join](create-a-join-bcb5f48.md) and [Create a Union](create-a-union-9cd6fbf.md).

4.  Click a node in the diagram to display tools for creating operators and performing other actions:

    > ### Note:  
    > You can only create one each of the *Filter*, *Projection*, *Calculated Columns*, and *Aggregation* operators per source or join in your diagram. Operators can be created in any order.


    <table>
    <tr>
    <th valign="top">

    Tools


    
    </th>
    <th valign="top">

    Description


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons"></span> \(Filter\)


    
    </td>
    <td valign="top">
    
    Add a *Filter* node to filter your data with an SQL expression. For more information, see [Filter Data](../filter-data-6f6fa18.md).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="SAP-icons"></span> \(Rename/Exclude Columns\)


    
    </td>
    <td valign="top">
    
    Add a *Projection* node to rename, reorder, or exclude columns. For more information, see [Reorder, Rename, and Exclude Columns](../reorder-rename-and-exclude-columns-b846d0d.md).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons"></span> \(Calculated Columns\)


    
    </td>
    <td valign="top">
    
    Add a *Calculated Columns* node to create new columns and define calculations in them. For more information, see [Create a Column](../create-a-column-3897f48.md).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons"></span> \(Aggregation\)


    
    </td>
    <td valign="top">
    
    Add an *Aggregation* node to perform `SUM`, `COUNT`, `MIN`, and `MAX` calculations. For more information, see [Aggregate Data](aggregate-data-f368ba0.md).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons"></span> \(Join Suggestion\)


    
    </td>
    <td valign="top">
    
    Create a join from a list of *Related Entities* that is populated based on the presence of associations between the current source and other artifacts.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons"></span> \(Preview Data\)


    
    </td>
    <td valign="top">
    
    Preview the data output by the selected diagram node in the *Data Preview* panel \(see [Viewing or Previewing Data in Data Builder Objects](../viewing-or-previewing-data-in-data-builder-objects-b338e4a.md)\).

    You can preview the SQL generated for the node by clicking the *Preview SQL* button in the panel or by clicking <span class="FPA-icons"></span> Export and selecting *Preview SQL*. Click *Copy* to copy the SQL code for pasting into the SQL View editor or elsewhere.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons"></span> \(Impact and Lineage Analysis\)


    
    </td>
    <td valign="top">
    
    Open the Impact and Lineage Analysis diagram. This diagram enables you to understand the lineage and impacts of the selected object. 

    \(see [Impact and Lineage Analysis](../Creating-Finding-Sharing-Objects/impact-and-lineage-analysis-9da4892.md).\)


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="SAP-icons"></span> \(Open in New Tab\)


    
    </td>
    <td valign="top">
    
    Open the object in its own editor in a new tab.


    
    </td>
    </tr>
    </table>
    
