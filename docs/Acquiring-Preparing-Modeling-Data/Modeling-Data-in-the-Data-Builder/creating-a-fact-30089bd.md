<!-- loio30089bd2aa754ab996a62cf5842ae60a -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Fact

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

1.  In the table editor or view editor output node side panel, set the *Semantic Usage* property to *Fact*.

2.  \[views\] To make your view available for consumption outside SAP Datasphere enable the *Expose for Consumption* property \(see [Consuming Data Exposed by SAP Datasphere](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/d7d56284bb5148c887ac4054689bfbca.html "All users of with any of the standard roles can consume data exposed by spaces they are assigned to. If a user does not need to access SAP Datasphere itself, and only wants to consume data exposed by it, they should be granted the DW Consumer role.") :arrow_upper_right:\).

    > ### Note:  
    > To consume your data in SAP Analytics Cloud, add it to an analytic model \(see [Creating an Analytic Model](creating-an-analytic-model-e5fbe9e.md)\).

3.  Specify one or more measures \(see [Specify Measures](specify-measures-33f7f29.md)\).

4.  Specify your attributes \(see [Specify Attributes](specify-attributes-cedc59c.md)\).

5.  \[optional\] Set attributes as keys to indicate that the data they contain can uniquely identify records.

    > ### Note:  
    > You may set one or more key attributes for a *Fact*, but none are required.

    To set an attribute as a key column, select the checkbox in the *Key* column or hover over the attribute in the side panel and click <span class="FPA-icons"></span> \(Menu\)** \> *Set as Key*.

6.  \[optional\] Create associations to point to other entities \(see [Create an Association](../create-an-association-66c6998.md)\).

    A *Fact* can point to a:

    -   *Dimension* - One attribute in the \(source\) *Fact* must be mapped to each \(target\) *Dimension* key column so that all target key columns are mapped.
    -   *Text Entity* - An attribute in the \(source\) *Fact* must be mapped to the \(target\) *Text Entity* identifier key column.

7.  Complete or consult other sections as appropriate:

    -   *Input Parameters* - Create input parameters to require the user to enter a value for use in calculated column, filter, and aggregation nodes \(see [Create an Input Parameter](../create-an-input-parameter-53fa99a.md)\).
    -   *Data Persistence* - Persist the view data to improve performance \(see [Persist View Data](../persist-view-data-9bd12cf.md)\).
    -   *Associations* - Create associations to other entities \(see [Create an Association](../create-an-association-66c6998.md)\).
    -   *Data Access Controls* - Add data access controls to apply row-based security and control access to individual rows based on various criteria \(see [Securing Data with Data Access Controls](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Data access controls allow you to apply row-level security to your objects. When a data access control is applied to a data layer view or a business layer object, any user viewing its data will see only the rows for which they are authorized, based on the specified criteria.") :arrow_upper_right:\).
    -   *Business Purpose* - Provide a description, purpose, contacts, and tags to help other users understand your entity.
    -   *Dependent Objects* - If your entity is used as a source or association target for other entities, then they are listed here \(see [Review the Objects That Depend on Your Table or View](../Creating-Finding-Sharing-Objects/review-the-objects-that-depend-on-your-table-or-view-ecac5fd.md)\).

8.  Click <span class="FPA-icons"></span> \(Save\)** \> *Save* to save your entity or click <span class="SAP-icons"></span> \(Deploy\) to save and deploy it immediately.

    For more information, see [Saving and Deploying Objects](../Creating-Finding-Sharing-Objects/saving-and-deploying-objects-7c0b560.md).


