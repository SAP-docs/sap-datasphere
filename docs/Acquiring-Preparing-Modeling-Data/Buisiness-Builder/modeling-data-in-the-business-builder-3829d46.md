<!-- loio3829d46c48a44f1e94915054bd76b7b9 -->

# Modeling Data in the Business Builder

Users with the *DW Modeler* role can use the *Business Builder* editors to combine, refine, and enrich *Data Builder* objects and expose lightweight, tightly-focused perspectives for consumption by SAP Analytics Cloud and other BI clients.

This topic contains the following sections:

-   [Consume Data From the Data Builder in Business Entities](modeling-data-in-the-business-builder-3829d46.md#loio3829d46c48a44f1e94915054bd76b7b9__section_business_entities)
-   [Combine Business Entities in Fact Models and Consumption Models](modeling-data-in-the-business-builder-3829d46.md#loio3829d46c48a44f1e94915054bd76b7b9__section_consumption_models)
-   [Expose Data in Perspectives](modeling-data-in-the-business-builder-3829d46.md#loio3829d46c48a44f1e94915054bd76b7b9__section_perspectives)
-   [Import SAP BW∕4HANA Queries](modeling-data-in-the-business-builder-3829d46.md#loio3829d46c48a44f1e94915054bd76b7b9__section_bw4hana_import)



<a name="loio3829d46c48a44f1e94915054bd76b7b9__section_business_entities"/>

## Consume Data From the Data Builder in Business Entities

Each business entity created in the *Business Builder* consumes data from a *Data Builder* entity. As you can, at any time, switch the data source of a business entity to a different *Data Builder* entity, this loose coupling allows you to maintain stable business entities for reporting, even as your physical data sources change.

-   You can create a business entity by selecting a *Data Builder* entity as its source \(see [Creating a Business Entity](creating-a-business-entity-c912cdc.md)\).
-   You can remove unneeded measures and attributes to simplify your business entity for a particular reporting need.
-   You can enrich your business entity with new measures \(including derived and calculated measures\), attributes, and other properties.
-   You can change the data source of your business entity to a new *Data Builder* entity if necessary.



<a name="loio3829d46c48a44f1e94915054bd76b7b9__section_consumption_models"/>

## Combine Business Entities in Fact Models and Consumption Models

Combine your business entities into star-schemas to prepare them for consumption \(see [Creating a Consumption Model](creating-a-consumption-model-337fa99.md)\).

You can use a single business entity in multiple consumption models and modify it by adding and removing measures and attributes as appropriate for a particular reporting context.

You can, optionally, combine your business entities into an intermediate fact model and then use this as a source for multiple consumption models \(see [Creating a Fact Model](creating-a-fact-model-5bbd14a.md)\).



<a name="loio3829d46c48a44f1e94915054bd76b7b9__section_perspectives"/>

## Expose Data in Perspectives

Create perspectives from a consumption model for exposure to SAP Analytics Cloud and other BI clients, MS Excel, and other apps and tools \(see [Define Perspectives](define-perspectives-ce26fd3.md)\).



<a name="loio3829d46c48a44f1e94915054bd76b7b9__section_bw4hana_import"/>

## Import SAP BW∕4HANA Queries

Import an SAP BW4/HANA query, along with its supporting InfoObjects and CompositeProviders to SAP Datasphere \(see [Importing SAP BW∕4HANA Models](importing-sap-bw-4hana-models-a3d4a2f.md)\).

