<!-- loiob917baf0431343bea8381fa37e12eeb8 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Transformation Flow in a File Space

Create transformation flows with tables as sources, apply various transformations, and store the resulting dataset into another local table \(file\).



<a name="loiob917baf0431343bea8381fa37e12eeb8__section_nbs_spt_zgc"/>

## Prerequisites

To create flows, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Connection* \(`-R------`\) - To access remote objects.
-   *Data Warehouse Data Builder* \(`CRUD----`\) - To create, edit, and delete flows.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.

To run and schedule flows, you must, in addition, have the following privileges:

-   *Data Warehouse Data Integration* \(`-R------`\) - To view data integration task logs in the *Data Integration Monitor* app.

-   *Data Warehouse Data Integration* \(`--U-----`\) - To manually run data integration tasks.

-   *Data Warehouse Data Integration* \(`----E---`\) - To schedule data integration tasks.


The *DW Modeler* role template, for example, grants the privileges to create and manage flows, and the *DW Integrator* role template grants the privileges to run them. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 



<a name="loiob917baf0431343bea8381fa37e12eeb8__section_qfd_ynt_zgc"/>

## Introduction

> ### Note:  
> For additional information on working with data in the object store, see SAP note [3538038](https://me.sap.com/notes/3538038), SAP note [3722983](https://me.sap.com/notes/3722983) and the blog post [Sizing the SAP Datasphere Object Store](https://community.sap.com/t5/technology-blog-posts-by-sap/sizing-the-sap-datasphere-object-store/ba-p/14376790).

You want to model transformation flows with tables as sources, apply various transformations in a file space dedicated to loading and preparing large quantities of data, and store the resulted dataset into another local table \(file\).

> ### Caution:  
> -   You must be in a file space. See [Create a File Space to Load Data in the Object Store](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/947444683e524cfd9169d7671b72ba0c.html "Create a file space and allocate compute resources to it. File spaces are intended for loading and preparing large quantities of data in an inexpensive inbound staging area and are stored in the SAP Datasphere object store.") :arrow_upper_right:.
> -   You can only preview data for source and target tables. Intermediate node transforms can’t be previewed.
> -   The solution based on SAP HANA Export is not intended or recommended for bulk data transfer. If you encounter resource limit errors due to a SAP HANA export failure, you can either increase the statement memory limit or reduce the number of threads in the source space.



<a name="loiob917baf0431343bea8381fa37e12eeb8__section_hjy_vnt_zgc"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Data Builder*\), select a file space \(if required\) and click *New Transformation Flow*.
2.  On the *New Transformation Flow* screen, add a source:
    -   One source table: drag and drop an object onto the source operator. See [Add a Source to a Graphical View](../add-a-source-to-a-graphical-view-1eee180.md). Note that you can only add local tables \(file\) that don't have deletion vectors enabled, shared local tables \(file\), local tables shared from a SAP HANA space, and shared remote tables on a Delta Share runtime.

        Certain data types that are supported in a SAP HANA Space aren't in a file space and require conversion to supported types. See [Converting Local Table Data Types from a HANA Space to a File Space](converting-local-table-data-types-from-a-hana-space-to-a-file-sp-aac37d0.md).

        > ### Note:  
        > When you use SAP HANA tables as sources in an embedded object store space, all data from the table is exported during initial loads. If you define a filter immediately after defining the table in a graphical view transform, the filter condition is applied while reading from the table. The system copies the data into the object store using SAP HANA export as part of the transformation flow run before further processing operators.

    -   Two or more source tables: click the *View Transform* node, and then click either the *Graphical View Transform* or *SQL View Transform* buttons. See [Create a Graphical View in a Transformation Flow on File](create-a-graphical-view-in-a-transformation-flow-on-file-6eb9640.md) and [Create a SQL View in a Transformation Flow on File](create-a-sql-view-in-a-transformation-flow-on-file-06c4e72.md).

        You can either use a graphical view transform or a SQL view transform in a transformation flow, not both.


