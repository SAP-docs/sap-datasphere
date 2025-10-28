<!-- loio6f3ffbd077294cfaa6ae159f45d130b7 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Create a Geo-Coordinates Column in a Graphical View

Create a geo-coordinates column to combine latitude and longitude values and output coordinate data that can be used in an SAP Analytics Cloud geo map.



## Context

When using the geo-coordinates column in an SAP Analytics Cloud geo map, the following types of layers are supported:

-   Bubble
-   Heat Map
-   Choropleth / Drill
-   Feature
-   Flow

For more information see [Creating a Geo Map in SAP Analytics Cloud](https://help.sap.com/viewer/00f68c2e08b941f081002fd3691d86a7/release/en-US/6ade40e98e9c4f11ab3ad28d345ab54f.html?q=adobe%20service).



## Procedure

1.  Create your graphical view and set its semantic usage to *Dimension*.

2.  Select an appropriate node in the diagram to display its context tools and click <span class="FPA-icons-V3"></span> Calculated Columns.

    ![](images/Create_Column_Gif_0560169.gif)

    A calculated column node is created, its symbol is selected, and its properties are displayed in the side panel.

3.  Click <span class="FPA-icons-V3"></span> \(Add New Calculated Column\) \> <span class="SAP-icons-V5"></span> \(Geo-Coordinates Column\) to create a new geo-coordinates column.

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
    
5.  Click <span class="FPA-icons-V3"></span> \(Save\)** \> *Save* to save your entity or click <span class="SAP-icons-V5"></span> \(Deploy\) to save and deploy it immediately.

    For more information, see [Saving and Deploying Objects](saving-and-deploying-objects-7c0b560.md).




<a name="loio6f3ffbd077294cfaa6ae159f45d130b7__result_u2w_ky1_xgc"/>

## Results

To use the geo-coordinates column in SAP Analytics Cloud you should now:

-   Create a view with a semantic usage of *Fact* \(see [Create a Fact to Contain Measurable Data](Modeling-Data-in-the-Data-Builder/create-a-fact-to-contain-measurable-data-30089bd.md)\).
-   Create an association in your *Fact* that points to your *Dimension* \(see [Create an Association to Define a Semantic Relationship Between Entities](Modeling-Data-in-the-Data-Builder/create-an-association-to-define-a-semantic-relationship-between-entities-66c6998.md)\).
-   Use the *Fact* as a fact source in an analytic model \(see [Add a Fact to an Analytic Model](Modeling-Data-in-the-Data-Builder/add-a-fact-to-an-analytic-model-27075ee.md)\).
-   Consume the analytic model in SAP Analytics Cloud \(see [Consume Data in SAP Analytics Cloud via a Live Connection](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/a2c5486c03174620be9de3c8c769ce54.html "You can create a live connection from SAP Analytics Cloud to SAP Datasphere and consume data exposed as analytic models and perspectives to create stories and analytic applications.") :arrow_upper_right:\).

