<!-- loio64b318f8afd74bb78467cf56eb44294f -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Sharing Entities and Task Chains to Other Spaces

Share a table or view to another space to allow users assigned to that space to use it as a source for their objects. Share a task chain to another space to allow it to be added to and controlled by another task chain in the space that you share it to.

This topic contains the following sections:

-   [Preparing to Share Entities](sharing-entities-and-task-chains-to-other-spaces-64b318f.md#loio64b318f8afd74bb78467cf56eb44294f__section_preparation)
-   [Share Entities](sharing-entities-and-task-chains-to-other-spaces-64b318f.md#loio64b318f8afd74bb78467cf56eb44294f__section_share)
-   [Share Supporting Entities](sharing-entities-and-task-chains-to-other-spaces-64b318f.md#loio64b318f8afd74bb78467cf56eb44294f__section_semantics)
-   [Share Task Chains](sharing-entities-and-task-chains-to-other-spaces-64b318f.md#loio64b318f8afd74bb78467cf56eb44294f__section_task_chains)
-   [Review Objects Shared With Your Space](sharing-entities-and-task-chains-to-other-spaces-64b318f.md#loio64b318f8afd74bb78467cf56eb44294f__section_review)
-   [Unshare an Object](sharing-entities-and-task-chains-to-other-spaces-64b318f.md#loio64b318f8afd74bb78467cf56eb44294f__section_unshare)



<a name="loio64b318f8afd74bb78467cf56eb44294f__section_sqf_1fx_vgc"/>

## Prerequisites

To share a table, a view, or a task chain to another space, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Data Builder* \(`-R----S-`\) - To share objects to other spaces.
-   *Spaces Files* \(`-R------`\) - To access objects in a space.

The *DW Modeler* role template, for example, grants these privileges \(see [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right: and [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right:\).



<a name="loio64b318f8afd74bb78467cf56eb44294f__section_preparation"/>

## Preparing to Share Entities

Your space is a secure area and its entities and other objects \(and their data\) cannot be seen in other spaces unless you choose to share them. When you share an entity to another space, users in that space can see its data and use it as a source for their views and other objects.

> ### Note:  
> Only entities \(tables and views\) and task chains can be shared. Other *Data Builder* objects and *Business Builder* objects cannot be shared to other spaces.

You can share tables and views, but only views can have row-level security applied to protect data \(see [Securing Data with Data Access Controls](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Users with a space administrator role can create data access controls to allow modelers to apply row-level security to Data Builder and Business Builder objects. Once a data access control is applied to an object, any user viewing its data either directly or via an object using it as a source, will see only those records they are authorized to view, based on the specified criteria.") :arrow_upper_right:\).

In this example, the *IT* space has imported the *Sales* and *Products* tables from a source system and wants to share them to the *Sales* space, but the *Sales* table contains sensitive data:

![](images/Sharing_Example_-_Step_1_e588dcd.png)

In order to protect that data and ensure that users can view only data for which they have permission, an *IT* space user consumes the *Sales* table in the *Sales* view and applies a data access control to the view \(see [Apply a Data Access Control to a Graphical or SQL View](../apply-a-data-access-control-to-a-graphical-or-sql-view-8f79fc8.md)\):

![](images/Sharing_Example_-_Step_2_6b60b6c.png)

Now that the data is protected, the *Sales* view and the *Products* table can both be shared to the *Sales* space, where they are joined with the *Promotions* view to produce the *Sales by Product* view, which inherits the row-level security from the shared *Sales* view:

![](images/Sharing_Example_-_Step_3_4bbcf1c.png)



<a name="loio64b318f8afd74bb78467cf56eb44294f__section_share"/>

## Share Entities

When you share an entity to another space, users in that space can see its data and use it as a source for their views and other objects.

1.  Select the entity or entities you want to share in the *Data Builder* start page or *Repository Explorer*.

    Alternatively, open an entity in its editor.

    > ### Note:  
    > An entity must be deployed before it can be shared.

2.  Click <span class="FPA-icons-V3"></span> \(Share\) to open the *Share* dialog.
3.  In the *Add Spaces* field, enter the name of the space or spaces that you want to share the objects to \(or click <span class="SAP-icons-V5"></span> to select the spaces in a list and then click *Select*.

    > ### Note:  
    > You can share objects to any spaces in your SAP Datasphere tenant, including those you are not assigned to.

4.  Click *Share* to grant the other spaces *Read* access to the objects.

    If you have selected a single space, the *Shared with* list is updated to include these spaces.

    > ### Note:  
    > The *Shared with* list is not shown if two or more objects are selected for sharing.

5.  Click *Close* to close the *Share* dialog.

    Entities that are shared to other spaces display a <span class="FPA-icons-V3"></span> \(Share\) icon after their business name in the *Data Builder* start page and *Repository Explorer*. You can click this icon to open the *Share* dialog, review the spaces the object is shared to, and, if appropriate, stop sharing it.




<a name="loio64b318f8afd74bb78467cf56eb44294f__section_semantics"/>

## Share Supporting Entities

Entities with a semantic usage of *Fact* or *Dimension* commonly have dependencies on other entities and when sharing them, you must also share these associated entities in order to make the services they provide work in the target space:

-   Dimensions - Providing categories to analyze measures \(see [Create a Dimension to Categorize Data](../Modeling-Data-in-the-Data-Builder/create-a-dimension-to-categorize-data-5aae0e9.md)\)
-   Text entities - Providing translations of text values \(see [Create a Text Entity for Attribute Translation](../Modeling-Data-in-the-Data-Builder/create-a-text-entity-for-attribute-translation-b25726d.md)\)
-   External hierarchies - Providing drill-down capabilities \(see [Create an External Hierarchy for Drill-Down](../Modeling-Data-in-the-Data-Builder/create-an-external-hierarchy-for-drill-down-dbac7a8.md)\)
-   Hierarchies with directories - Including all their supporting entities \(see [Create a Hierarchy with Directory](../Modeling-Data-in-the-Data-Builder/create-a-hierarchy-with-directory-36c39ee.md)\)
-   Value help entities - Providing values for input parameters \(see [Create an Input Parameter in a Graphical View](../create-an-input-parameter-in-a-graphical-view-53fa99a.md)\)
-   Lookup entities - Providing help in deriving values for variables \(see [Create a Variable in an Analytic Model](../Modeling-Data-in-the-Data-Builder/create-a-variable-in-an-analytic-model-cdd8fa0.md)\)

> ### Note:  
> If any expected service is missing in the space to which you share your entity, verify that the relevant supporting entity is correctly shared. For example, if texts, hierarchies, or value helps are missing, verify that you have shared the appropriate text entity, hierarchy, or value help entity.

In this example, the *Cities* entity has a semantic usage of *Dimension* and has associations to the *Cities Texts* text entity and to the *Countries* dimension \(which, itself, has an association to the *Countries Texts* text entity\). When sharing *Cities*, you would generally share the other three entities as well:

![](images/Share_Semantic_Entities_-_Dimension_Example_3944abb.png)

In this example, the *Sales View* entity has a semantic usage of *Fact* and has associations to the *Cities* and *Products* dimensions. These dimensions then have further associations to other dimensions and text entities. When sharing *Sales View*, you would generally share the other five entities as well:

![](images/Share_Semantic_Entities_-_Fact_Example_60337a6.png)

> ### Note:  
> You should only share additional entities \(dimensions, text entities, and hierarchies\) that are connected by associations. In this example, you would not share the source table, *Sales Data*, nor the data access control, *Data Access by Department*.



<a name="loio64b318f8afd74bb78467cf56eb44294f__section_task_chains"/>

## Share Task Chains

When you share a task chain to another space, users in that space can add it as a step in their task chains.

> ### Note:  
> When you share a task chain to another space, the integrator in that space must also be a member of your space in order to be able to run your shared task chain as a step in their task chain.

1.  Select the task chains you want to share in the *Data Builder* start page or *Repository Explorer*.

    Alternatively, open a task chain in its editor.

    > ### Note:  
    > A task chain must be deployed before it can be shared.

2.  Click <span class="FPA-icons-V3"></span> \(Share\) to open the *Share* dialog.
3.  In the *Add Spaces* field, enter the name of the space or spaces that you want to share the objects to \(or click <span class="SAP-icons-V5"></span> to select the spaces in a list and then click *Select*.

    > ### Note:  
    > You can share objects to any spaces in your SAP Datasphere tenant, including those you are not a assigned to.

4.  Click *Share* to grant the other spaces *Read* access to the objects.

    If you have selected a single space, the *Shared with* list is updated to include these spaces.

    > ### Note:  
    > The *Shared with* list is not shown if two or more objects are selected for sharing.

5.  Click *Close* to close the *Share* dialog.

    Objects that are shared to other spaces display a <span class="FPA-icons-V3"></span> \(Share\) icon after their business name in the *Data Builder* start page and *Repository Explorer*. You can click this icon to open the *Share* dialog, review the spaces the object is shared to, and, if appropriate, stop sharing it.




<a name="loio64b318f8afd74bb78467cf56eb44294f__section_review"/>

## Review Objects Shared With Your Space

You can see the objects shared with your space:

-   In the *Repository Explorer* \(see [Repository Explorer](repository-explorer-f8ce0b4.md)\).
-   In the *Shared Objects* folder on the *Repository* tab of the *Source Browser* in any *Data Builder* editor \(see [Using the Source Browser](../using-the-source-browser-7d2b21d.md)\).

> ### Note:  
> Objects shared to your space are not listed in the *Data Builder* start page.



<a name="loio64b318f8afd74bb78467cf56eb44294f__section_unshare"/>

## Unshare an Object

To stop sharing an object, expand the *Shared with* list, select the spaces you want to stop sharing it with, and click *Unshare*.