3.  Add a transformation. The *View Transform* does not support all functions available in a transformation flow created in an SAP HANA space. See [List of Functions Supported by a Transformation Flow \(in a File Space\)](list-of-functions-supported-by-a-transformation-flow-in-a-file-s-37e737f.md):


    <table>
    <tr>
    <th valign="top">

    Supported Transformations
    
    </th>
    <th valign="top">

    Reference
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Join*
    
    </td>
    <td valign="top">
    
    See [Create a Join in a Graphical View](../create-a-join-in-a-graphical-view-947d6d8.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Union*
    
    </td>
    <td valign="top">
    
    See [Create a Union in a Graphical View](../create-a-union-in-a-graphical-view-5c3d354.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Projection/Rename*
    
    </td>
    <td valign="top">
    
    See [Reorder, Rename, and Exclude Columns in a Graphical View](../reorder-rename-and-exclude-columns-in-a-graphical-view-b846d0d.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Filter*
    
    </td>
    <td valign="top">
    
    See [Filter Data in a Graphical View](../filter-data-in-a-graphical-view-6f6fa18.md) 

    When a shared source is connected directly to the filter node in the view transform, the filter is applied before exporting the data to the local table \(file\) to reduce the size of the file and data movement.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Calculated Column*
    
    </td>
    <td valign="top">
    
    See [Create a Calculated Column in a Graphical View](../create-a-calculated-column-in-a-graphical-view-3897f48.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Aggregation*
    
    </td>
    <td valign="top">
    
    See [Aggregate Data in a Graphical View](../aggregate-data-in-a-graphical-view-7733250.md).
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > Local tables \(file\) support a limited number of data types. See [Data Types Supported By Local Tables \(File\)](data-types-supported-by-local-tables-file-2f39104.md).

    > ### Note:  
    > If a column contains *Personal Data* or *Sensitive Personal Data* from a data product, then it is tagged accordingly, and its parent object also displays the appropriate tag \(see [Modeling with Personal Data](../modeling-with-personal-data-fd0d4e6.md)\).

4.  \[optional\] For machine learning, AI, and analytics use cases, you may need to simplify complex star-schema data models by joining tables to create a flattened view. See [Creating a Flatten Operator](creating-a-flatten-operator-34f48fa.md).
5.  After adding a new source, you might encounter duplicate records in your dataset. The *Remove Duplicate Records* operator allows you to efficiently remove these duplicates from your transformation flow. See [Removing Duplicate Records](removing-duplicate-records-d4b2df0.md).
6.  \[optional\] If your source is a shared table with *Delta Capture* enabled:
    -   you can change its load type \(All Active Records or Delta Capture\) in its settings panel.
    -   if the load type is Inital and Delta, delta changes are propagated to the target table, and even to non-delta target table. See [Capturing Delta Changes in Your Local Table](capturing-delta-changes-in-your-local-table-154bdff.md).

7.  \[optional\] Add a **Python** operator to transform incoming data with a Python script and output structured data to the next operator. See [Creating a Python Operator](creating-a-python-operator-a747acf.md).
8.  Add a target table. See [Create or Add a Target Table to a Transformation Flow](../create-or-add-a-target-table-to-a-transformation-flow-0950746.md).

    > ### Note:  
    > It can only be a local table \(file\).
    > 
    > In a transformation flow, when using delta capture with active records views in joins, deletions may not propagate correctly to the target table in the following cases:
    > 
    > -   Inner joins: Deleted records will not be removed from the target because the join cannot match deletion markers with records that no longer exist in the active records view.
    > -   Filtered left joins: When the active records view is on the right side \(of left join\) with NOT NULL filters applied on active records view column, deletions will not propagate if the matching record is removed from active records view.

9.  \[optional\] Add incremental aggregations to the target table. It is useful for handling incremental data loads and maintaining aggregated results efficiently. See [Creating an Incremental Aggregation on a Target Table in a Transformation Flow on File](creating-an-incremental-aggregation-on-a-target-table-in-a-trans-89cf294.md).
10. Review the properties of your transformation flow, save, deploy, and run it. See [Creating a Transformation Flow](../creating-a-transformation-flow-f7161e6.md).

    > ### Note:  
    > -   The transformation will be saved in the object store. While deploying, a virtual procedure will be created to enable the runtime in the file space.
    > -   A transformation flow on a file space using a shared object as a source cannot be cancelled while running.
    > -   Loading data in batches is not supported in a file space.
    > -   A transformation flow run fails if it lasts for over 48 hours.
    > -   A transformation flow run fails when the source table contains columns that conflict with any of the reserved columns \(\_DRT\_STATUS, \_DRT\_MESSAGE\) of the data remediation table. Rename any conflicting columns in your source table and try again.

11. You can share the target local table \(file\) to another space, including to a space dedicated to SAP HANA Database \(Disk and In-Memory\) storage.
12. More flow analysis options are available in the transformation flow monitor via the *Data Integration Monitor*, like *Simulate Run*, *Generate a SQL Analyzer Plan File*, or [Set Priorities and Statement Limits for Spaces or Groups](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d66ac1efb5054068a104c4559b72d272.html "Prioritize between spaces or groups for resource consumption and set limits to the amount of memory and threads that a space or group can consume when processing statements.") :arrow_upper_right:. See [Explore Transformation Flows](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/7588192bf4cd4e3db43704239ba4d366.html "Use Run with Settings to explore graphical or SQL views and the entities they consume in a transformation flow.") :arrow_upper_right:.

13. \[optional\] You can download your transformation flow on file Spark driver logs in the *Data Integration Monitor* in the flow's *Details* screen. To download this file, you must have the DWC\_RUNTIME privilege added to your DW Administrator role or custom role. There are no logs to download if the run fails before the Spark driver gets started. See [Monitoring Flows](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/b661ea0766a24c7d839df950330a89fd.html "In the Flows monitor, you can find all the deployed flows per space.") :arrow_upper_right:.

