<!-- loio947d6d8d447f40169a720cdeaad78c8a -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Create a Join

Drag a source from the *Source Browser* and drop it onto a source or other node in the diagram.



## Procedure

1.  If the *Source Browser* panel is not visible on the left of the screen, click *Source Browser* in the toolbar to show it.

2.  Browse or search for the object you want to add on either of the tabs.

    -   The *Repository* tab lists all the tables, views, and intelligent lookups that are available in the space \(including objects shared to the space\). You can search and expand the categories \(see [Add Objects from the Repository](add-objects-from-the-repository-13fcecd.md)\).

    -   The *Sources* tab lists all the connections and other data sources that have been integrated to the space from which you can import tables. You can:

        -   Expand the data sources to browse through their objects \(see [Import an Object from a Connection or Other Source](import-an-object-from-a-connection-or-other-source-3e6f8f2.md)\).
        -   Open the *Import Objects from Connection* dialog on a particular connection to select multiple objects for import \(see [Import Multiple Objects from a Connection](import-multiple-objects-from-a-connection-e720b13.md)\).


3.  Select the object of your choice, and then drag it over a source or other node in the diagram. When the target node is highlighted green, drop the new source to create a join.

    ![](images/Create_Join_Gif_dc051d5.gif)The source is added to the diagram and it is joined to the target node. The join symbol is selected and its properties are displayed in the side panel. A projection node is added after the join node to remove any duplicate columns.

    > ### Note:  
    > If you choose a table or view from the *Sources* tab, it is automatically imported into the repository and deployed, and will be available on the *Repository* tab for future use by you or others.

4.  Optional. Rename the node in its side panel to clearly identify it. This name can be changed at any time and can contain only alphanumeric characters and underscores.

5.  Set the following properties in the *General* section:


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
    
6.  Specify the mapping of join columns in the *Mappings* section:

    -   A mapping is automatically created by matching column names if possible.
    -   To manually map columns, drag a column from the left list and drop it onto a column in the right list.
    -   To delete a mapping, click the link and then click the *Delete* tool.
    -   You can filter the *Mappings* section to show only mapped or unmapped pairs of columns.
    -   You can filter or sort the left or right column lists independently

7.  Click <span class="FPA-icons"></span> \(Preview Data\) to open the *Data Preview* panel and review the data output by this node. For more information, see [Viewing or Previewing Data in Data Builder Objects](viewing-or-previewing-data-in-data-builder-objects-b338e4a.md).


