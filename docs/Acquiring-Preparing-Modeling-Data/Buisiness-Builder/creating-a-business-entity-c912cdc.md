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

Business entities can be modeled as a dimension or as an analytical dataset. The definition doesn't really differ but rather the intended usage within the consumption model. Dimensions are generally used to contain master data and must have a key defined. Analytical datasets are generally used to contain transactional data and must have at least one measure defined.



## Procedure

1.  In the side navigation area, click <span class="FPA-icons"></span> \(*Business Builder*\), select a space if necessary, and click *New Dimension* or *New Analytical Dataset* to open the editor.

2.  Select a source. You can use views or tables which have been created in the Data Builder as a source.

3.  Select the properties you want to copy from the source. You can copy attributes, measures, input parameters and key definitions.

    > ### Note:  
    > Associations cannot be copied yet.

4.  Enter a descriptive name to help users identify the object. This name can be changed at any time. By default, the name of the source is taken.

5.  A technical name is generated.

    To override the default technical name, enter a new one in the field. Technical names can contain only alphanumeric characters and underscores.

    > ### Note:  
    > Once the object is saved, the technical name can no longer be modified.

6.  Choose *Public Data Access* if you want to allow unrestricted access for this business entity.

    Keep in mind that in most cases data restrictions need to be applied. To do this, select an appropriate authorization scenario. More information: [Authorization Scenario](authorization-scenario-46d8c42.md)

7.  Define the version of your business entity. More information: [Create Versions of an Object](create-versions-of-an-object-e13efeb.md)

8.  If you feel that you have chosen the wrong type for your purpose, you can still convert your dimension into an analytical dataset, or vice versa.

9.  Save your entries.

10. Define the measures of your business entity. More information: [Define Measures](define-measures-903acb8.md)

11. Define the attributes of your business entity. More information: [Define Attributes](define-attributes-270bb3d.md)

12. Define the keys of your business entity. You need to define at least one unique key in order to use the business entity as a dimension later on. More information: [Define a Key](define-a-key-9748bab.md)

    In case you have taken over the key definition from the source, you need to verify the uniqueness of your key. Go to the *Key Definitions* tab and choose *Verify*.

13. Associate the dimensions. More information: [Define Associations](define-associations-77cb7fc.md)

14. You can assign an authorization scenario, if you want to restrict the access to this business entity. More information: [Assigning an Authorization Scenario](assigning-an-authorization-scenario-2e62354.md)

15. You can check your business entity in the data preview. A data preview is only possible if the underlying object in the Data Builder is deployed.

16. Once you are satisfied with the definition of your business entity, you can set the status of your version to *Ready to Use*. For more information on versions, see [Create Versions of an Object](create-versions-of-an-object-e13efeb.md).




<a name="loioc912cdc1537d4efbb24b08327ea68918__result_hx4_wcb_x4b"/>

## Results

You can use your business entity in fact models and consumption models.

