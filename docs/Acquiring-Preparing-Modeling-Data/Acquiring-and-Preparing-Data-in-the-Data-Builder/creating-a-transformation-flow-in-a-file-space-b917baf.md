<!-- loiob917baf0431343bea8381fa37e12eeb8 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Transformation Flow in a File Space

Create transformation flows with local tables \(file\), shared local tables, and shared remote tables on a Delta Share runtime as sources, apply various transformations, and store the resulted dataset into another local table \(file\).



<a name="loiob917baf0431343bea8381fa37e12eeb8__section_nbs_spt_zgc"/>

## Prerequisites

To create flows, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Connection* \(`-R------`\) - To access remote objects.
-   *Data Warehouse Data Builder* \(`CRUD----`\) - To create, edit and delete flows.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.

To run and schedule flows, you must, in addition, have the following privileges:

-   *Data Warehouse Data Integration* \(`-RU-----`\) - To run flows.
-   *Data Warehouse Data Integration* \(`-R--E---`\) - To schedule flows.

The *DW Modeler* and *DW Integrator* role templates together, for example, grant these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 



<a name="loiob917baf0431343bea8381fa37e12eeb8__section_qfd_ynt_zgc"/>

## Introduction

> ### Note:  
> For additional information on working with data in the object store, see SAP note [3538038](https://me.sap.com/notes/3538038).

You want to model transformation flows with local tables \(file\), shared local tables, and shared remote tables on a Delta Share runtime as sources, apply various transformations in a file space dedicated to loading and preparing large quantities of data, and store the resulted dataset into another local table \(file\).

> ### Caution:  
> -   You must be in a file space. For more information, see [Create a File Space to Load Data in the Object Store](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/947444683e524cfd9169d7671b72ba0c.html "Create a file space and allocate compute resources to it. File spaces are intended for loading and preparing large quantities of data in an inexpensive inbound staging area and are stored in the SAP Datasphere object store.") :arrow_upper_right:.
> -   Your source can be a local table \(file\), a shared local table from a SAP HANA Space, or a shared remote tables on a Delta Share runtime. Your target must be a local table \(file\). For more information, see [Creating a Local Table \(File\)](creating-a-local-table-file-d21881b.md).
> -   You can only create a graphical view transform.
> -   You can only preview data for source and target tables. Intermediate node transforms can’t be previewed.
> -   If your source is a shared table with *Delta Capture* enabled, you can change its load type \(*All Active Records* or *Delta Capture*\) in its settings panel.



<a name="loiob917baf0431343bea8381fa37e12eeb8__section_hjy_vnt_zgc"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Data Builder*\), select a file space \(if required\) and click *New Transformation Flow*.
2.  On the *New Transformation Flow* screen, you can either drag and drop an object onto the source operator or click the *View Transform* node, and then click *Graphical View Transform* button.

    > ### Note:  
    > On file space, you can only create *Graphical View Transform*.

3.  Add a source. For more information, see [Add a Source to a Graphical View](../add-a-source-to-a-graphical-view-1eee180.md). Note that you can only add local tables \(file\), local tables shared from a SAP HANA space, and shared remote tables on a Delta Share runtime.
4.  Add a Transformation. The *View Transform* does not support all functions available in a transformation flow created in an SAP HANA space. For more information, see [List of Functions Supported by a Transformation Flow \(in a File Space\)](list-of-functions-supported-by-a-transformation-flow-in-a-file-s-37e737f.md):


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
    
    See [Create a Join in a Graphical View](../create-a-join-in-a-graphical-view-947d6d8.md)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Union*
    
    </td>
    <td valign="top">
    
    See [Create a Union in a Graphical View](../create-a-union-in-a-graphical-view-5c3d354.md)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Projection/Rename*
    
    </td>
    <td valign="top">
    
    See [Reorder, Rename, and Exclude Columns in a Graphical View](../reorder-rename-and-exclude-columns-in-a-graphical-view-b846d0d.md)
    
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
    
    See [Create a Calculated Column in a Graphical View](../create-a-calculated-column-in-a-graphical-view-3897f48.md)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Aggregation*
    
    </td>
    <td valign="top">
    
    See [Aggregate Data in a Graphical View](../aggregate-data-in-a-graphical-view-7733250.md)
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > Local tables \(file\) support a limited number of data types. For more information, see [Data Types Supported By Local Tables \(File\)](data-types-supported-by-local-tables-file-2f39104.md).

5.  \[optional\] Add a **Python** operator to transform incoming data with a Python script and output structured data to the next operator. For more information, see [Creating a Python Operator](creating-a-python-operator-a747acf.md).
6.  \[optional\] Add incremental aggregations to the target table. It is useful for handling incremental data loads and maintaining aggregated results efficiently:

    1.  Click the target node to display its properties in the side panel. In the *Incremental Aggregation* section, click *Edit Aggregation*.
    2.  In the *Incremental Aggregation* dialog are listed all aggregations with numerical data types. You can define the aggregation types LAST \(default\), SUM, or COUNT.
    3.  Click *Save*. You can see the updated columns in the *Incremental Aggregations* section.

    > ### Note:  
    > -   Incremental aggregations are supported only if the source table has *Delta Capture* enabled. They aren't supported for shared sources having *Delta Capture* enabled.
    > -   LAST refers to the latest operations applied on the row.
    > -   Columns with non-numerical aggregation types can only have the type LAST.
    > -   In the case the row is deleted on the source delta table, the row will be available in the target table and the aggregated values are then set to 0.
    > -   If incremental aggregation is enabled, the input DataFrame for the Python script will include the previous versions of the data for updates.

7.  Add a target table. For more information, see [Create or Add a Target Table to a Transformation Flow](../create-or-add-a-target-table-to-a-transformation-flow-0950746.md).

    > ### Note:  
    > It can only be a local table \(file\) and *Delete All Before Loading* is not supported.

8.  Review the properties of your transformation flow, save, deploy, and run it. See [Creating a Transformation Flow](../creating-a-transformation-flow-f7161e6.md).

    > ### Note:  
    > -   The transformation will be saved in the object store. While deploying, a virtual procedure will be created to enable the runtime in the file space.
    > -   A transformation flow on a file space using a shared object as a source cannot be cancelled while running. Wait until the export step of the run is complete to cancel it.

9.  You can share the target local table \(file\) to another space, including to a space dedicated to SAP HANA Database \(Disk and In-Memory\) storage.
10. More flow analysis options are available in the transformation flow monitor via the *Data Integration Monitor*:

    -   Simulate a run that doesn't save changes in the target table by clicking *Simulate Run*. Simulating allows you to test a transformation flow and see if you get the desired outcome. Based on the result, you can decide to deploy the flow, resolve errors, or to optimize the flow to improve performances.
    -   Download a PLV file of a visual map of the operators and their relationships and hierarchies by clicking *Generate a SQL Analyzer Plan File*. The plan file contains detailed information about your data model that you can download for further analysis. Analyzing this file allows you to resolve errors and enhance the transformation flow performances.
    -   See your change details. If you experience a *Failed Resource Limit Error*, you must either increase the statement memory limit or reduce the number of threads. See [Set Priorities and Statement Limits for Spaces or Groups](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d66ac1efb5054068a104c4559b72d272.html "Prioritize between spaces or groups for resource consumption and set limits to the amount of memory and threads that a space or group can consume when processing statements.") :arrow_upper_right:.

    For more information, see [Explore Transformation Flows](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/7588192bf4cd4e3db43704239ba4d366.html "Use Run with Settings to explore graphical or SQL views and the entities they consume in a transformation flow.") :arrow_upper_right:.


