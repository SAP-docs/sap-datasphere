<!-- loioa91c042549fb497384e756d5f5c71fde -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Creating an Entity-Relationship Model

Create an E/R model to import, visualize, edit, and deploy multiple tables and views together. You can use an E/R model to better understand a subset of the entities in your space, and to communicate this information to other stakeholders.



<a name="loioa91c042549fb497384e756d5f5c71fde__prereq_hzf_stt_zgc"/>

## Prerequisites

To create E/R models, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Data Builder* \(`CRUD----`\) - To create, edit and delete E/R models.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.

The *DW Modeler* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 



## Context

An E/R model provides a diagram for arranging your data entities \(tables and views\) in relation to one another. You can:

-   Add entities from the repository or import them from a connection or a CSN file, as well as creating new entities directly.
-   Modify the properties of your entities including adding human-readable business names and creating associations directly in the diagram.
-   Save and deploy all the contents of your model with a single action.

The work that you do in an E/R model benefits all the users in your space as they can use the entities that you import or enhance as sources in their views.

In addition to working with E/R models in the editor, you can also:

-   List, create, read, update, and delete them using the `datasphere` command line interface \(see [Manage Modeling Objects and Tasks via the Command Line](https://help.sap.com/viewer/d0ecd6f297ac40249072a44df0549c1a/cloud/en-US/6f5c65f209004751aa48f9682ee2ec45.html "Users with a modeler role can use the datasphere command line interface to list, create, update, and delete modeling objects.") :arrow_upper_right:\).
-   Export and import them via the secure *Transport* app \(see [Transporting Content Between Tenants](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/df12666cf98e41248ef2251c564b0166.html "Users with an administrator or space administrator role can use the Transport app to transfer content between tenants via a private cloud storage area.") :arrow_upper_right:\).
-   Export and import them via CSN files \(see [Importing and Exporting Objects in CSN/JSON Files](Creating-Finding-Sharing-Objects/importing-and-exporting-objects-in-csn-json-files-f8ff062.md)\).



## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Data Builder*\), select a space if necessary, and click *New ER Model* to open the editor.

2.  Add, import, or create entities in the diagram:

    -   **Add objects from the repository** - Drag entities from the *Repository* tab of the *Source Browser* and drop them onto the diagram \(see [Add Objects from the Repository](add-objects-from-the-repository-13fcecd.md)\).

    -   **Import objects from a connection** - Drag entities from the *Sources* tab of the *Source Browser* and drop them onto the diagram \(see [Import an Object from a Connection or Other Source](import-an-object-from-a-connection-or-other-source-3e6f8f2.md)\).
    -   **Import objects from a CSN/JSON file** \(see [Importing Objects from a CSN/JSON File](Creating-Finding-Sharing-Objects/importing-objects-from-a-csn-json-file-23599e6.md)\).
    -   **Create a table** \(see [Create a Table in an E/R Model](create-a-table-in-an-e-r-model-3939414.md)\).
    -   **Create a view** \(see [Create a View in an E/R Model](create-a-view-in-an-e-r-model-9e547d1.md)\).

3.  Select an entity to access its toolbar:


    <table>
    <tr>
    <th valign="top">

    Button
    
    </th>
    <th valign="top">

    Action
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Add Column\) 
    
    </td>
    <td valign="top">
    
    Add a column to the selected table.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Create View from Selection\)
    
    </td>
    <td valign="top">
    
    Create a view from the selected entity \(see [Create a View in an E/R Model](create-a-view-in-an-e-r-model-9e547d1.md)\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Create Table\)
    
    </td>
    <td valign="top">
    
    Create a table along with an association pointing from the selected entity to the new table \(see [Create a Table in an E/R Model](create-a-table-in-an-e-r-model-3939414.md)\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    :arrow_right:
    
    </td>
    <td valign="top">
    
    Create an association from the selected entity to another entity \(see [Create an Association in an E/R Model Diagram](create-an-association-in-an-e-r-model-diagram-82e6869.md)\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Add Related Entities\)
    
    </td>
    <td valign="top">
    
    Add entities that are related \(by association\) to the selected entity \(see [Add Related Entities to an E/R Model Diagram](add-related-entities-to-an-e-r-model-diagram-bbde0a7.md)\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Preview Data\)
    
    </td>
    <td valign="top">
    
    Preview the data for the selected entity \(see [Viewing Object Data](viewing-object-data-b338e4a.md)\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Impact and Lineage Analysis\)
    
    </td>
    <td valign="top">
    
    Open the Impact and Lineage Analysis diagram. This diagram enables you to understand the lineage and impacts of the selected object. 

    \(see [Impact and Lineage Analysis](impact-and-lineage-analysis-9da4892.md).\)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="SAP-icons-V5"></span> \(Edit Custom CSN Annotations\)
    
    </td>
    <td valign="top">
    
    \[optional\] Click <span class="SAP-icons-V5"></span> \(Edit Custom CSN Annotations\) to open the *Edit Custom CSN Annotations* dialog. 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="SAP-icons-V5"></span> \(Open in New Tab\)
    
    </td>
    <td valign="top">
    
    Open the selected entity in its own editor in a new tab.
    
    </td>
    </tr>
    </table>
    
4.  Edit the selected entity's properties in the *Properties* panel.

5.  Click <span class="FPA-icons-V3"></span> \(Save\) to save your model:

    -   *Save* to save the entities displayed in your E/R model.
    -   *Save As* to create a local a copy of the entities displayed in your E/R model. The model must have been previously saved at least once. The *Save* dialog opens. Enter new business and technical names and click *Save*.

6.  Click <span class="SAP-icons-V5"></span> \(Deploy\) to deploy the entities displayed in your E/R model:

    -   Newly-created entities are deployed for the first time.
    -   Entities that have changes to deploy are re-deployed.

    > ### Note:  
    > The E/R model itself is not deployed and does not have a deployment status.

7.  The tools in the editor toolbar help you work with your object throughout its lifecycle:


    <table>
    <tr>
    <th valign="top">

    Tool
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Save\)
    
    </td>
    <td valign="top">
    
    Save your changes to the design-time repository. You can use *Save As* to create a copy of the object. 

    See [Saving and Deploying Objects](saving-and-deploying-objects-7c0b560.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="SAP-icons-V5"></span> \(Deploy\)
    
    </td>
    <td valign="top">
    
    Deploy your changes to make them available in the run-time environment.

    See [Saving and Deploying Objects](saving-and-deploying-objects-7c0b560.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Source Browser\)
    
    </td>
    <td valign="top">
    
    Show the *Source Browser* panel to drag objects into the E/R model diagram. 

    See [Using the Source Browser](using-the-source-browser-7d2b21d.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Preview Data\)
    
    </td>
    <td valign="top">
    
    Open the *Data Preview* panel to preview data in the selected object.

    See [Viewing Object Data](viewing-object-data-b338e4a.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Undo\) / <span class="FPA-icons-V3"></span> \(Redo\)
    
    </td>
    <td valign="top">
    
    Revert the last change to the object or redo a change you have previously undone.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Add from Repository\)
    
    </td>
    <td valign="top">
    
    Add entities connected to your entity by associations.

    For more information, see [Add Related Entities to an E/R Model Diagram](add-related-entities-to-an-e-r-model-diagram-bbde0a7.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Import\)
    
    </td>
    <td valign="top">
    
    Import entities from a connection or from a CSN file.

    For more information, see [Import an Object from a Connection or Other Source](import-an-object-from-a-connection-or-other-source-3e6f8f2.md) and [Importing Objects from a CSN/JSON File](Creating-Finding-Sharing-Objects/importing-objects-from-a-csn-json-file-23599e6.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Export\)
    
    </td>
    <td valign="top">
    
    Export all the objects in the E/R model to a CSN/JSON file. 

    See [Exporting Objects to a CSN/JSON File](Creating-Finding-Sharing-Objects/exporting-objects-to-a-csn-json-file-3916101.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Versions
    
    </td>
    <td valign="top">
    
    Open the *Version History* dialog for the object. 

    See [Reviewing and Restoring Object Versions](reviewing-and-restoring-object-versions-4f717cc.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Details
    
    </td>
    <td valign="top">
    
    Toggles the display of the *Properties* panel.
    
    </td>
    </tr>
    </table>
    

