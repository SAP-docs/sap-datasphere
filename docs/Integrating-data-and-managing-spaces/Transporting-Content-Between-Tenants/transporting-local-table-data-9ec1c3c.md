<!-- loio9ec1c3ce2ec24c8f9ce330f075918cd5 -->

# Transporting Local Table Data

If your SAP Datasphere tenant is part of an SAP Business Data Cloud formation, you can include local table data in your package. This feature is intended to allow you to transport limited quantities of data for static and slowly changing dimensions, text entities, and relational datasets.

This topic contains the following sections:

-   [Enable Data Transport for a Local Table](transporting-local-table-data-9ec1c3c.md#loio9ec1c3ce2ec24c8f9ce330f075918cd5__enable)
-   [Export a Package Containing Local Table Data](transporting-local-table-data-9ec1c3c.md#loio9ec1c3ce2ec24c8f9ce330f075918cd5__export)
-   [Import a Package Containing Local Table Data](transporting-local-table-data-9ec1c3c.md#loio9ec1c3ce2ec24c8f9ce330f075918cd5__import)



<a name="loio9ec1c3ce2ec24c8f9ce330f075918cd5__enable"/>

## Enable Data Transport for a Local Table

In order to transport data in a local table:

-   Your SAP Datasphere tenant must be part of an SAP Business Data Cloud formation.
-   You must:
    -   Set the *Semantic Usage* to one of:
        -   *Dimension* - See [Create a Dimension to Categorize Data](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/5aae0e95361a4a4c964e69c52eada87d.html "Select a Semantic Usage of Dimension to indicate that your entity contains attributes that can be used to analyze and categorize measures defined in other entities.") :arrow_upper_right: or [Create a Fiscal Time Dimension](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/24248abea33c421bb6223becbfa6fb45.html "Select a Semantic Usage of Dimension and a Dimension Type of Fiscal Time to indicate that your entity contains attributes that can be used to analyze and categorize measures defined in other entities by fiscal time period.") :arrow_upper_right:.
        -   *Text* - See [Create a Text Entity for Attribute Translation](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/b25726df116b463e97435ba720e48ac9.html "Select a Semantic Usage of Text to indicate that your entity contains strings with language identifiers to translate text attributes in other entities.") :arrow_upper_right:.
        -   *Relational Dataset*

    -   Turn on the *Allow Data Transport* switch.




<a name="loio9ec1c3ce2ec24c8f9ce330f075918cd5__export"/>

## Export a Package Containing Local Table Data

To include local table data in a package:

1.  Open the *Transport* \> *Packages* editor and create your package as usual.

    > ### Note:  
    > You cannot transport local table data in a package created directly in the *Transport* \> *Export* editor.

2.  If the local table has the *Allow Data Transport* switch turned on, then an additional item, `<table_name>::data`, appears in the list of objects and you can select this item to include the data in your package.
3.  Once your package is complete and validated, click *Export*.

    A confirmation message is displayed. Click *OK* to confirm that you intend to transport the included data.


For general information about creating packages, see [Creating Packages to Export](creating-packages-to-export-24aba84.md).



<a name="loio9ec1c3ce2ec24c8f9ce330f075918cd5__import"/>

## Import a Package Containing Local Table Data

Import your package as usual, using the *Transport* \> *Import* editor. If the local table is created by the import \(or if it already exists but is empty\), the transported data will be imported to it.

For general information about importing packages, see [Importing Content from Another Tenant](importing-content-from-another-tenant-b607a12.md).

