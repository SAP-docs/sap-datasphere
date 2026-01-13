<!-- loio8b84bd8dbbbf498f9dff8add4bff6489 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Sharing Analytic Models to Other Spaces

Share an analytic model to another space to allow users assigned to that space to use it as a source for another analytic model. This enables users to consume models from other spaces.



<a name="loio8b84bd8dbbbf498f9dff8add4bff6489__prereq_bq3_kl5_2hc"/>

## Prerequisites

To share a table, a view, or a task chain to another space, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Data Builder* \(`-R----S-`\) - To share objects to other spaces.
-   *Spaces Files* \(`-R------`\) - To access objects in a space.

The *DW Modeler* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 

Every entity that is consumed by the analytic model has to be shared before you start sharing the analytic model.



## Context

Your space is a secure area and its entities and other objects \(and their data\) cannot be seen in other spaces unless you choose to share them. When you share an analytic model to another space, users in that space can see its data and use it as a source for another analytic model.

> ### Caution:  
> In case your analytic model contains conversion measures for currencies or units, you need to be aware that the analytic model always uses the conversion tables and views of the space where it is consumed. This ensures that even in a complex scenario all conversion measures are converted using the same conversion tables and views and are consistent within the analytic model.



## Procedure

1.  Select the analytic model you want to share in the *Data Builder* start page or *Repository Explorer*. Alternatively, open an analytic model in its editor.

    > ### Note:  
    > The analytic model must be deployed before it can be shared.

2.  Choose <span class="FPA-icons-V3"></span> \(Share\) to open the *Share* dialog.

3.  In the *Add Spaces* field, enter the name of the space or spaces that you want to share the analytic model to \(or choose <span class="SAP-icons-V5"></span> to select the spaces in a list and then click *Select*.

    > ### Note:  
    > You can share objects to any spaces in your SAP Datasphere tenant, including those you are not assigned to.

4.  Choose *Share* to grant the other spaces *Read* access to the objects. If you have selected a single space, the *Shared with* list is updated to include these spaces.

    > ### Note:  
    > The *Shared with* list is not shown if two or more objects are selected for sharing.

5.  Choose *Close* to close the *Share* dialog.

    Entities that are shared to other spaces display a <span class="FPA-icons-V3"></span> \(Share\) icon after their business name in the *Data Builder* start page and *Repository Explorer*. You can click this icon to open the *Share* dialog, review the spaces the object is shared to, and, if appropriate, stop sharing it.


