<!-- loio5aae0e95361a4a4c964e69c52eada87d -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Dimension to Categorize Data

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
    > In order to use a time dimension in SAP Analytics Cloud, you must create your dimension by following the procedure at [Create Time Data and Dimensions](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/c5cfce4d22b04650b2fd6078762cdeb9.html "Create a time table and dimension views in your space to provide standardized time data for your analyses. The time table contains a record for each day in the specified period (by default from 1900 to 2050), and the dimension views allow you to work with this date data at a granularity of day, week, month, quarter, and year, and to drill down and up in hierarchies.") :arrow_upper_right:. Manually-created or other time dimensions may not function correctly.




<a name="loio5aae0e95361a4a4c964e69c52eada87d__steps_nsd_rz3_spb"/>

## Procedure

1.  In the table editor or view editor output node side panel, complete the *General* section as follows:


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
    
    Package
    
    </td>
    <td valign="top">
    
    Select the package to which the object belongs. 

    Packages are used to group related objects in order to facilitate their transport between tenants.

    > ### Note:  
    > Once a package is selected, it cannot be changed here. Only a user with the DW Space Administrator role \(or equivalent privileges\) can modify a package assignment in the *Packages* editor.

    For more information, see [Creating Packages to Export](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/24aba84ceeb3416881736f70f02e3a0a.html "Users with the DW Space Administrator role can create packages to model groups of related objects for transport between tenants. Modelers can add objects to packages via the Package field, which appears in editors when a package is created in their space. Once a package is complete and validated, the space administrator can export it to the Content Network. The structure of your package is preserved and, as the objects it contains evolve, you can easily export updated versions of it.") :arrow_upper_right:.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Release State
    
    </td>
    <td valign="top">
    
    \[views only\] Specifies whether the object is released, providing modelers and consumers with confidence that it will remain available in its current form for the foreseeable future. 

    For more information, see [Releasing Stable Views for Consumption](../releasing-stable-views-for-consumption-5b99e9b.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Semantic Usage
    
    </td>
    <td valign="top">
    
    Select *Dimension*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Expose for Consumption
    
    </td>
    <td valign="top">
    
    \[views only\] Enable this option to make the view available for consumption outside SAP Datasphere via OData or ODBC/JDBC. 

    This option is not required if you want to expose your data through an analytic model \(see [Creating an Analytic Model](creating-an-analytic-model-e5fbe9e.md)\). For an overview about making your data accessible outside SAP Datasphere, see [Exposing Data For Consumption](exposing-data-for-consumption-40ec77e.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Run in Analytical Mode
    
    </td>
    <td valign="top">
    
    \[views only\] Enable this option to send the `USE_OLAP_PLAN` hint to the SQL optimizer. 

    This may improve view performance, particularly if a union is performed. It is only available if *Expose for Consumption* is enabled.

    For more information, see [HINT Details](https://help.sap.com/viewer/c1d3f60099654ecfb3fe36ac93c121bb/latest/en-US/4ba9edce1f2347a0b9fcda99879c17a1.html) in the *SAP HANA Cloud, SAP HANA Database SQL Reference Guide*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Allow Data Transport
    
    </td>
    <td valign="top">
    
    \[local tables only\] Enables users to include the table data when transporting the table in a repository package. 

    This feature is intended to allow you to transport data for static or slowly changing dimensions and can only be used to initialize data when importing the table for the first time.

    See [Creating Packages to Export](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/24aba84ceeb3416881736f70f02e3a0a.html "Users with the DW Space Administrator role can create packages to model groups of related objects for transport between tenants. Modelers can add objects to packages via the Package field, which appears in editors when a package is created in their space. Once a package is complete and validated, the space administrator can export it to the Content Network. The structure of your package is preserved and, as the objects it contains evolve, you can easily export updated versions of it.") :arrow_upper_right:.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Storage
    
    </td>
    <td valign="top">
    
    \[local tables only\] Displays the table storage. 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Status
    
    </td>
    <td valign="top">
    
    \[read-only\] Displays the deployment and error status of the object. 

    For more information, see [Saving and Deploying Objects](../saving-and-deploying-objects-7c0b560.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Deployed On
    
    </td>
    <td valign="top">
    
    \[read-only\] Displays the date and time of the last deployment.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Data Validation Status
    
    </td>
    <td valign="top">
    
    \[views only\] Displays the status of the last data validation. 

    Click the button to open the *Data Validation* panel \(see [Validating View Data](../validating-view-data-ed4063d.md)\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Validated On
    
    </td>
    <td valign="top">
    
    \[views only\] \[read-only\] Displays the date and time of the last data validation.
    
    </td>
    </tr>
    </table>
    
2.  Specify your attributes \(see [Specify Attributes as Keys, Units, and Other Characteristics](specify-attributes-as-keys-units-and-other-characteristics-cedc59c.md)\).

3.  Set attributes as keys to indicate that the data they contain can uniquely identify records.

    > ### Note:  
    > You must set one or more key attributes for a *Dimension*:
    > 
    > -   One or more identifier columns
    > -   Validity Start Date - if time-dependency is required \(see [Enable Time-Dependency for a Dimension or Text Entity](enable-time-dependency-for-a-dimension-or-text-entity-11b2ff4.md)\)

    To set an attribute as a key column, select the checkbox in the *Key* column or hover over the attribute in the side panel and click <span class="FPA-icons-V3"></span> \(Menu\)** \> *Set as Key*.

4.  \[optional\] Create associations to point to other entities \(see [Create an Association to Define a Semantic Relationship Between Entities](create-an-association-to-define-a-semantic-relationship-between-entities-66c6998.md)\).

    A *Dimension* can point to a:

    -   *Dimension* - One attribute in the \(source\) *Dimension* must be mapped to each \(target\) *Dimension* key column so that all target key columns are mapped.
    -   *Text Entity* - One attribute in the \(source\) *Dimension* must be mapped to each \(target\) *Text Entity* identifier key column.
    -   *Hierarchy* - Each key attribute in the \(source\) *Dimension* must be mapped to a \(target\) *Hierarchy* child attribute key column.

5.  Complete or consult other sections as appropriate:

    -   *Input Parameters* - Create input parameters to require the user to enter a value for use in calculated column, filter, and aggregation nodes \(see [Create an Input Parameter in a Graphical View](../create-an-input-parameter-in-a-graphical-view-53fa99a.md)\).
    -   *Data Persistence* - Persist the view data to improve performance \(see [Persist Data in a Graphical or SQL View](../persist-data-in-a-graphical-or-sql-view-9bd12cf.md)\).
    -   *Associations* - Create associations to other entities \(see [Create an Association to Define a Semantic Relationship Between Entities](create-an-association-to-define-a-semantic-relationship-between-entities-66c6998.md)\).
    -   *Data Access Controls* - Add data access controls to apply row-based security and control access to individual rows based on various criteria \(see [Securing Data with Data Access Controls](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Users with a space administrator role can create data access controls to allow modelers to apply row-level security to Data Builder and Business Builder objects. Once a data access control is applied to an object, any user viewing its data either directly or via an object using it as a source, will see only those records they are authorized to view, based on the specified criteria.") :arrow_upper_right:\).
    -   *Business Purpose* - Provide a description, purpose, contacts, and tags to help other users understand your entity.
    -   *Dependent Objects* - If your entity is used as a source or association target for other entities, then they are listed here \(see [Review the Objects That Depend on Your Table or View](../review-the-objects-that-depend-on-your-table-or-view-ecac5fd.md)\).

6.  Click <span class="FPA-icons-V3"></span> \(Save\)** \> *Save* to save your entity or click <span class="SAP-icons-V5"></span> \(Deploy\) to save and deploy it immediately.

    For more information, see [Saving and Deploying Objects](../saving-and-deploying-objects-7c0b560.md).


