<!-- loioc912cdc1537d4efbb24b08327ea68918 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Business Entity

You use business entities to build your consumption model for analysis and reporting.



<a name="loioc912cdc1537d4efbb24b08327ea68918__prereq_xh3_qsy_1mb"/>

## Prerequisites

Views or tables have been created in the Data Builder.



## Context

Business entities can define measures or attributes. Measures are quantifiable values that refer to an aggregable field of the underlying model. An attribute is a descriptive element of a business entity and provides meaningful business insights into measures. The underlying model is a view or a table, which has been created in the Data Builder.

In order to model a meaningful consumption model, business entities define associations between each other. All potential association targets can be pre-defined on the data layer in order to provide business users a variety of modeling options to choose from when preparing their use case-specific consumption model.

Business entities can be modeled as a dimension or as a fact. Dimensions are generally used to contain master data and must have a key defined. Facts are generally used to contain transactional data and must have at least one measure defined.



## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Business Builder*\), select a space if necessary, and click *New Dimension* or *New Fact* to open the editor.

2.  Select a source. You can use views or tables which have been created in the Data Builder as a source.

3.  Select the properties you want to copy from the source. You can copy attributes, measures, input parameters and key definitions.

    > ### Note:  
    > Associations cannot be copied yet.

4.  Enter a descriptive name to help users identify the object. This name can be changed at any time. By default, the name of the source is taken.

5.  A technical name is generated.

    To override the default technical name, enter a new one in the field. Technical names can contain only alphanumeric characters and underscores.

    > ### Note:  
    > Once the object is saved, the technical name can no longer be modified.

6.  \[optional\] Select the package to which the object belongs.

    Packages are used to group related objects in order to facilitate their transport between tenants.

    > ### Note:  
    > Once a package is selected, it cannot be changed here. Only a user with the DW Space Administrator role \(or equivalent privileges\) can modify a package assignment in the *Packages* editor.

    For more information, see [Creating Packages to Export](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/24aba84ceeb3416881736f70f02e3a0a.html "Users with the DW Space Administrator role can create packages to model groups of related objects for transport between tenants. Modelers can add objects to packages via the Package field, which appears in editors when a package is created in their space. Once a package is complete and validated, the space administrator can export it to the Content Network. The structure of your package is preserved and, as the objects it contains evolve, you can easily export updated versions of it.") :arrow_upper_right:.

7.  Choose *Public Data Access* if you want to allow unrestricted access for this business entity.

    Keep in mind that in most cases data restrictions need to be applied. To do this, select an appropriate authorization scenario. More information: [Authorization Scenario](authorization-scenario-46d8c42.md)

8.  Define the version of your business entity. More information: [Create Versions of an Object](create-versions-of-an-object-e13efeb.md)

9.  If you feel that you have chosen the wrong type for your purpose, you can still convert your dimension into a fact, or vice versa.

10. Save your entries.

11. Define the measures of your business entity. More information: [Define Measures](define-measures-903acb8.md)

12. Define the attributes of your business entity. More information: [Define Attributes](define-attributes-270bb3d.md)

13. Define the keys of your business entity. You need to define at least one unique key in order to use the business entity as a dimension later on. More information: [Define a Key](define-a-key-9748bab.md)

    In case you have taken over the key definition from the source, you need to verify the uniqueness of your key. Go to the *Key Definitions* tab and choose *Verify*.

14. Associate the dimensions. More information: [Define Associations](define-associations-77cb7fc.md)

15. You can assign an authorization scenario, if you want to restrict the access to this business entity. More information: [Assigning an Authorization Scenario](assigning-an-authorization-scenario-2e62354.md)

16. You can check your business entity in the data preview. A data preview is only possible if the underlying object in the Data Builder is deployed.

17. Once you are satisfied with the definition of your business entity, you can set the status of your version to *Ready to Use*. For more information on versions, see [Create Versions of an Object](create-versions-of-an-object-e13efeb.md).




<a name="loioc912cdc1537d4efbb24b08327ea68918__result_hx4_wcb_x4b"/>

## Results

You can use your business entity in fact models and consumption models.

