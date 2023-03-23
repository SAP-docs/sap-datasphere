<!-- loio845fedbd28574aa8b84239df848936f6 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Import Entities from SAP S/4HANA Cloud

You can import existing entities from SAP S/4HANA Cloud into SAP Datasphere in order to build new models on top of them or enhance them.



<a name="loio845fedbd28574aa8b84239df848936f6__prereq_itn_tcy_xrb"/>

## Prerequisites

Make sure that model import is enabled for the SAP S/4HANA Cloud connection type. For more information, see [SAP S/4HANA Cloud](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/internal/en-US/a98e5ffdf47c44d9a845dca01a18bd82.html "Use the connection to access or import extraction-enabled ABAP Core Data Services views (ABAP CDS views) from SAP S/4HANA Cloud.") :arrow_upper_right:.

The communication scenarios SAP\_COM\_0531, SAP\_COM\_0532, SAP\_COM\_0722 need to be active. For more information, see

-   [Integrating CDS Views Using ABAP CDS Pipeline](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/2111.501/en-US/f509eddda867452db9631dae1ae442a3.html)
-   [Integrating CDI](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/2111.501/en-US/4a006b43551d4cb5aed6399c0ace6b98.html)
-   [Integrating SAP Data Warehouse Cloud](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/2111.501/en-US/8b0662cbc94940b98d8bb6f0696ccfa4.html?q=SAP_COM_0722)

in the SAP S/4HANA Cloud documentation.



## Context

The import of entities enables you to re-use existing metadata and data from SAP S/4HANA Cloud so that you can include this metadata and data in SAP Datasphere without having to rebuild them manually. The format of the metadata of these entities are transformed in the process to the definition of entities known in SAP Datasphere.

With the import, objects are generated in the Business Builder and the Data Builder. Through these objects, data access to the source systems is realized. The data is retrieved directly from the source systems via remote tables.

You can then use these models as they are or enhance the data in SAP Datasphere on each level of your model - for example by adding master data to a view of type dimension.



## Procedure

1.  In the side navigation area, click *Data Builder*. Select a space if necessary.

2.  Choose <span class="FPA-icons"></span> \(Import\) ** \> *Import Entities*.

3.  In the *Import Wizard*, select the connection type that you would like to use. Choose *Next Step*.

4.  Select the target space. Choose *Next Step*.

5.  Select the connection. Choose *Next Step*. The system will show you all available entities.

6.  You can filter the entities by application component, modeling pattern, contract, and software component. For more information, see [Supported Capabilities for CDS Views](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/6a6ff32b25dd473080e6aeddbefecfca.html) and [Stability Contracts for CDS Views](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/2e4edbede2f94fb7b7f6eac856c02b19.html).

7.  Select the entity that you would like to import. Choose *Next Step*.

8.  You will get a list of objects which will be generated. When re-importing a model, changes in the column defintions of source entities that generate remote tables will automatically result in updating and redeploying the remote tables.

    > ### Note:  
    > If an associated entity cannot be imported, it is left out. The generated object however will still be a complete object.

9.  Choose *Import and Deploy*.

    > ### Note:  
    > The system will generate notifications about the import process.
    > 
    > If the import was successful, the generated objects will appear in the Business Builder and Data Builder.


