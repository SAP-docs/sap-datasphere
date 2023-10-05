<!-- loiof8ce0b4a24fe473a962176c8aa3cad42 -->

# Repository Explorer

The *Repository Explorer* gives you access to all your SAP Datasphere objects. You can search and filter the list, open or act on existing objects, and create new objects.

This topic contains the following sections:

-   [Open the Repository Explorer](repository-explorer-f8ce0b4.md#loiof8ce0b4a24fe473a962176c8aa3cad42__section_open)
-   [Enter a String to Search On](repository-explorer-f8ce0b4.md#loiof8ce0b4a24fe473a962176c8aa3cad42__section_string_search)
-   [Filter by Collection or Space](repository-explorer-f8ce0b4.md#loiof8ce0b4a24fe473a962176c8aa3cad42__section_collection_space_filter)
-   [Filter by Criteria](repository-explorer-f8ce0b4.md#loiof8ce0b4a24fe473a962176c8aa3cad42__section_criteria_filter)
-   [Create Objects and Act on Existing Objects](repository-explorer-f8ce0b4.md#loiof8ce0b4a24fe473a962176c8aa3cad42__section_tools)



<a name="loiof8ce0b4a24fe473a962176c8aa3cad42__section_open"/>

## Open the Repository Explorer

Click *Repository Explorer* in the left navigation area. There is no need to select a space. The *Explorer* shows you all the objects in all the spaces you are assigned to.

![](images/explorer_e469392.png)

> ### Note:  
> The *Repository Explorer* lists your *Data Builder* objects and data access controls. *Business Builder* objects can be accessed via the *Business Builder* start page \(see [Modeling Data in the Business Builder](../Buisiness-Builder/modeling-data-in-the-business-builder-3829d46.md)\).



<a name="loiof8ce0b4a24fe473a962176c8aa3cad42__section_string_search"/>

## Enter a String to Search On

Enter one or more characters in the *Search* field and press *Enter* \(or click *Search*\).

As you type, the field will begin proposing objects and search strings. Select an object to open it directly. Click on a string to trigger a search on it.



<a name="loiof8ce0b4a24fe473a962176c8aa3cad42__section_collection_space_filter"/>

## Filter by Collection or Space

Restrict the scope of the list by selecting a collection or space in the *Search In* area of the left panel.

Choose one collection or one space:

-   *Collection*:
    -   *All* \(default\)
    -   *Recent* - Objects that you recently opened
    -   *My Objects* - Objects that you created
    -   *Shared* - Objects that are shared from/to their space to/from other spaces

        > ### Note:  
        > If you are not assigned to a space an object is shared from, it appears greyed out and you cannot open or otherwise act on it.

    -   *Favorites* - Objects that you have favorited \(by clicking the star in the *Actions* column\)

-   *Space*: Up to five spaces are listed here in order of your last visit. If you are assigned to more than five spaces, you can add them by clicking *Show More* and selecting them in the dialog.



<a name="loiof8ce0b4a24fe473a962176c8aa3cad42__section_criteria_filter"/>

## Filter by Criteria

Filter by any of the categories listed in the *Filter By* area of the left panel.

You can select one or more values in each filter category in the *Filter By* section:

-   Each value selected in a category acts as an `OR` condition.
-   Values selected in separate categories act together as `AND` conditions.

For example, to:


<table>
<tr>
<th valign="top">

To Display



</th>
<th valign="top">

Select Filter Criteria



</th>
</tr>
<tr>
<td valign="top">

All objects with a semantic usage of *Fact*



</td>
<td valign="top">

*Semantic Usage*: *Fact*



</td>
</tr>
<tr>
<td valign="top">

All objects with a semantic usage of *Fact* or *Dimension*



</td>
<td valign="top">

*Semantic Usage*: *Fact*, *Dimension*



</td>
</tr>
<tr>
<td valign="top">

Only views with a semantic usage of *Fact* or *Dimension*



</td>
<td valign="top">

*Type* \> *View*

and

*Semantic Usage*: *Fact*, *Dimension*



</td>
</tr>
</table>

Filtering for shared objects changes when you select a space:


<table>
<tr>
<th valign="top">

To Display



</th>
<th valign="top">

Select Filter Criteria



</th>
</tr>
<tr>
<td valign="top">

All objects that are shared with any other spaces



</td>
<td valign="top">

*Sharing* \> *Shared*



</td>
</tr>
<tr>
<td valign="top">

All objects that are shared from a particular space



</td>
<td valign="top">

*Space* \> **<Space\>**

and

*Sharing* \> *Shared from My Space*



</td>
</tr>
<tr>
<td valign="top">

All objects that are shared with a particular space



</td>
<td valign="top">

*Space* \> **<Space\>**

and

*Sharing* \> *Shared with My Space*



</td>
</tr>
</table>

> ### Note:  
> If you are not assigned to a space an object is shared from, it appears greyed out and you cannot open or otherwise act on it.



<a name="loiof8ce0b4a24fe473a962176c8aa3cad42__section_b25_xs5_cxb"/>

## Define Advanced Filter Conditions

For those filter options that are not related to date or time, you can create a custom filter with specific conditions.

1.  Click *Show More* at the bottom of a filter category to open the Filter Settings dialog. Some filters have a *Select Items* and a *Define Conditions* tab.
2.  On the *Define Conditions* tab, choose an operator and enter a value in the *Filter Condition* box.
3.  Click the plus icon to create an alternative condition. Each condition in one category acts as an `OR` operator, so that an object must meet one of the conditions to be included in the search results. If you define one condition in two categories, then each category acts as an `AND` operator, so that both conditions must be true for the object to be returned in the search results.

You can create advanced filter conditions for multiple filter categories. An object must meet one of the conditions in each of the categories to be included in the search results.



<a name="loiof8ce0b4a24fe473a962176c8aa3cad42__section_tools"/>

## Create Objects and Act on Existing Objects

You can act on objects in the list in the following ways:

-   Click the *Business Name* of an object to open it in its editor.
-   Click the *Favorite* tool in the *Actions* column to add an object to your *Favorites* collection.
-   Select one or more objects and use any of the following tools:

    > ### Note:  
    > If you select an object that is shared from a space you're not assigned to, you cannot access any of these tools.


    <table>
    <tr>
    <th valign="top">

    Tool


    
    </th>
    <th valign="top">

    Description


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Create


    
    </td>
    <td valign="top">
    
    Create a new object \(independent of any selection\) and open it in the appropriate editor. 

    Choose from the following:

    -   Local Table \(see [Creating a Local Table](../Acquiring-and-Preparing-Data-in-the-Data-Builder/creating-a-local-table-2509fe4.md)\)
    -   Graphical View \(see [Creating a Graphical View](../creating-a-graphical-view-27efb47.md)\)
    -   SQL View \(see [Creating an SQL View](../creating-an-sql-view-81920e4.md)\)
    -   Entity-Relationship Model \(see [Creating an Entity-Relationship Model](../creating-an-entity-relationship-model-a91c042.md)\)
    -   Data Flow \(see [Creating a Data Flow](../Acquiring-and-Preparing-Data-in-the-Data-Builder/creating-a-data-flow-e30fd14.md)\)
    -   Data Access Control \(see [Create a Data Access Control](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/5246328ec59045cb9c2aa693daee2557.html "Space administrators can create data access controls to define criteria on which data can be displayed to users.") :arrow_upper_right:\)
    -   Currency Conversion Views \(see [Enabling Currency Conversion with TCUR\* Tables and Views](enabling-currency-conversion-with-tcur-tables-and-views-b462239.md)\)


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Edit


    
    </td>
    <td valign="top">
    
    Open the selected object in the appropriate editor. 


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Deploy


    
    </td>
    <td valign="top">
    
    Deploy the selected objects. Allows multi-selection of supported object types from a single space. 

    Only the following object types can be deployed here:

    -   Local Table \(see [Creating a Local Table](../Acquiring-and-Preparing-Data-in-the-Data-Builder/creating-a-local-table-2509fe4.md)\)
    -   Graphical View \(see [Creating a Graphical View](../creating-a-graphical-view-27efb47.md)\)
    -   SQL View \(see [Creating an SQL View](../creating-an-sql-view-81920e4.md)\)
    -   Data Access Control \(see [Create a Data Access Control](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/5246328ec59045cb9c2aa693daee2557.html "Space administrators can create data access controls to define criteria on which data can be displayed to users.") :arrow_upper_right:\)
    -   Analytic Model \(see [Creating an Analytic Model](../Modeling-Data-in-the-Data-Builder/creating-an-analytic-model-e5fbe9e.md)\)
    -   Task Chain \(see [Creating a Task Chain](../Acquiring-and-Preparing-Data-in-the-Data-Builder/creating-a-task-chain-d1afbc2.md)\)

    Other types of objects can only be deployed from their editors. If one or more objects that you have selected cannot be deployed, the *Deploy* dialog opens, allowing you to review your selection. Click *Deploy* to deploy those objects listed on the Deployable tab, or *Cancel* to go back and alter your selection.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Delete


    
    </td>
    <td valign="top">
    
    Delete the selected objects. Allows multi-selection. 

    > ### Note:  
    > -   If the object is used by one or more other objects then a dialog listing these dependencies opens, and the deletion is canceled.
    > -   If you want to delete a remote table whose data access is *Replicated \(Real-time\)*, you must ensure that the following requirements are met to allow a proper deletion:
    > 
    >     -   The data provisioning agent is not disconnected.
    > 
    >     -   The real-time replication is not paused at connection level and is working properly.
    > 
    >     If one of the requirement is not met, you must remove the replicated data first, before you can delete the remote table.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Share


    
    </td>
    <td valign="top">
    
    Share the selected objects to other spaces. Allows multi-selection from a single space. 

    For more information, see [Sharing Tables and Views To Other Spaces](sharing-tables-and-views-to-other-spaces-64b318f.md).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Copy


    
    </td>
    <td valign="top">
    
    Create a copy of the selected object in the same space. You must specify a new business and technical name. 


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Impact and Lineage Analysis


    
    </td>
    <td valign="top">
    
    Open the *Impact and Lineage Analysis* graph for the selected object. 

    For more information, see [Impact and Lineage Analysis](impact-and-lineage-analysis-9da4892.md).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Select Columns


    
    </td>
    <td valign="top">
    
    Open the *Columns* dialog to control the display of columns in the results table. 

    Modify the column list in any of the following ways, and then click *OK* to apply your changes:

    -   To select a column for display, select its checkbox. To hide a column deselect its checkbox.
    -   Click on a column token to highlight it and use the arrow buttons to move it in the list.
    -   Click *Reset* to go back to the default column display.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Sort


    
    </td>
    <td valign="top">
    
    Open the *Sort* dialog to control the ordering of the results table. 

    By default, the table is sorted by *Best Match on Top*, which calculates relevance on a range of criteria, including objects that you have recently changed, those that you have created, and those that have validation errors. To sort on a specific column, select a *Sort Order* and a *Sort By* column, and then click *OK* to apply them.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Display as...


    
    </td>
    <td valign="top">
    
    Set the presentation of the object list to *Table* \(default\), Grid, or List. 


    
    </td>
    </tr>
    </table>
    

