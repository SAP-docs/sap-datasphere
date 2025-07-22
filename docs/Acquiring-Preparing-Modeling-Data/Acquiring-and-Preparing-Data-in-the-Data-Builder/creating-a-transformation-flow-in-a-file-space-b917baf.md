<!-- loiob917baf0431343bea8381fa37e12eeb8 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Transformation Flow in a File Space

Create transformation flows with local tables \(file\) as sources, apply various transformations, and store the resulted dataset into another local table \(file\).

> ### Note:  
> For additional information on working with data in the object store, see SAP note [3538038](https://me.sap.com/notes/3538038).

As a Datasphere modeler, you want to model transformation flows with local tables \(file\) as sources, apply various transformations in a file space dedicated to loading and preparing large quantities of data, and store the resulted dataset into another local table \(file\).

> ### Caution:  
> -   You must be in a file space. For more information, see [Create a File Space to Load Data in the Object Store](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/947444683e524cfd9169d7671b72ba0c.html "Create a file space and allocate compute resources to it. File spaces are intended for loading and preparing large quantities of data in an inexpensive inbound staging area and are stored in the SAP Datasphere object store.") :arrow_upper_right:.
> -   You source and target must be local table \(file\). For more information, see [Creating a Local Table \(File\)](creating-a-local-table-file-d21881b.md).
> -   You can only create a graphical view transform.
> -   You can only preview data for source and target tables. Intermediate node transforms can’t be previewed.

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Data Builder*\), select a file space \(if required\) and click *New Transformation Flow*.
2.  On the *New Transformation Flow* screen, you can either drag and drop an object onto the source operator or click the *View Transform* node, and then click *Graphical View Transform* button.

    > ### Note:  
    > On file space, you can only create *Graphical View Transform*.

3.  Add a source. For more information, see [Creating a Transformation Flow in a File Space](creating-a-transformation-flow-in-a-file-space-b917baf.md). Note that you can only add a local table \(file\).
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
    > -   LAST refers to the latest operations applied on the row.
    > -   Columns with non-numerical aggregation types can only have the type LAST.
    > -   In the case the row is deleted on the source delta table, the row will be available in the target table and the aggregated values are then set to 0.
    > -   If incremental aggregation is enabled, the input DataFrame for the Python script will include the previous versions of the data for updates.

7.  Add a target table. For more information, see [Create or Add a Target Table to a Transformation Flow](../create-or-add-a-target-table-to-a-transformation-flow-0950746.md).

    > ### Note:  
    > It can only be a local table \(file\) and *Delete All Before Loading* is not supported.

8.  Review the properties of your transformation flow, save and deploy it. See [Creating a Transformation Flow](../creating-a-transformation-flow-f7161e6.md).

    > ### Note:  
    > The transformation will be saved in the object store. While deploying, a virtual procedure will be created to enable the runtime in the file space.

9.  You can share the target local table \(file\) to another space, including to a space dedicated to SAP HANA Database \(Disk and In-Memory\) storage.
10. More flow analysis options are available in the transformation flow monitor via the *Data Integration Monitor*:

    -   Simulate a run that doesn't save changes in the target table by clicking *Simulate Run*. Simulating allows you to test a transformation flow and see if you get the desired outcome. Based on the result, you can decide to deploy the flow, resolve errors, or to optimize the flow to improve performances.
    -   Download a PLV file of a visual map of the operators and their relationships and hierarchies by clicking *Generate a SQL Analyzer Plan File*. The plan file contains detailed information about your data model that you can download for further analysis. Analyzing this file allows you to resolve errors and enhance the transformation flow performances.

    For more information, see [Explore Transformation Flows](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/7588192bf4cd4e3db43704239ba4d366.html "Use Run with Settings to explore graphical or SQL views and the entities they consume in a transformation flow.") :arrow_upper_right:


