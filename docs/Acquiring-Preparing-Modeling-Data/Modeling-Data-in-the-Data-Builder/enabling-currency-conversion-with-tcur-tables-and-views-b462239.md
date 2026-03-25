<!-- loiob462239ffb644d9baab4442a10a72edf -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Enabling Currency Conversion with TCUR\* Tables and Views

Create currency conversion views and the necessary supporting objects based on an SAP connection, tables shared from another space, or manually.

To enable currency conversion, you create the necessary objects in your space.

-   You can create currency conversion local tables and views and then manually add and maintain currency conversion data.

-   You can import currency conversion objects and data from these SAP connections: SAP S/4 HANA Cloud, SAP S/4 HANA On-Premise and SAP ABAP.

-   You can use the currency conversion tables shared from another space.


Once the objects are created, you will be able to convert currency values into another currency using a currency conversion column in a graphical view or an SQL view. See [Create a Currency Conversion Column in a Graphical View](../create-a-currency-conversion-column-in-a-graphical-view-6e3d8be.md).



<a name="loiob462239ffb644d9baab4442a10a72edf__section_x5w_m31_mvb"/>

## Create Currency Conversion Objects

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Data Builder*\), select a space if necessary, and click +, then *Currency Conversion Views*. The *Currency Conversion Views* dialog opens.

    > ### Note:  
    > You can also access the *Currency Conversion Views* dialog from the *Repository Explorer*.

2.  In the *Source* dropdown list, the local connections \(of type SAP S/4 HANA Cloud, SAP S/4 HANA On-Premise, SAP ABAP\) that are in your space are displayed. Also, if the TCUR\* tables of another space have been shared to your space, the name of the space is displayed in the list. Select one of the following:

    -   *Manual* - Local tables and views will be created and you will then need to enter or import the data.
    -   An SAP S/4 HANA Cloud or SAP S/4 HANA On-Premise connection - Local tables, views and data flows will be imported.
    -   An SAP ABAP connection - Local tables, views, data flows and remote tables will be imported.
    -   A space name - Views will be created. Data is read from the shared local currency conversion tables that views are based on.

    The objects listed below will be generated for each object type: local tables \(unless the tables are shared from another space\), views, and, depending on the connection you've selected, data flows and remote tables:


    <table>
    <tr>
    <th valign="top">

    Table
    
    </th>
    <th valign="top">

    View
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Currency Codes / `SAP.CURRENCY.TABLE.TCURC`
    
    </td>
    <td valign="top">
    
    Currency Codes View / `SAP.CURRENCY.VIEW.TCURC`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Conversion Factors / `SAP.CURRENCY.TABLE.TCURF`
    
    </td>
    <td valign="top">
    
    Conversion Factors View / `SAP.CURRENCY.VIEW.TCURF`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Quotations / `SAP.CURRENCY.TABLE.TCURN`
    
    </td>
    <td valign="top">
    
    Quotations View / `SAP.CURRENCY.VIEW.TCURN`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Exchange Rates / `SAP.CURRENCY.TABLE.TCURR`
    
    </td>
    <td valign="top">
    
    Exchange Rates View / `SAP.CURRENCY.VIEW.TCURR`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Currency Text / `SAP.CURRENCY.TABLE.TCURT`
    
    </td>
    <td valign="top">
    
    Currency Text View / `SAP.CURRENCY.VIEW.TCURT`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Exchange Rate Types / `SAP.CURRENCY.TABLE.TCURV`
    
    </td>
    <td valign="top">
    
    Exchange Rate Types View / `SAP.CURRENCY.VIEW.TCURV`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Exchange Rate Type Text / `SAP.CURRENCY.TABLE.TCURW`
    
    </td>
    <td valign="top">
    
    Exchange Rate Type Text View / `SAP.CURRENCY.VIEW.TCURW`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Decimal Places in Currencies / `SAP.CURRENCY.TABLE.TCURX`
    
    </td>
    <td valign="top">
    
    Decimal Places in Currencies View / `SAP.CURRENCY.VIEW.TCURX`
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > You can use these same entities with a `CONVERT_CURRENCY` function in a standard calculated column or in an SQL view \(see [CONVERT\_CURRENCY](https://help.sap.com/viewer/7c78579ce9b14a669c1f3295b0d8ca16/Cloud/en-US/d22d746ed2951014bb7fb0114ffdaf96.html) in the *SAP HANA* documentation\).

3.  If needed, rename the business names of each object.
4.  Click *Create*.

    The creation process runs in the background and you can keep working in SAP Datasphere. You’re notified when the creation of the objects has been completed.

5.  Once the creation of the objects is finished, do one of the following:
    -   If you've chosen *Manual*, local tables and views have been created and you now need to enter currency conversion data manually or for example import the data from a CSV file in a local table.

    -   If you've chosen a connection as a source, local tables, views, data flows and - for an SAP ABAP connection - remote tables have been created. You now need to run the data flows to fill the tables with data. See [Run a Data Flow](../Acquiring-and-Preparing-Data-in-the-Data-Builder/run-a-data-flow-20e5be3.md).

    -   If you've chosen a space as a source, views have been created and data is read from the tables.



Next steps: Now that the necessary objects are created, you can convert currency values into another currency using a currency conversion column in a graphical view. See [Create a Currency Conversion Column in a Graphical View](../create-a-currency-conversion-column-in-a-graphical-view-6e3d8be.md).



<a name="loiob462239ffb644d9baab4442a10a72edf__section_ejj_pk1_mvb"/>

## Share Currency Conversion Tables to Other Spaces

Once you’ve created the currency conversion objects in your space, you can share the TCUR\* tables to other spaces. The spaces to which you share these tables can then use them as a source to generate their own TCUR\* views with the dialog.

> ### Note:  
> As a general rule, you can share objects \(including TCUR\* tables\) to another space by following another procedure. For more information, see [Sharing Entities and Task Chains to Other Spaces](../Creating-Finding-Sharing-Objects/sharing-entities-and-task-chains-to-other-spaces-64b318f.md)

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Data Builder*\), select a space if necessary, and click +, then *Currency Conversion Views*. The *Currency Conversion Views* dialog opens.
2.  Click *Share*.

    > ### Note:  
    > If the currency conversion objects have not been created for your space, the *Share* button is disabled.

3.  In the dialog box that opens, enter or select the spaces to which you want to share the TCUR\* currency conversion tables and click *Share*.

> ### Note:  
> If the TCUR\* tables have been shared to your space, you must still follow the steps at the [Create Currency Conversion Objects](enabling-currency-conversion-with-tcur-tables-and-views-b462239.md#loiob462239ffb644d9baab4442a10a72edf__section_x5w_m31_mvb) and in the *Source* dropdown list, select the name of the space the tables are shared from.

