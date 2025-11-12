<!-- loio4e45d4cb71404f52bd3cb01676f328e1 -->

# Enable Choropleth Layers for Geographical Visualizations

Choropleth maps display data such as population density, per capita income, or election results, by shading or coloring geographical areas in proportion to the value of that data. Users consuming data from SAP Datasphere may want to view it via a choropleth layer in SAP Analytics Cloud or other analytics clients.

This topic contains the following sections:

-   [Prerequisites](enable-choropleth-layers-for-geographical-visualizations-4e45d4c.md#loio4e45d4cb71404f52bd3cb01676f328e1__section_prerequisites)
-   [Install Default Choropleth Shapefile Data](enable-choropleth-layers-for-geographical-visualizations-4e45d4c.md#loio4e45d4cb71404f52bd3cb01676f328e1__section_default)
-   [Install Custom Choropleth Content](enable-choropleth-layers-for-geographical-visualizations-4e45d4c.md#loio4e45d4cb71404f52bd3cb01676f328e1__section_custom)
-   [Add Your Custom Choropleth Layers To a Hierarchy](enable-choropleth-layers-for-geographical-visualizations-4e45d4c.md#loio4e45d4cb71404f52bd3cb01676f328e1__section_hierarchy)
-   [Select Custom Choropleth Layers in SAP Analytics Cloud](enable-choropleth-layers-for-geographical-visualizations-4e45d4c.md#loio4e45d4cb71404f52bd3cb01676f328e1__section_consume)



<a name="loio4e45d4cb71404f52bd3cb01676f328e1__section_prerequisites"/>

## Prerequisites

To install default or custom choropleth shapefile data, you must have access to a database user and its Open SQL Schema \(see [Create a Database User](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/798e3fd6707940c3bd2219b2d1ebaac2.html "Users with a space administration role can create database users, granting them privileges to read from and/or write to an Open SQL schema with restricted access to the space schema.") :arrow_upper_right:\).



<a name="loio4e45d4cb71404f52bd3cb01676f328e1__section_default"/>

## Install Default Choropleth Shapefile Data

To allow users to work with choropleth layers, you must ensure that the default choropleth data is installed in SAP Datasphere.

> ### Note:  
> SAP Datasphere tenants provisioned up to and including version 2025.23 include default choropleth shapefile data. Tenants provisioned since then no longer include this data, but you can manually install it.

1.  Go to [https://me.sap.com/softwarecenter](https://me.sap.com/softwarecenter) and search for `DSP_GEO_DEFAULT_CONTENT.zip`.
2.  Download and unzip the file.
3.  Create an Open SQL Schema in any space in your SAP Datasphere tenant \(see [Create a Database User](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/798e3fd6707940c3bd2219b2d1ebaac2.html "Users with a space administration role can create database users, granting them privileges to read from and/or write to an Open SQL schema with restricted access to the space schema.") :arrow_upper_right:\).
4.  Open the SAP HANA Database Explorer and connect to your Open SQL Schema \(see [Connect to Your Open SQL Schema](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/b78ad208f8c4494489aabf97284679b6.html "When you have created a database user, you can connect to your Open SQL schema with the SAP HANA database explorer or with other tools.") :arrow_upper_right:\).
5.  Select your schema and open the *SQL Console*.
6.  From the downloaded zip file, copy the contents of `Create_Statements.sql` to the *SQL Console* and run it to create six tables.
7.  Open the `data` folder in your download and import each of the six csv files into its relevant table, specifying the pipe character \(`|`\) as separator:


    <table>
    <tr>
    <th valign="top">

    Table Name
    
    </th>
    <th valign="top">

    CSV Filename
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    `CHOROPLETH_CUSTOM_HIERARCHY`
    
    </td>
    <td valign="top">
    
    `DEFAULT_GEO_HIER.csv`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `SAMPLE.GEOGRAPHY_AREA`
    
    </td>
    <td valign="top">
    
    `SAMPLE_GEOGRAPHY_AREA.csv`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `SAMPLE.GEOGRAPHY_AREA_DESCRIPTION`
    
    </td>
    <td valign="top">
    
    `SAMPLE_GEOGRAPHY_AREA_DESCRIPTION.csv`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `SAMPLE.GEOGRAPHY_SHAPE`
    
    </td>
    <td valign="top">
    
    `SAMPLE_GEOGRAPHY_SHAPE.csv`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `SAMPLE.ISO_CODES`
    
    </td>
    <td valign="top">
    
    `SAMPLE_ISO_Codes.csv`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `SAMPLE.VERSION`
    
    </td>
    <td valign="top">
    
    `SAMPLE_VERSION.csv`
    
    </td>
    </tr>
    </table>
    
8.  From the unzipped downloaded files, copy the contents of `Expose_Content.sql` to the *SQL Console*.
9.  Edit the following line to add the name of your Open SQL schema:

    ```
    GRANT SELECT ON SCHEMA "<OpenSQLSchema>" TO "PUBLIC";
    ```

10. Run the script to make the imported data available to all spaces.

    Once this sharing step is complete, users consuming geographical data from any space can view it in the default choropleth hierarchy in SAP Analytics Cloud \(see [Add Choropleth Layers to Geo Maps](https://help.sap.com/docs/SAP_ANALYTICS_CLOUD/00f68c2e08b941f081002fd3691d86a7/5446d2beeb0b42029c225c27c2e482da.html) in the *SAP Analytics Cloud* documentation\).




<a name="loio4e45d4cb71404f52bd3cb01676f328e1__section_custom"/>

## Install Custom Choropleth Content

Some organizations need to visualize their geographical data using different area borders.

If default choropleth data is already installed in your SAP Datasphere \(see [Install Default Choropleth Shapefile Data](enable-choropleth-layers-for-geographical-visualizations-4e45d4c.md#loio4e45d4cb71404f52bd3cb01676f328e1__section_default)\), you can import additional shapefile data to provide further custom choropleth layers for use in visualizations.

1.  Obtain the custom shapefile data that you want to use, along with its Spatial Reference Identifier \(SRID\).

    In this example, we will import the [Regions \(December 2019\) Boundaries EN BUC](https://geoportal.statistics.gov.uk/datasets/ons::regions-december-2019-boundaries-en-buc/explore) shapefile layer available from the UK government Open Geography portal, which has the SRID `27700` \(`OSGB 1936 / British National Grid`\).

2.  In the SAP HANA Database Explorer, open your Open SQL Schema, expand the *Catalog* node, right-click the *Tables* node, click *Import Data*, and complete the wizard steps as follows:
    1.  Select *Import ESRI Shapefiles* and click *Step 2*.
    2.  Select your `.zip` file and click *Step 3*.
    3.  Select your Open SQL schema and click *Step 4*.
    4.  Enter the appropriate Spatial Reference Identifier \(SRID\)

        In our example, we enter the value `27700`, which represents `OSGB 1936 / British National Grid`.

    5.  Click *Import*.

        The import will create a table with the name of the shapefile in your schema and load the data into it.


3.  Select your schema and open the *SQL Console*.
4.  Copy the following code to the *SQL Console*, adapt it for your imported shapefile, and run it to convert the data into a format that SAP Analytics Cloud can read in a new table, *<Table\>*:

    ```
    CREATE COLUMN TABLE <Table> (ID INT PRIMARY KEY, NAME VARCHAR(100), SHAPE ST_GEOMETRY(3857), SHAPEPOINT ST_POINT(3857), IS_LEAF BOOLEAN);
     
    INSERT INTO <Table>
    SELECT
    ROW_NUMBER() Over () as "ID" ,
    "<NameColumn>" as "NAME",
    SHAPE.ST_SRID(3857).ST_Transform(3857) as SHAPE /* SAP Analytics Cloud requires SRID 3857 */, 
    SHAPE.ST_SRID(3857).ST_Transform(3857).ST_Centroid() as SHAPEPOINT,
    false AS IS_LEAF
    FROM "<ShapeFileName>";                                                 
    
    ```

    Complete the parameters as follows:


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *<Table\>*
    
    </td>
    <td valign="top">
    
    Enter the name of the table to create to contain your SAP Analytics Cloud-compatible choropleth data.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *<NameColumn\>*
    
    </td>
    <td valign="top">
    
    Enter the column containing your shapefile shape names.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *<ShapeFileName\>*
    
    </td>
    <td valign="top">
    
    Enter the name of your imported shapefile.
    
    </td>
    </tr>
    </table>
    
    In our example, we enter the following :

    ```
    CREATE COLUMN TABLE ENGLAND_L1 (ID INT PRIMARY KEY, NAME VARCHAR(100), SHAPE ST_GEOMETRY(3857), SHAPEPOINT ST_POINT(3857), IS_LEAF BOOLEAN);
     
    INSERT INTO ENGLAND_L1
    SELECT
    ROW_NUMBER() Over () as "ID" ,
    "rgn19nm" as "NAME",
    SHAPE.ST_SRID(3857).ST_Transform(3857) as SHAPE /* SAP Analytics Cloud requires SRID 3857 */, 
    SHAPE.ST_SRID(3857).ST_Transform(3857).ST_Centroid() as SHAPEPOINT,
    false AS IS_LEAF
    FROM "Regions__December_2019__Boundaries_EN_BUC";                                                 
    
    ```

    You can install additional custom layers as necessary.

    Before you can access your custom layers in SAP Analytics Cloud, you must add them to a hierarchy.




<a name="loio4e45d4cb71404f52bd3cb01676f328e1__section_hierarchy"/>

## Add Your Custom Choropleth Layers To a Hierarchy

To make your custom choropleth layers available in SAP Analytics Cloud, you must create a new hierarchy for them. These hierarchies are selected in SAP Analytics Cloud and allow you to drill up and down through layers.

Copy the following code to the *SQL Console*, adapt it for your layer, and run it:

```

INSERT INTO "sap.fpa.services.spatial::custom_hierarchy.CHOROPLETH_CUSTOM_HIERARCHY" VALUES(
'<HierarchyName>', <HierarchyID>,'<NameColumn>','name',<LayerID>,<LayerLevel>,'<LayerName>','SHAPE','<TableName>','','<SPACE#DBUSER>',0);
```

Complete the parameters as follows:


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*<HierarchyName\>*

</td>
<td valign="top">

Enter the hierarchy name to be shown in SAP Analytics Cloud.

</td>
</tr>
<tr>
<td valign="top">

*<HierarchyID\>*

</td>
<td valign="top">

Enter a unique ID. The default choropleth layer has ID 1.

</td>
</tr>
<tr>
<td valign="top">

*<NameColumn\>*

</td>
<td valign="top">

Enter `NAME` \(or `AREA_NAME` when reusing a default layer\).

</td>
</tr>
<tr>
<td valign="top">

*<LayerID\>*

</td>
<td valign="top">

Enter a unique ID for the shape or layer. The default choropleth layers have IDs 1-5.

</td>
</tr>
<tr>
<td valign="top">

*<LayerLevel\>*

</td>
<td valign="top">

Enter the level of the layer in the hierarchy in the form <code><i class="varname">&lt;n&gt;</i></code> or <code><i class="varname">&lt;n&gt;</i>.<i class="varname">&lt;n&gt;</i></code>.

</td>
</tr>
<tr>
<td valign="top">

*<LayerName\>*

</td>
<td valign="top">

Enter the layer name to be shown in SAP Analytics Cloud.

</td>
</tr>
<tr>
<td valign="top">

*<TableName\>*

</td>
<td valign="top">

Enter the name of the table containing your custom layer \(or `SAC_CHOROPLETH_DATA` when reusing a default layer\).

</td>
</tr>
<tr>
<td valign="top">

*<SPACE\#DBUSER\>*

</td>
<td valign="top">

Enter your Open SQL schema name \(or `PUBLIC` when reusing a default layer\).

</td>
</tr>
</table>

In this example, we create a single-level hierarchy with name `English Regions` and ID: `2`, and insert our imported custom layer with name `English Region`, ID: `6`, and level `1`:

```
 
INSERT INTO "sap.fpa.services.spatial::custom_hierarchy.CHOROPLETH_CUSTOM_HIERARCHY" VALUES(
'English Regions',2,'NAME','name',6,1,'English Region','SHAPE','ENGLAND_L1','','MYSPACE#MYUSER','0');
```

Your new hierarchy can reuse default layers if appropriate. In this example, we create a three-layer hierarchy with name `Country - English Regions` and ID: `3`, and insert two default layers before placing our imported custom layer at level `3`:

```
 
INSERT INTO "sap.fpa.services.spatial::custom_hierarchy.CHOROPLETH_CUSTOM_HIERARCHY" VALUES(
'Country - English Regions',3,'AREA_NAME','name',7,1,'Country','SHAPE','SAC_CHOROPLETH_DATA','','PUBLIC','0');
 
INSERT INTO "sap.fpa.services.spatial::custom_hierarchy.CHOROPLETH_CUSTOM_HIERARCHY" VALUES(
'Country - English Regions',3,'AREA_NAME','name',8,2,'Region','SHAPE','SAC_CHOROPLETH_DATA','','PUBLIC','0');
 
INSERT INTO "sap.fpa.services.spatial::custom_hierarchy.CHOROPLETH_CUSTOM_HIERARCHY" VALUES(
'Country - English Regions',3,'NAME','name',9,3,'English Region','SHAPE','ENGLAND_L1','','MYSPACE#MYUSER','0');
```



<a name="loio4e45d4cb71404f52bd3cb01676f328e1__section_consume"/>

## Select Custom Choropleth Layers in SAP Analytics Cloud

To make standard or custom choropleth layers available in SAP Analytics Cloud:

-   In SAP Datasphere, a modeler must include geographical data in a dimension \(see [Create a Geo-Coordinates Column in a Graphical View](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/6f3ffbd077294cfaa6ae159f45d130b7.html "Create a geo-coordinates column to combine latitude and longitude values and output coordinate data that can be used in an SAP Analytics Cloud geo map.") :arrow_upper_right:\).
-   In SAP Analytics Cloud, an analyst must add a *Geo Map* widget to the story and set the following properties for it:


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Content Layers
    
    </td>
    <td valign="top">
    
    Click *Add Layer*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Layer Type
    
    </td>
    <td valign="top">
    
    Select *Choropleth/Drill*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Layer Style
    
    </td>
    <td valign="top">
    
    Select *Shape \(Choropleth\)*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Location Dimension
    
    </td>
    <td valign="top">
    
    Select the location dimension, and then click the *Hierarchy* button and choose the standard or a custom layer from the list.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Choropleth Color
    
    </td>
    <td valign="top">
    
    Select a measure, calculation or measure input control.
    
    </td>
    </tr>
    </table>
    
    For more information, see [Add Choropleth Layers to Geo Maps](https://help.sap.com/docs/SAP_ANALYTICS_CLOUD/00f68c2e08b941f081002fd3691d86a7/5446d2beeb0b42029c225c27c2e482da.html) in the *SAP Analytics Cloud* documentation.


