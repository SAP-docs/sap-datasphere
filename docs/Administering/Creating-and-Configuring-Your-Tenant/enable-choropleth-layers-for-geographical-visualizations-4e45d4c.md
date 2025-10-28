<!-- loio4e45d4cb71404f52bd3cb01676f328e1 -->

# Enable Choropleth Layers for Geographical Visualizations

Choropleth maps display data such as population density, per capita income, or election results, by shading or coloring geographical areas in proportion to the value of that data. Users consuming data from SAP Datasphere may want to view it via a choropleth layer in SAP Analytics Cloud or other analytics clients.

This topic contains the following sections:

-   [Prerequisites](enable-choropleth-layers-for-geographical-visualizations-4e45d4c.md#loio4e45d4cb71404f52bd3cb01676f328e1__section_prerequisites)
-   [Install Default Choropleth Shapefile Data](enable-choropleth-layers-for-geographical-visualizations-4e45d4c.md#loio4e45d4cb71404f52bd3cb01676f328e1__section_default)
-   [Install Custom Choropleth Content](enable-choropleth-layers-for-geographical-visualizations-4e45d4c.md#loio4e45d4cb71404f52bd3cb01676f328e1__section_custom)
-   [Select Custom Choropleth Layers in SAP Analytics Cloud](enable-choropleth-layers-for-geographical-visualizations-4e45d4c.md#loio4e45d4cb71404f52bd3cb01676f328e1__section_consume)



<a name="loio4e45d4cb71404f52bd3cb01676f328e1__section_prerequisites"/>

## Prerequisites

To install default or custom choropleth shapefile data, you must have access to a database user and their Open SQL Schema \(see [Create a Database User](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/798e3fd6707940c3bd2219b2d1ebaac2.html "Users with a space administration role can create database users, granting them privileges to read from and/or write to an Open SQL schema with restricted access to the space schema.") :arrow_upper_right:\).



<a name="loio4e45d4cb71404f52bd3cb01676f328e1__section_default"/>

## Install Default Choropleth Shapefile Data

To allow users to work with choropleth layers, you must ensure that the default choropleth data is installed in SAP Datasphere

> ### Note:  
> SAP Datasphere tenants provisioned up to and including version 2025.23 include default choropleth shapefile data. Tenants provisioned since then no longer include this data, but you can manually install it.

1.  Go to [https://me.sap.com/softwarecenter](https://me.sap.com/softwarecenter) and search for `DSP_GEO_DEFAULT_CONTENT.zip`.
2.  Download and unzip the file.
3.  Create an Open SQL Schema in any space in your SAP Datasphere tenant \(see [Create a Database User](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/798e3fd6707940c3bd2219b2d1ebaac2.html "Users with a space administration role can create database users, granting them privileges to read from and/or write to an Open SQL schema with restricted access to the space schema.") :arrow_upper_right:\).
4.  Open the SAP HANA Database Explorer and connect to your Open SQL Schema \(see [Connect to Your Open SQL Schema](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/b78ad208f8c4494489aabf97284679b6.html "When you have created a database user, you can connect to your Open SQL schema with the SAP HANA database explorer or with other tools.") :arrow_upper_right:\).
5.  Select your schema and open the *SQL Console*.
6.  From the downloaded zip file, copy the contents of `Create_Statements.sql` to the *SQL Console* and run it to create six tables.
7.  Open the `data` folder in your download and import each of the six csv files into its relevant table.


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
9.  Edit line 4 to add the name of your Open SQL schema, and run the script to make the imported data available to all spaces.

    Once this sharing step is complete, users consuming geographical data from any space can view it in the default choropleth layer in SAP Analytics Cloud \(see [Add Choropleth Layers to Geo Maps](https://help.sap.com/docs/SAP_ANALYTICS_CLOUD/00f68c2e08b941f081002fd3691d86a7/5446d2beeb0b42029c225c27c2e482da.html) in the *SAP Analytics Cloud* documentation\).




<a name="loio4e45d4cb71404f52bd3cb01676f328e1__section_custom"/>

## Install Custom Choropleth Content

Some organizations need to visualize their geographical data using different area borders.

If default choropleth data is already installed in your SAP Datasphere \(see [Install Default Choropleth Shapefile Data](enable-choropleth-layers-for-geographical-visualizations-4e45d4c.md#loio4e45d4cb71404f52bd3cb01676f328e1__section_default)\), you can import additional shapefile data to provide further custom choropleth layers for use in visualizations.

1.  Obtain the custom shapefile data that you want to use, along with its Spatial Reference Identifier \(SRID\).

    In this example, we will import the [Regions \(December 2019\) Boundaries EN BUC](https://geoportal.statistics.gov.uk/datasets/ons::regions-december-2019-boundaries-en-buc/explore) shapefile layer available from the UK government Open Geography portal, which has the SRID `27700` \(`OSGB 1936 / British National Grid`\).

2.  In the SAP HANA Database Explorer, open your Open SQL Schema, expand the *Catalog* node, right-click the *Tables* node, click *Import Data*, and complete the wizard steps as follows:
    1.  Select *Import ESRI* and click *Step 2*.
    2.  Select your `.zip` file and click *Step 3*.
    3.  Select your Open SQL schema and click *Step 4*.
    4.  Enter the appropriate Spatial Reference Identifier \(SRID\) and click *Import*.

        In our example, we enter the value `27700`.


3.  Select your schema and open the *SQL Console*.
4.  Copy the following code to the *SQL Console*, adapt it for your imported shapefile data, and run it:

    ```
    CREATE COLUMN TABLE <TableName> (ID INT PRIMARY KEY, NAME VARCHAR(100), SHAPE ST_GEOMETRY(3857), SHAPEPOINT ST_POINT(3857), IS_LEAF BOOLEAN);
     
    INSERT INTO <TableName>
    SELECT
    ROW_NUMBER() Over () as "ID" ,
    "<ColumnName>" as "NAME"                                                /* Enter the column containing the names of shapes */,
    SHAPE.ST_SRID(3857).ST_Transform(3857) as SHAPE                       /* Do not modify. SRID 3857 is required for SAP Analytics Cloud */,
    SHAPE.ST_SRID(3857).ST_Transform(3857).ST_Centroid() as SHAPEPOINT    /* Do not modify. SRID 3857 is required for SAP Analytics Cloud */,
    false AS IS_LEAF
    FROM "<ShapeFileName>";                                                 
    
     
    INSERT INTO "sap.dsp.services.spatial::custom_hierarchy.CHOROPLETH_CUSTOM_HIERARCHY" VALUES(
    '<HierarchyName>'                 /* NAME: Enter the hierarchy name to be shown in SAP Analytics Cloud */,
    2                              /* HIERARCHYID: Enter a unique ID. The default choropleth layer has ID 1 */,
    'NAME'                          /* COLUMN: Do not modify. Uses the NAME column in the table created above */,
    'name'                          /* COLUMNLABEL: Do not modify */,
    6                               /* ID: Enter a unique ID for the shape or layer. The default choropleth layers have IDs 1-5  */,
    1                               /* LEVEL: Do not modify. Indicates the level of the layer in the hierarchy */,
    '<LevelName>'     /* LNAME: Enter the layer name to be shown in SAP Analytics Cloud */,
    'SHAPE'                         /* LOCATION: Do not modify. Uses the SHAPE column in the table created above */,
    '<TableName>'                    /* OBJECT:Enter the name of the table storing shapefile data */,
    ''                              /* PACKAGE: Not Used */,
    '<SPACE#DBUSER>'                  /* SCHEMA: Enter your Open SQL schema name */,
    '0'                             /* DEFAULT: Do not modify. 0 indicates a custom region and 1 is for SAP supplied conent */;
    ```

    In our example, we enter the following :

    ```
    CREATE COLUMN TABLE ENGLAND_L1 (ID INT PRIMARY KEY, NAME VARCHAR(100), SHAPE ST_GEOMETRY(3857), SHAPEPOINT ST_POINT(3857), IS_LEAF BOOLEAN);
     
    INSERT INTO ENGLAND_L1
    SELECT
    ROW_NUMBER() Over () as "ID" ,
    "rgn19nm" as "NAME"                                                /* Enter the column containing the names of shapes */,
    SHAPE.ST_SRID(3857).ST_Transform(3857) as SHAPE                       /* Do not modify. SRID 3857 is required for SAP Analytics Cloud */,
    SHAPE.ST_SRID(3857).ST_Transform(3857).ST_Centroid() as SHAPEPOINT    /* Do not modify. SRID 3857 is required for SAP Analytics Cloud */,
    false AS IS_LEAF
    FROM "Regions__December_2019__Boundaries_EN_BUC";                                                 
    
     
    INSERT INTO "sap.dsp.services.spatial::custom_hierarchy.CHOROPLETH_CUSTOM_HIERARCHY" VALUES(
    'English Regions'                 /* NAME: Enter the hierarchy name to be shown in SAP Analytics Cloud */,
    2                              /* HIERARCHYID: Enter a unique ID. The default choropleth layer has ID 1 */,
    'NAME'                          /* COLUMN: Do not modify. Uses the NAME column in the table created above */,
    'name'                          /* COLUMNLABEL: Do not modify */,
    6                               /* ID: Enter a unique ID for the shape or layer. The default choropleth layers have IDs 1-5  */,
    1                               /* LEVEL: Do not modify. Indicates the level of the layer in the hierarchy */,
    'English Region'     /* LNAME: Enter the layer name to be shown in SAP Analytics Cloud */,
    'SHAPE'                         /* LOCATION: Do not modify. Uses the SHAPE column in the table created above */,
    'ENGLAND_L1'                    /* OBJECT:Enter the name of the table storing shapefile data */,
    ''                              /* PACKAGE: Not Used */,
    'SPACE#DBUSER'                  /* SCHEMA: Enter your Open SQL schema name */,
    '0'                             /* DEFAULT: Do not modify. 0 indicates a custom region and 1 is for SAP supplied conent */;
    ```

    Once this step is complete, users consuming geographical data from any space can select the imported custom choropleth layer in SAP Analytics Cloud.

    You can, optionally, add further custom layers as necessary.




<a name="loio4e45d4cb71404f52bd3cb01676f328e1__section_consume"/>

## Select Custom Choropleth Layers in SAP Analytics Cloud

To make standard or custom choropleth layers available in SAP Analytics Cloud:

-   In SAP Datasphere, a modeler must include geographical data in a dimension \(see [Create a Geo-Coordinates Column in a Graphical View](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/6f3ffbd077294cfaa6ae159f45d130b7.html "Create a geo-coordinates column to combine latitude and longitude values and output coordinate data that can be used in an SAP Analytics Cloud geo map.") :arrow_upper_right:\).
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


