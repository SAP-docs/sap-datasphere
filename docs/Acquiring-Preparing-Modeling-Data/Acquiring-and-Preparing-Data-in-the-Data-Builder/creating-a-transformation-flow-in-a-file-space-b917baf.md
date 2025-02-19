<!-- loiob917baf0431343bea8381fa37e12eeb8 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Transformation Flow in a File Space

Create transformation flows with local tables \(file\) as sources, apply various transformations, and store the resulted dataset into another local table \(file\).

> ### Note:  
> The object store is not enabled by default in SAP Datasphere tenants. To enable it in your tenant, see SAP note [3525760](https://me.sap.com/notes/3525760).
> 
> For additional information on working with data in the object store, see SAP Note [3538038](https://me.sap.com/notes/3538038).
> 
> The object store cannot be enabled in SAP Datasphere tenants provisioned prior to version 2021.03. To request the migration of your tenant, see SAP note [3268282](https://me.sap.com/notes/3268282).

As a Datasphere modeler, you want to model transformation flows with local tables \(file\) as sources, apply various transformations in a file space dedicated to loading and preparing large quantities of data, and store the resulted dataset into another local table \(file\).

> ### Caution:  
> -   You must be in a file space. For more information, see [Create a File Space to Load Data in the Object Store](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/947444683e524cfd9169d7671b72ba0c.html "Create a space with SAP HANA data lake files storage in the object store, allocate compute resources and assign one or more users to allow them to start acquiring and preparing data. File spaces are intended for loading and preparing large quantities of data in an inexpensive inbound staging area.") :arrow_upper_right:.
> -   You source and target targe must be local table \(file\). For more information, see [Creating a Local Table \(File\)](creating-a-local-table-file-d21881b.md).
> -   You can only create a graphical view transform.
> -   You can only preview data for source and target tables. Intermediate node transforms can’t be previewed.

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Data Builder*\), select a file space \(if required\) and click *New Transformation Flow*.
2.  On the *New Transformation Flow* screen, click the *View Transform* node, and then click *Graphical View Transform* button.

    > ### Note:  
    > On file space, you can only create *Graphical View Transform*.

3.  Add a source. For more information, see  <?sap-ot O2O class="- topic/xref " href="ec702fe3b1134f278c5c538b447b7435.xml" text="" desc="" xtrc="xref:3" xtrf="file:/home/builder/src/dita-all/sqq1737416514784/loioc25299a38b6448f889a43b42c9e5897d_en-US/src/content/localization/en-us/b917baf0431343bea8381fa37e12eeb8.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> . Note that you can only add a local table \(file\).
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
    
    See  <?sap-ot O2O class="- topic/xref " href="bcb5f48ec99242da8f2cb3483b8409b7.xml" text="" desc="" xtrc="xref:5" xtrf="file:/home/builder/src/dita-all/sqq1737416514784/loioc25299a38b6448f889a43b42c9e5897d_en-US/src/content/localization/en-us/b917baf0431343bea8381fa37e12eeb8.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Union*
    
    </td>
    <td valign="top">
    
    See  <?sap-ot O2O class="- topic/xref " href="9cd6fbf4710e4a31a3fd5246302ed9ec.xml" text="" desc="" xtrc="xref:6" xtrf="file:/home/builder/src/dita-all/sqq1737416514784/loioc25299a38b6448f889a43b42c9e5897d_en-US/src/content/localization/en-us/b917baf0431343bea8381fa37e12eeb8.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> 
    
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
    
    See  <?sap-ot O2O class="- topic/xref " href="f368ba00de89482e8034d2c7281c255b.xml" text="" desc="" xtrc="xref:10" xtrf="file:/home/builder/src/dita-all/sqq1737416514784/loioc25299a38b6448f889a43b42c9e5897d_en-US/src/content/localization/en-us/b917baf0431343bea8381fa37e12eeb8.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> 
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > Local tables \(file\) support a limited number of data types. For more information, see [Data Types Supported By Local Tables \(File\)](data-types-supported-by-local-tables-file-2f39104.md).

5.  \[optional\] Add a **Python** operator to transform incoming data with a Python script and output structured data to the next operator. For more information, see [Creating a Python Operator](creating-a-python-operator-a747acf.md).
6.  Add a target table. For more information, see [Create or Add a Target Table to Your Transformation Flow](../create-or-add-a-target-table-to-your-transformation-flow-0950746.md).

    > ### Note:  
    > It can only be a local table \(file\) and *Delete All Before Loading* is not supported.

7.  Review the properties of your transformation flow, save and deploy it. See [Creating a Transformation Flow](../creating-a-transformation-flow-f7161e6.md).

    > ### Note:  
    > The transformation will be saved in the object store. While deploying, a virtual procedure will be created to enable the runtime in the file space.

8.  You can share the target local table \(file\) to another space, including to a space dedicated to SAP HANA Database \(Disk and In-Memory\) storage.
9.  More flow analysis options are available in the transformation flow monitor via the *Data Integration Monitor*:

    -   Simulate a run that doesn't save changes in the target table by clicking *Simulate Run*. Simulating allows you to test a transformation flow and see if you get the desired outcome. Based on the result, you can decide to deploy the flow, resolve errors, or to optimize the flow to improve performances.
    -   Download a PLV file of a visual map of the operators and their relationships and hierarchies by clicking *Generate a SQL Analyzer Plan File*. The plan file contains detailed information about your data model that you can download for further analysis. Analyzing this file allows you to resolve errors and enhance the transformation flow performances.

    For more information, see [Explore Transformation Flows](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/7588192bf4cd4e3db43704239ba4d366.html "Use Run with Settings to explore graphical or SQL views and the entities they consume in a transformation flow.") :arrow_upper_right:


