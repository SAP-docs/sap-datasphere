<!-- loio30089bd2aa754ab996a62cf5842ae60a -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Fact to Contain Measurable Data

Select a *Semantic Usage* of *Fact* to indicate that your entity contains numerical measures that can be analyzed.



<a name="loio30089bd2aa754ab996a62cf5842ae60a__context_pmz_lr3_spb"/>

## Context

Facts typically contain transactional data, such as:

-   Financial - Sales, Purchases, Orders
-   Logistical - Deliveries, Orders
-   Organizational - Attendance, Leave, Salaries, Expenses

In this example, *Regional Sales* is a *Fact* with:

-   Three measures: *Net Sales*, *Gross Sales*, and *Quantity*.
-   Associations to three dimensions: *Time Dimension - Day*, *Geo Dimension*, and *Product Dimension*.

![](images/Semantic_Usage_Example_91a911d.png)



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

    For more information, see [Creating Packages to Export](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/24aba84ceeb3416881736f70f02e3a0a.html "Users with the DW Space Administrator role can create packages to model groups of related objects for transport between tenants. Modelers can add objects to packages via the Package field, which appears in editors when a package is created in their space. Once a package is complete and validated, the space administrator can export it to the Content Network. The structure of your package is preserved and, as the objects it contains evolve, you can easily export updated versions of it.") :arrow_upper_right:.
    
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
    
    Select *Fact*.

    Alternatively, click <span class="SAP-icons-V5"></span> \(Generate\)** \> *Generate Semantics* to request SAP Datasphere to suggest a *Semantic Usage* for your entity, identify the uses of your columns, and apply appropriate semantic types to them \(see [Generating Semantic Information](generating-semantic-information-2fc1d26.md)\).
    
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
    
    Storage
    
    </td>
    <td valign="top">
    
    \[local tables only\] \[read-only\] Displays the table storage. 
    
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
    
2.  \[views\] To make your view available for consumption outside SAP Datasphere enable the *Expose for Consumption* property \(see [Consuming Data Exposed by SAP Datasphere](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/d7d56284bb5148c887ac4054689bfbca.html "All users with any of the standard roles can consume data exposed by spaces they are assigned to. If a user does not need to access SAP Datasphere itself, and only wants to consume data exposed by it, they should be granted a consumer role.") :arrow_upper_right:\).

    > ### Note:  
    > To consume your data in SAP Analytics Cloud, add it to an analytic model \(see [Creating an Analytic Model](creating-an-analytic-model-e5fbe9e.md)\).

3.  Specify one or more measures \(see [Specify Measures to Analyze](specify-measures-to-analyze-33f7f29.md)\).

4.  Specify your attributes \(see [Specify Attributes as Keys, Units, and Other Characteristics](specify-attributes-as-keys-units-and-other-characteristics-cedc59c.md)\).

5.  \[optional\] Set attributes as keys to indicate that the data they contain can uniquely identify records.

    > ### Note:  
    > You may set one or more key attributes for a *Fact*, but none are required.

    To set an attribute as a key column, select the checkbox in the *Key* column or hover over the attribute in the side panel and click <span class="FPA-icons-V3"></span> \(Menu\)** \> *Set as Key*.

6.  \[optional\] Create associations to point to other entities \(see [Create an Association to Define a Semantic Relationship Between Entities](create-an-association-to-define-a-semantic-relationship-between-entities-66c6998.md)\).

    A *Fact* can point to a:

    -   *Dimension* - One attribute in the \(source\) *Fact* must be mapped to each \(target\) *Dimension* key column so that all target key columns are mapped.

        \[optional\] To bring any data access controls applied to the dimension into the fact to protect its data, select *Apply Dimension Data Access Controls to Fact*.

    -   *Text Entity* - One attribute in the \(source\) *Fact* must be mapped to each \(target\) *Text Entity* identifier key column.

7.  Complete or consult other sections as appropriate:

    -   *Input Parameters* - Create input parameters to require the user to enter a value for use in calculated column, filter, and aggregation nodes \(see [Create an Input Parameter in a Graphical View](../create-an-input-parameter-in-a-graphical-view-53fa99a.md)\).
    -   *Data Persistence* - Persist the view data to improve performance \(see [Persist Data in a Graphical or SQL View](../persist-data-in-a-graphical-or-sql-view-9bd12cf.md)\).
    -   *Associations* - Create associations to other entities \(see [Create an Association to Define a Semantic Relationship Between Entities](create-an-association-to-define-a-semantic-relationship-between-entities-66c6998.md)\).
    -   *Data Access Controls* - Add data access controls to apply row-based security and control access to individual rows based on various criteria \(see [Securing Data with Data Access Controls](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Users with a space administrator role can create data access controls to allow modelers to apply row-level security to Data Builder and Business Builder objects. Once a data access control is applied to an object, any user viewing its data either directly or via an object using it as a source, will see only those records they are authorized to view, based on the specified criteria.") :arrow_upper_right:\).
    -   *Business Purpose* - Provide a description, purpose, contacts, and tags to help other users understand your entity.
    -   *Dependent Objects* - If your entity is used as a source or association target for other entities, then they are listed here \(see [Review the Objects That Depend on Your Table or View](../review-the-objects-that-depend-on-your-table-or-view-ecac5fd.md)\).

8.  Click <span class="FPA-icons-V3"></span> \(Save\)** \> *Save* to save your entity or click <span class="SAP-icons-V5"></span> \(Deploy\) to save and deploy it immediately.

    For more information, see [Saving and Deploying Objects](../saving-and-deploying-objects-7c0b560.md).


