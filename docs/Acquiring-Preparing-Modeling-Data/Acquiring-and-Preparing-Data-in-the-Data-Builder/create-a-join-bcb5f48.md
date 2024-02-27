<!-- loiobcb5f48ec99242da8f2cb3483b8409b7 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Join

Use a join operator to merge two data sets together using a join definition to match the records.



<a name="loiobcb5f48ec99242da8f2cb3483b8409b7__steps_imk_rvj_lyb"/>

## Procedure

1.  Select a source table in the *Repository*, and then drag it over a source table in the diagram. Wait for the context menu to appear, slide your cursor over the *Join* option and then release the mouse button.

2.  Optional. Rename the node in its side panel to clearly identify it. This name can be changed at any time and can contain only alphanumeric characters and underscores.

3.  Set the following properties in the *General* section:


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
    
    Join Type
    
    </td>
    <td valign="top">
    
    Specifies the type of SQL join to create. You can choose from:

    -   Cross - Return all of the rows from the left table joined to all of the rows from the right table.
    -   Full - Return all of the rows from both tables, joining records from the left table where possible.
    -   Inner - \[default\] - Return all of the rows in the left table that have a matching row in the right table.
    -   Left - Return all of the rows from the left table \(whether or not they have a match in the right table\), and any matching rows from the right table.
    -   Right - Return all of the rows from the right table \(whether or not they have a match in the left table\), and any matching rows from the left table.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Distinct Values
    
    </td>
    <td valign="top">
    
    Return only unique values.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Cardinality
    
    </td>
    <td valign="top">
    
    Specifies the number of rows matching another table in a join and may improve the view's performance. You can choose from:

    -   `MANY TO ONE`
    -   `MANY TO EXACT ONE`
    -   `MANY TO MANY`
    -   `ONE TO ONE`
    -   `ONE TO EXACT ONE`
    -   `ONE TO MANY`
    -   `EXACT ONE TO ONE`
    -   `EXACT ONE TO EXACT ONE`
    -   `EXACT ONE TO MANY`

    The cardinality is integrated in the code and is visible in the SQL preview.
    
    </td>
    </tr>
    </table>
    
4.  Specify the mapping of join columns in the *Mappings* section:

    -   A mapping is automatically created by matching column names if possible.
    -   To manually map columns, drag a column from the left list and drop it onto a column in the right list.
    -   To delete a mapping, click the link and then click the *Delete* tool.
    -   You can filter the *Mappings* section to show only mapped or unmapped pairs of columns.
    -   You can filter or sort the left or right column lists independently

5.  Click <span class="FPA-icons-V3"></span> \(Preview Data\) to open the *Data Preview* panel and review the data output by this node. For more information, see [Viewing or Previewing Data in Data Builder Objects](../viewing-or-previewing-data-in-data-builder-objects-b338e4a.md).


