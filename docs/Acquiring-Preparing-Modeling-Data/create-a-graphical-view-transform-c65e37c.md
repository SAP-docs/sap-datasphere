<!-- loioc65e37c5918148e89206a542ee3bb660 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Create a Graphical View Transform

Create a graphical view transform that uses SQL syntax to combine and transform data as part of your transformation flow. You can drag and drop sources from the *Repository* tab or from the *Sources* tab, join them as appropriate, add other operators to remove or create columns and filter or aggregate data.



## Context

When working in a view transform, you are using an editor similar to the standard view editors with the following modifications:

-   View transforms do not support creating input parameters or adding data access controls, and the output node does not contain any information except for the list of columns passed to the target node.
-   If you add an entity containing input parameters as a source to a view transform, then you must set a value for each input parameter.

    > ### Note:  
    > If you add a remote table shared from an SAP BW bridge space and configured to load delta changes as a source:
    > 
    > -   It is no longer possible to preview the data being output by the view transform.
    > -   The system adds the following read-only input parameters to the view transform:
    >     -   REQTSN\_LOW - When loading delta changes, the value of this input parameter is the watermark. When loading all active records, the value of this input parameter is the minimum timestamp. For more information, see [Watermarks](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/890897f00a4944c7a6f90d3816a8d4c6.html "When you run a transformation flow that loads delta changes to a target table, the system uses a watermark (a timestamp) to track the data that has been transferred.") :arrow_upper_right:.
    >     -   REQTSN\_HIGH - The value of this input parameter is the maximum timestamp.
    >     -   EXTRACTION\_MODE - The value of this input parameter is DELTA\_AI to indicate the loading of delta changes from the remote table.

-   You cannot save and deploy the view transform \(the secondary editor\) separately from the transformation flow \(the primary editor\). To exit the view transform editor, click the <span class="FPA-icons-V3"></span> \(Navigate Back\) button in the editor toolbar.



## Procedure

1.  On the *New Transformation Flow* screen, click the *View Transform* node.

2.  Create a new *Graphical View Transform* for your transformation flow by clicking the *Graphical View Transform* button.

3.  The system displays the *Graphical View Editor*. Add a source. For more information, see [Add a Source to a Graphical View](add-a-source-to-a-graphical-view-1eee180.md).

4.  Optional: Drag additional sources from the *Repository* tab or from the *Sources* tab and drop them onto a source to create a join or union. For more information, see [Create a Join in a Graphical View](create-a-join-in-a-graphical-view-947d6d8.md) and [Create a Union in a Graphical View](create-a-union-in-a-graphical-view-5c3d354.md).

5.  Click a node in the diagram to display tools for creating operators and performing other actions:

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
    
    <span class="FPA-icons-V3"></span> \(Filter\)
    
    </td>
    <td valign="top">
    
    Add a *Filter* node to filter your data with an SQL expression. For more information, see [Filter Data in a Graphical View](filter-data-in-a-graphical-view-6f6fa18.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="SAP-icons-V5"></span> \(Rename/Exclude Columns\)
    
    </td>
    <td valign="top">
    
    Add a *Projection* node to rename, reorder, or exclude columns. For more information, see [Reorder, Rename, and Exclude Columns in a Graphical View](reorder-rename-and-exclude-columns-in-a-graphical-view-b846d0d.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Calculated Columns\)
    
    </td>
    <td valign="top">
    
    Add a *Calculated Columns* node to create new columns and define calculations in them. For more information, see [Create a Calculated Column in a Graphical View](create-a-calculated-column-in-a-graphical-view-3897f48.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Aggregation\)
    
    </td>
    <td valign="top">
    
    Add an *Aggregation* node to perform `SUM`, `COUNT`, `MIN`, and `MAX` calculations. For more information, see [Aggregate Data in a Graphical View](aggregate-data-in-a-graphical-view-7733250.md). 

    > ### Note:  
    > You cannot perform an aggregation in a transformation flow with a target table that has delta capture enabled, since the change-tracking columns must be output and cannot be excluded to allow an appropriate grouping expression.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Join Suggestion\)
    
    </td>
    <td valign="top">
    
    Create a join from a list of *Related Entities* that is populated based on the presence of associations between the current source and other artifacts.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Preview Data\)
    
    </td>
    <td valign="top">
    
    Preview the data output by the selected diagram node in the *Data Preview* panel \(see [Viewing Object Data](viewing-object-data-b338e4a.md)\).

    You can preview the SQL generated for the node by clicking the *Preview SQL* button in the panel or by clicking <span class="FPA-icons-V3"></span> Export and selecting *Preview SQL*. Click *Copy* to copy the SQL code for pasting into the SQL View editor or elsewhere.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Impact and Lineage Analysis\)
    
    </td>
    <td valign="top">
    
    Open the Impact and Lineage Analysis diagram. This diagram enables you to understand the lineage and impacts of the selected object. \(see [Impact and Lineage Analysis](impact-and-lineage-analysis-9da4892.md).\)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="SAP-icons-V5"></span> \(Open in New Tab\)
    
    </td>
    <td valign="top">
    
    Open the object in its own editor in a new tab.
    
    </td>
    </tr>
    </table>
    
6.  Click the <span class="FPA-icons-V3"></span> \(Navigate Back\) button to save your work and return to the *Transformation Flow Editor*. You can then add or create a target table for the transformation flow. For more information, see [Create or Add a Target Table to Your Transformation Flow](create-or-add-a-target-table-to-your-transformation-flow-0950746.md).


