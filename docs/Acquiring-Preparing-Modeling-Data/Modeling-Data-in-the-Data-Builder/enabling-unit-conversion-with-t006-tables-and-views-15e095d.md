<!-- loio15e095db68f04876a799b34fb66fc635 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Enabling Unit Conversion with T006\* Tables and Views

Create unit conversion views and the necessary supporting objects based on an SAP connection, tables shared from another space, or manually.



## Context

To enable unit conversion, you create the necessary objects in your space.

-   You can create unit conversion local tables and views and then manually add and maintain currency conversion data.

-   You can import unit conversion objects and data from these SAP connections: SAP S/4 HANA Cloud, SAP S/4 HANA On-Premise and SAP ABAP.

-   You can use the unit conversion tables shared from another space.


Once the objects are created, you will be able to convert unit values into another unit using a conversion measure for units in an analytic model. See [Create a Conversion Measure for Units](create-a-conversion-measure-for-units-965ce56.md).



## Procedure

1.  In the side navigation area, choose <span class="FPA-icons-V3"></span> \(*Data Builder*\), select a space if necessary, and choose +, then *Unit Conversion Views*. The *Unit Conversion Views* dialog opens.

    > ### Note:  
    > You can also access the *Unit Conversion Views* dialog from the *Repository Explorer*.

2.  In the *Source* dropdown list, the local connections \(of type SAP S/4 HANA Cloud, SAP S/4 HANA On-Premise, SAP ABAP\) that are in your space are displayed. Also, if the TCUR\* tables of another space have been shared to your space, the name of the space is displayed in the list. Select one of the following:

    -   *Manual* - Local tables and views will be created and you will then need to enter or import the data.
    -   An SAP S/4 HANA Cloud or SAP S/4 HANA On-Premise connection - Local tables, views and data flows will be imported.
    -   An SAP ABAP connection - Local tables, views, data flows and remote tables will be imported.
    -   A space name - Views will be created. Data is read from the shared local currency conversion tables that views are based on.

    You can see that the objects listed below will be generated for each object type: local tables \(unless the tables are shared from another space\), views, and, depending on the connection you've selected, data flows and remote tables:

    -   `SAP.UNIT.TABLE.T006` - units of measurement table
    -   `SAP.UNIT.TABLE.T006D` - units of measurement dimensions table
    -   `SAP.UNIT.TABLE.T006A` - units of measurement annotation table

3.  If needed, rename the business names of each object.

4.  Choose *Create*. The creation process runs in the background and you can keep working in SAP Datasphere. You’re notified when the creation of the objects has been completed.

5.  Once the creation of the objects is finished, do one of the following:

    -   If you've chosen *Manual*, local tables and views have been created and you now need to enter unit conversion data manually or for example import the data from a CSV file in a local table.

    -   If you've chosen a connection as a source, local tables, views, data flows and - for an SAP ABAP connection - remote tables have been created. You now need to run the data flows to fill the tables with data. See  <?sap-ot O2O class="- topic/xref " href="5b591d4998fa4a148750016a29ada91e.xml" text="" desc="" xtrc="xref:2" xtrf="file:/home/builder/src/dita-all/znj1755614851492/loioc25299a38b6448f889a43b42c9e5897d_en-US/src/content/localization/en-us/15e095db68f04876a799b34fb66fc635.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> .

    -   If you've chosen a space as a source, views have been created and data is read from the tables.


    You can now use these tables to convert unit values into another unit using a conversion measure for units in an analytic model.


**Share Unit Conversion Tables to Other Spaces**

6.  In the side navigation area, choose <span class="FPA-icons-V3"></span> \(*Data Builder*\), select a space if necessary, and choose +, then *Unit Conversion Views*. The *Unit Conversion Views* dialog opens.

7.  Choose *Share*.

    > ### Note:  
    > If the unit conversion objects have not been created for your space, the *Share* button is disabled.

8.  In the dialog box that opens, enter or select the spaces to which you want to share the T006\*\* unit conversion tables and click *Share*.

    > ### Note:  
    > If the T006\* tables have been shared to your space, you must still use the *Unit Conversion Views* dialog to create local T006\* views, before you can do unit conversion.


<a name="task_fjj_j5m_nfc"/>

<!-- task\_fjj\_j5m\_nfc -->

## Share Unit Conversion Tables to Other Spaces

Once you’ve created the unit conversion objects in your space, you can share the T006\* tables to other spaces.



<a name="task_fjj_j5m_nfc__context_gjj_j5m_nfc"/>

## Context

The spaces to which you share these tables can then use them as a source to generate their own T006\* views with the dialog.



## Procedure

1.  In the side navigation area, choose <span class="FPA-icons-V3"></span> \(*Data Builder*\), select a space if necessary, and choose +, then *Unit Conversion Views*. The *Unit Conversion Views* dialog opens.

2.  Choose *Share*.

    > ### Note:  
    > If the unit conversion objects have not been created for your space, the *Share* button is disabled.

3.  In the dialog box that opens, enter or select the spaces to which you want to share the T006\*\* unit conversion tables and click *Share*.

    > ### Note:  
    > If the T006\* tables have been shared to your space, you must still use the *Unit Conversion Views* dialog to create local T006\* views, before you can do unit conversion.


