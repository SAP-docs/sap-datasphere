<!-- loioe5fbe9e2cb93484dab8b1963145e565f -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating an Analytic Model

Create an analytic model as a basis for consumption in SAP Analytics Cloud.



## Context

Analytic models are the analytical foundation for making data ready for consumption in SAP Analytics Cloud. They allow you to create and define multi-dimensional models to provide data for analytical purposes to answer different business questions. Pre-defined measures, hierarchies, filters, parameters, and associations provide flexible and simple navigation through the underlying data.

The sources for analytic models are facts \(or analytical datasets\), which can contain dimensions, texts, and hierarchies.

> ### Note:  
> Some terms and concepts are used differently in analytic models to align more closely with the terminology in SAP Analytics Cloud stories:
> 
> -   "Input parameters” in facts are called “variables” in analytic models.
> -   "Attributes” in facts are called “dimensions” in analytic models.

This graphic shows the role of the analytic model within SAP Datasphere:

![The graphic has an explanatory text.](images/DWC_-_analytic_model_new_db30cbc.png)



## Procedure

1.  From the side navigation, choose *Data Builder*, select a space if necessary, and choose *New Analytic Model* to open the editor.

2.  Drag your source from the Repository and drop it onto the canvas. For more information, see [Add a Source](add-a-source-27075ee.md).

3.  The side panel shows the properties of your analytic model. Complete the missing information as appropriate:


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Business Name
    
    </td>
    <td valign="top">
    
    Enter a descriptive name to help users identify the object. This name can be changed at any time.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Technical Name
    
    </td>
    <td valign="top">
    
    Displays the name used in scripts and code, synchronized by default with the *Business Name*.

    To override the default technical name, enter a new one in the field. Technical names can contain only alphanumeric characters and underscores.

    > ### Note:  
    > Once the object is saved, the technical name can no longer be modified.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Package
    
    </td>
    <td valign="top">
    
    Select the package to which the object belongs.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Status
    
    </td>
    <td valign="top">
    
    \[read-only\] Displays the deployment and error status of the object.

    For more information, see [Saving and Deploying Objects](../Creating-Finding-Sharing-Objects/saving-and-deploying-objects-7c0b560.md).
    
    </td>
    </tr>
    </table>
    
4.  Select your fact source on the canvas to select or deselect any measures, associated dimensions, or attributes in the properties panel on the right. For more information, see [Add a Dimension](add-a-dimension-4caf098.md).

    > ### Note:  
    > Attributes of type ***LargeString*** are not consumable in SAP Analytics Cloud.

5.  When you click on a dimension or the fact source on the canvas, you make several changes:


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Alias
    
    </td>
    <td valign="top">
    
    You can change the alias of this item. The alias is the name that is shown in the story in SAP Analytics Cloud.

    > ### Example:  
    > In many cases you need to have a more specific name for a field than the source provides. For example, the field name is *Costcenter*, but you want to specify if it is to *Receiving Costcenter* or *Sending Costcenter*.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Measures
    
    </td>
    <td valign="top">
    
    You can add or deselect measures.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Associated Dimensions
    
    </td>
    <td valign="top">
    
    You can add or deselect associated dimensions.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Attributes
    
    </td>
    <td valign="top">
    
    You can add or deselect attributes.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Input Parameters
    
    </td>
    <td valign="top">
    
    You can add or deselect input parameters.
    
    </td>
    </tr>
    </table>
    
6.  You can choose <span class="FPA-icons-V3"></span> \(Export\)** \> *Export to CSN/JSON File* to export the definition of your analytic models to a CSN/JSON file. For more information, see [Exporting Objects to a CSN/JSON File](../Creating-Finding-Sharing-Objects/exporting-objects-to-a-csn-json-file-3916101.md).

7.  You can choose <span class="FPA-icons-V3"></span> \(Export\)** \> *Export Support Information* to export information from the runtime CSN for support to analyze it.

8.  You can choose *Preview* to check if the data looks like expected. Here you have two options: there is the simple preview which is available via the context menu in the editor at the analytic model. For more information, see [Viewing or Previewing Data in Data Builder Objects](../viewing-or-previewing-data-in-data-builder-objects-b338e4a.md). And then there is the analytical preview in which you can drill down by rows and columns. For more information, see [Using the Data Preview](using-the-data-preview-9f1fa73.md).

    > ### Note:  
    > When you change an analytic model for which a story has been defined, and you deploy it again, you need to open the story in SAP Analytics Cloud and save it again.


