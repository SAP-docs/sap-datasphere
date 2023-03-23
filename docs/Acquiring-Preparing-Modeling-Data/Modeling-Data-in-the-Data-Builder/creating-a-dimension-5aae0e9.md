<!-- loio5aae0e95361a4a4c964e69c52eada87d -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Dimension

Select a *Semantic Usage* of *Dimension* to indicate that your entity contains attributes that can be used to analyze and categorize measures defined in other entities.



<a name="loio5aae0e95361a4a4c964e69c52eada87d__context_pmz_lr3_spb"/>

## Context

Typical types of dimensions include:

-   Geography - Region, Country, State, City
-   Product - Range, Category, Product
-   Customer
-   Organization - Company, Department, Organization Unit
-   Time - Year, Quarter, Month, Day

    > ### Note:  
    > In order to use a time dimension in SAP Analytics Cloud, you must create your dimension by following the procedure at [Create Time Data and Dimensions](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/internal/en-US/c5cfce4d22b04650b2fd6078762cdeb9.html "As a Space Administrator, you can enrich your models and stories even further by creating a time-related table for your space.") :arrow_upper_right:. Manually-created or other time dimensions may not function correctly.




<a name="loio5aae0e95361a4a4c964e69c52eada87d__steps_nsd_rz3_spb"/>

## Procedure

1.  In the table editor or view editor output node side panel, set the *Semantic Usage* property to *Dimension*.

2.  Specify your attributes \(see [Specify Attributes](specify-attributes-cedc59c.md)\).

3.  Set attributes as keys to indicate that the data they contain can uniquely identify records.

    > ### Note:  
    > You must set one or more key attributes for a *Dimension*:
    > 
    > -   One or more identifier columns
    > -   Validity Start Date - if time-dependency is required \(see [Enable Time-Dependency for a Dimension or Text Entity](enable-time-dependency-for-a-dimension-or-text-entity-11b2ff4.md)\)

    To set an attribute as a key column, select the checkbox in the *Key* column or hover over the attribute in the side panel and click <span class="FPA-icons"></span> \(Menu\)** \> *Set as Key*.

4.  \[optional\] Create associations to point to other entities \(see [Create an Association](../Acquiring-and-Preparing-Data-in-the-Data-Builder/create-an-association-66c6998.md)\).

    A *Dimension* can point to a:

    -   *Dimension* - One attribute in the \(source\) *Dimension* must be mapped to each \(target\) *Dimension* key column so that all target key columns are mapped.
    -   *Text Entity* - An attribute in the \(source\) *Dimension* must be mapped to the \(target\) *Text Entity* identifier key column.
    -   *Hierarchy* - The key attribute in the \(source\) *Dimension* must be mapped to the \(target\) *Hierarchy* child attribute key column.

5.  Complete or consult other sections as appropriate:

    -   *Input Parameters* - Create input parameters to require the user to enter a value for use in calculated column, filter, and aggregation nodes \(see [Create an Input Parameter](../Acquiring-and-Preparing-Data-in-the-Data-Builder/create-an-input-parameter-53fa99a.md)\).
    -   *Persistency* - Persist the view data to improve performance \(see [Persist View Data](../Acquiring-and-Preparing-Data-in-the-Data-Builder/persist-view-data-9bd12cf.md)\).
    -   *Associations* - Create associations to other entities \(see [Create an Association](../Acquiring-and-Preparing-Data-in-the-Data-Builder/create-an-association-66c6998.md)\).
    -   *Data Access Controls* - Add data access controls to apply row-based security and control access to individual rows based on various criteria \(see [Securing Data with Data Access Controls](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/internal/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Data access controls allow you to apply row-level security to your objects. When a data access control is applied to a data layer view or a business layer object, any user viewing its data will see only the rows for which they are authorized, based on the specified criteria.") :arrow_upper_right:\).
    -   *Business Purpose* - Provide a description, purpose, contacts, and tags to help other users understand your entity.
    -   *Dependent Objects* - If your entity is used as a source or association target for other entities, then they are listed here \(see [Review the Objects That Depend on Your Table or View](../Creating-Finding-Sharing-Objects/review-the-objects-that-depend-on-your-table-or-view-ecac5fd.md)\).

6.  Click <span class="FPA-icons"></span> \(Save\) to save your entity:

    -   *Save* to save your object.
    -   *Save As* to create a local a copy of the object you're working on. The object must have been previously saved at least once. The *Save* dialog opens. Enter new business and technical names and click *Save*.

    Click <span class="SAP-icons"></span> \(Deploy\) to deploy your entity.


