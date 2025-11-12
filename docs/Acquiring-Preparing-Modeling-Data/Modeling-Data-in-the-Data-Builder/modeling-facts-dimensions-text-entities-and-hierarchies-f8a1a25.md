<!-- loiof8a1a25c50c14fd8b4439132a793de4c -->

# Modeling Facts, Dimensions, Text Entities, and Hierarchies

You can enrich your entities with semantic information to make your data ready for analysis.



<a name="loiof8a1a25c50c14fd8b4439132a793de4c__section_znc_vwt_zgc"/>

## Prerequisites

To enrich your entities with semantic information in the *Data Builder*, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.
-   *Data Warehouse Data Builder* \(`CRUD----`\) - To create, edit and delete *Data Builder* objects.

The *DW Modeler* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 



<a name="loiof8a1a25c50c14fd8b4439132a793de4c__section_vf5_rwt_zgc"/>

## Introduction to Modeling Facts, Dimensions, Text Entities, and Hierarchies

SAP Datasphere helps you to:

-   Specify the semantic usage of each of your entities. See:
    -   [Create a Fact to Contain Measurable Data](create-a-fact-to-contain-measurable-data-30089bd.md)
    -   [Create a Dimension to Categorize Data](create-a-dimension-to-categorize-data-5aae0e9.md)
    -   [Create a Text Entity for Attribute Translation](create-a-text-entity-for-attribute-translation-b25726d.md)
    -   [Create an External Hierarchy for Drill-Down](create-an-external-hierarchy-for-drill-down-dbac7a8.md)
    -   [Create a Hierarchy with Directory](create-a-hierarchy-with-directory-36c39ee.md)

-   Identify measures and attributes, and assign semantic types to them. See:
    -   [Specify Measures to Analyze](specify-measures-to-analyze-33f7f29.md)
    -   [Specify Attributes as Keys, Units, and Other Characteristics](specify-attributes-as-keys-units-and-other-characteristics-cedc59c.md)
    -   [Specify Semantic Types for Measures and Attributes](specify-semantic-types-for-measures-and-attributes-f7272c0.md)

-   Set key columns and create associations between entities. See:
    -   [Set Key Columns to Uniquely Identify Records](set-key-columns-to-uniquely-identify-records-d9ef2c9.md)
    -   [Create an Association to Define a Semantic Relationship Between Entities](create-an-association-to-define-a-semantic-relationship-between-entities-66c6998.md)


Your entities can be exposed for consumption:

-   Directly as relational objects via OData or ODBC/JDBC \(views only\). See [Exposing Data For Consumption](exposing-data-for-consumption-40ec77e.md).
-   Combined and further refined and enriched via an analytic model. See [Creating an Analytic Model](creating-an-analytic-model-e5fbe9e.md).
-   Via further combination in the *Business Builder*. See [Modeling Data in the Business Builder](../Buisiness-Builder/modeling-data-in-the-business-builder-3829d46.md).

