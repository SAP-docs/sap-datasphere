<!-- loio7588192bf4cd4e3db43704239ba4d366 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Explore Transformation Flows

Use *Run with Settings* to explore graphical or SQL views and the entities they consume in a transformation flow.

The *Run with Settings* option provides you with the ability to simulate a run, but also to download a plan file containing statistics and useful information on each entity that composes your view, no matter the complexity of the view. You can analyze each view definition, the consumed views, the local tables and the data sources used by remote tables that compose your data model. You can then use this information to optimize your data model and decide, for example, which view to persist when performance or technical problems such as out-of-memory errors occur.

1.  Go to *Data Integration Monitor* \> *Flows*. Select the view you need to analyze and navigate to the details screen of this view. You need to select a space if you are assigned to several spaces.

2.  Select *Run* \> *Run with Settings*. You have several options:

    -   *Simulate Run*: Simulating a flow allows you to test a transformation flow and see if you get the desired outcome. Based on the result, you can decide to resolve errors or to optimize the flow to improve performances. No changes are saved in the target table.

        > ### Note:  
        > A simulated run will not take the truncate function into account.

        *Generate Explain Plan*: The Explain Plan shows how the selected transformation flow run will be executed and provides a compiled plan in tabular form, listing the operators used to execute a query along with relevant information about them. This lightweight tool can be generated in case of transformation flow run simulation failure or out-of-memory errors when the SQL Analyzer Plan file fails.

        To generate an Explain Plan, you must have the *DWC\_RUNTIME* privilege added to your *DW Administrator* role or custom role. For more information, see [Authorization and Permissions](authorization-and-permissions-e5f9e81.md).

        -   view it by clicking *View Details*. This is possible only if the plan has less than a 1000 rows. If not, only downloading the plan is possible.
        -   download it as a `.csv` file by clicking *Download* in the *Explain Plan* window, or <span class="SAP-icons-V5"></span> \(Download\) in the activity log.

    -   *Generate SQL Analyzer Plan File*: Before using this option, you must consider the following requirements:

        > ### Note:  
        > -   This option is only available to file spaces.
        > -   To download this file, you must have either the roles of:
        > 
        >     -   the scoped role *DW Administrator* with the privileges *DWC\_DATABUILDER \(Read\)* and *DWC\_DATAINTEGRATION \(Read\)*.
        >     -   an additional custom role with the privileges of *Data Warehouse Runtime \(Read\)*, *DWC\_DATABUILDER \(Read\)*, and *DWC\_DATAINTEGRATION \(Read\)*.
        > 
        >     For more information, see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right:.
        > 
        > -   To open this file, you must install a compatible SQL plan visualization tool, such as [SQL Analyzer Tool for SAP HANA](https://help.sap.com/docs/sql-analyzer/sap-hana-sql-analyzer/guide-to-sql-analyzer-tool-for-sap-hana?locale=en-US).
        > -   This option requires additional system resources.

        This file allows you to analyze your transformation flow to resolve errors and enhance its performances. With this option, you create a plan file \(also called `.plv` file\) containing detailed information about your data model that you can download for further analysis. This file provides more details than the *Simulate Run* option.

        > ### Note:  
        > You can select only one flow per download.

        The plan file is stored along with task logs and has a retention period that is the same as the task logs.



