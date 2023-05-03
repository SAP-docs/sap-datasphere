<!-- loio13fcecd59327407a91777c2e8e111bd7 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Add Objects from the Repository

Drag objects from the *Repository* tab of the *Source Browser* to add them as sources in your data flow, graphical view, SQL view, or intelligent lookup. In an E/R model, you add objects to visualize them together in a diagram and prepare them for use in other editors.



## Procedure

1.  If the *Source Browser* panel is not visible on the left of the screen, click *Source Browser* in the toolbar to show it.

2.  Click the *Repository* tab.

     The *Repository* tab lists all the tables, views, and intelligent lookups that are available in the space \(including objects shared to the space\). The following categories can be available:

    -   *Tables* - Contains all remote and local tables in the space \(see [Acquiring Data in the Data Builder](Acquiring-and-Preparing-Data-in-the-Data-Builder/acquiring-data-in-the-data-builder-1f15a29.md)\).
    -   *Views* - Contains all graphical and SQL views present in the space \(see [Modeling Data in the Data Builder](Modeling-Data-in-the-Data-Builder/modeling-data-in-the-data-builder-5c1e3d4.md)\).

        > ### Note:  
        > You cannot use views with input parameters as sources in a data flow.

    -   *Intelligent Lookups* - Contains all intelligent lookups present in the space \(see [Creating an Intelligent Lookup](creating-an-intelligent-lookup-8f29f80.md)\).
    -   *Shared Objects* - Contains all objects shared to the space \(see [Sharing Tables and Views To Other Spaces](Creating-Finding-Sharing-Objects/sharing-tables-and-views-to-other-spaces-64b318f.md).

3.  Drag the object from the *Repository Browser* and drop it on the diagram.

    ![](images/Add_Source_3a8e699.gif)

    > ### Note:  
    > In an E/R model, you can additionally::
    > 
    > -   Add multiple objects simultaneously, click <span class="FPA-icons"></span> \(Add from Repository\) to open the *Add Repository Object* dialog. Select the objects you want to import and click *OK*.
    > -   Add objects that are related to those already in the diagram \(see [Add Related Entities to an E/R Model Diagram](add-related-entities-to-an-e-r-model-diagram-bbde0a7.md)\).
    > -   Add objects from a CSN file \(see [Importing Objects from a CSN/JSON File](Creating-Finding-Sharing-Objects/importing-objects-from-a-csn-json-file-23599e6.md)\).


