<!-- loio6f3ffbd077294cfaa6ae159f45d130b7 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Create a Geo-Coordinates Column

Create a geo-coordinates column to combine latitude and longitude values and output coordinate data that can be used in an SAP Analytics Cloud geo map.



## Context

You can create a geo coordinates only in a graphical view with a semantic usage of *Dimension*. To use the geo-coordinates column in SAP Analytics Cloud you must:

-   Create a view with a semantic usage of *Fact* and enable *Expose for Consumption*.
-   Create an association in your *Fact* that points to your *Dimension*.

When using the geo-coordinates column in an SAP Analytics Cloud geo map, the following types of layers are supported:

-   Bubble
-   Heat Map
-   Choropleth / Drill

-   Feature

-   Flow

For more information see [Creating a Geo Map in SAP Analytics Cloud](https://help.sap.com/viewer/00f68c2e08b941f081002fd3691d86a7/release/en-US/6ade40e98e9c4f11ab3ad28d345ab54f.html?q=adobe%20service).



## Procedure

1.  Ensure that the following properties are set correctly for your view output node:

    -    *Semantic Usage* - *Dimension* 
    -    *Expose for Consumption* - Enabled

2.  Select any object in your graphical view to display its context tools and click <span class="FPA-icons"></span> Calculated Columns.

    ![](images/Create_Column_Gif_0560169.gif)

    A calculated column node is created, its symbol is selected, and its properties are displayed in the side panel.

3.  Click <span class="FPA-icons"></span> \(Add New Calculated Column\) \> <span class="SAP-icons"></span> \(Geo-Coordinates Column\) to create a new geo-coordinates column.

    The new column properties are displayed in the side panel. The column is named *Location* by default.

4.  Complete the column's properties:


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
    
        Business Name


    
    </td>
    <td valign="top">
    
        Enter a descriptive name to help users identify the object. This name can be changed at any time.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        Technical Name


    
    </td>
    <td valign="top">
    
        Displays the name used in scripts and code, synchronized by default with the *Business Name*.

    To override the default technical name, enter a new one in the field. Technical names can contain only alphanumeric characters and underscores.

    > ### Note:  
    > Once the object is saved, the technical name can no longer be modified.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        Spatial Reference Identifier


    
    </td>
    <td valign="top">
    
        Every spatial reference system has an identifier called a *Spatial Reference Identifier* \(or *SRID*\). By default, it is set to *4326* but can be changed to *0* or *3857*. For more information, see [Spatial Reference Identifier on SAP HANA](https://help.sap.com/viewer/cbbbfc20871e4559abfd45a78ad58c02/2.0.02/en-US/7a2ea357787c101488ecd1b725836f07.html).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        Latitude and Longitude


    
    </td>
    <td valign="top">
    
        These columns must have string or double as data types.


    
    </td>
    </tr>
    </table>
    
5.  Click <span class="FPA-icons"></span> \(Save\) to save your entity:

    -   *Save* to save your object.
    -   *Save As* to create a local a copy of the object you're working on. The object must have been previously saved at least once. The *Save* dialog opens. Enter new business and technical names and click *Save*.

    Click <span class="SAP-icons"></span> \(Deploy\) to deploy your entity.

6.  Open a view that will point to your *Dimension* with an association and set its properties as follows:

    -   *Semantic Usage* - *Fact*
    -   *Expose for Consumption* - Enabled
    -   Create an association and point to your dimension.


