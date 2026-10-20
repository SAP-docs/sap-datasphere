<!-- loio55d92f3d718d4246bca5782325b078b2 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Viewing SAP Analytics Cloud Objects in the Data Pipeline Analyzer

To view SAP Analytics Cloud \(SAC\) objects in the Data Pipeline Analyzer, specific access and authorization requirements must be met.

If you have the required permissions, you can identify SAP Analytics Cloud \(SAC\) stories that are impacted by pipeline issues. Impacted stories are displayed in both the impact summary and the pipeline graph, allowing you to quickly assess downstream business impact and navigate directly to related objects.



## Prerequisites

To view SAC Stories in the *Data Pipeline Analyzer*, you must have

-   A scoped role that grants you access to a space with the following privileges:
    -   -   **Data Warehouse AI Consumption \(–--–E--\)** - To use SAP Business AI features, and thus use the *Generate* button. For more information, see [Generate Summaries of the Data Pipeline Analyzer With AI](generate-summaries-of-the-data-pipeline-analyzer-with-ai-1e72ea2.md)
-   **Data Warehouse Data Integration** \(-**R**------\) or **Data Warehouse Data Builder** \(-R------\) To start the *Data Pipeline Analyzer*.
-   **Catalog Asset**\(-**R**------\): To see any published SAP Analytics Cloud stories in the graph. Users without this privilege will see no SAC container.
-   **Catalog System**\(-**R**------\): To see both published and unpublished stories.

        For more information, see see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:.


-   Access to the space and container hosting the SAC story.
-   If you are connected through SAP Business Data Cloud, the SAP Analytics Cloud tenant must be part of a Business Data Cloud \(BDC\) formation. This configuration enables the discovery of SAC stories that are based on SAP Datasphere models.



## **Viewing and Accessing Information on Related SAP Analytics Cloud Objects**

The *Data Pipeline Analyzer* can display SAC stories that are connected to SAP Datasphere objects.

-   **Navigate from the Impact Summary**: Objects referenced in the AI-generated impact summary are displayed as links. Selecting a link opens the monitoring page for the corresponding pipeline object. For analytical models and exposed views, related SAC stories are included in the impact summary when available and if you have the required privileges. Selecting a story link opens the corresponding catalog asset page.
-   **View SAC story nodes in the pipeline graph**: SAC story nodes returned from the catalog are appended to the right of the pipeline graph \(downstream of the Analytical Model / Exposed View\), inside a single SAC system container box showing the SAC tenant name and folder, mirroring the Impact and Lineage Analysis visualization shown. You can click to <span class="SAP-icons-V5"></span> \(Show Details\) to display and review the object’s properties.



## SAP Analytics Cloud Objects Are Locked or Not Visible

If SAC objects do not appear as expected, verify that the required content exists and that you have the necessary authorizations



### SAC Objects Appear Locked

A locked SAC object indicates that the story exists, but you don't have sufficient permissions to access it. Verify that:

-   You have access to the space and container where the SAC story is stored.
-   You have either the **Catalog Asset** permission or the **Catalog System** permission.



### No SAC Objects Are Displayed

If no related SAC objects are shown in the impact summary or pipeline graph, the SAC story may no longer be available. Verify that:

-   The SAC story still exists.
-   The SAC story is published and accessible.

