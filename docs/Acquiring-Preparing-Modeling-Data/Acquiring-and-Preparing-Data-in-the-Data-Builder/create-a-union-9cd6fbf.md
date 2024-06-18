<!-- loio9cd6fbf4710e4a31a3fd5246302ed9ec -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Union

A union combines the results from two select statements on separate sources.



<a name="loio9cd6fbf4710e4a31a3fd5246302ed9ec__steps_usp_wtj_lyb"/>

## Procedure

1.  Browse or search for the object you want to add on either the *Repository* tab or the *Sources* tab.

2.  Select a source, and then drag it over a source table in the diagram. Wait for the context menu to appear, slide your cursor over the *Union* option and then release the mouse button.

    The source is added to the diagram and it is unioned with the target node. The union symbol is selected and its properties are displayed in the side panel. You can add multiple tables to the union by dragging and dropping them on the union symbol.

3.  Optional. Rename the node in its side panel to clearly identify it. This name can be changed at any time and can contain only alphanumeric characters and underscores.

4.  Set the following properties in the *General* section:


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Union All
    
    </td>
    <td valign="top">
    
    Default option and fastest to create. It combines two or more `SELECT` statements or queries and includes all rows, including duplicates. Disabling this option applies *Union*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Union
    
    </td>
    <td valign="top">
    
    It combines the result set of two or more `SELECT` statements or queries \(only distinct values\) and returns fewer rows. It takes longer to create it because it removes duplicate rows.
    
    </td>
    </tr>
    </table>
    
5.  The *Mappings* section shows, by default, the recently dropped source object columns on the left and the union output columns, initialized from the target source columns on the right.

    -   Mappings are automatically created by matching column names where possible.
    -   To manually map input columns to union output columns, drag a column from the left list and drop it onto a column in the right list.
    -   To delete a mapping, click the link and then click the *Delete* tool.
    -   You can filter the *Mappings* section to show only mapped or unmapped pairs of columns.
    -   You can filter or sort the left or right column lists independently.
    -   You can modify the list of union output columns using the Menu above the right list:
        -   *Add All Source Columns as Union Columns* - Add all columns in the left list to the right list \(if they are not already present\).
        -   *Add Selected Source Columns as Union Columns* - Add columns selected in the left list to the right list \(if they are not already present\).
        -   *Delete Selected Union Columns* - Delete any columns selected in the right list so that they are no longer union output columns.
        -   *Delete All Union Columns* - Delete all columns in the right list so that they are no longer union output columns.

    -   To switch to viewing another input, click the drop-down arrow above the left column list and select it in the list.

6.  Optional. Drop another source object onto the union node to union it with the existing unioned sources.

    The source table is added to the diagram and added to the union node. The union symbol is selected, its properties are displayed in the side panel, the new source table is displayed in the *Mappings* section and its columns are mapped automatically by matching column names where possible.

7.  Click <span class="FPA-icons-V3"></span> \(Preview Data\) to open the *Data Preview* panel and review the data output by this node. For more information, see [Viewing Object Data](../viewing-object-data-b338e4a.md).


