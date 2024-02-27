<!-- loioce26fd3da31b414f9482292d3969340a -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define Perspectives

Perspectives are reusable configurations that contain a subset of a consumption models attributes, measures and parameters.



## Context

You can create multiple perspectives for your consumption model which allows for different variants to enable quick validation while modeling. Perspectives can be used to create stories in SAP Analytics Cloud.

You can create a perspective in the *Perspectives* tab of your consumption model or by choosing *Data Preview* and saving your preview as a perspective.

> ### Note:  
> Older perspectives use internal naming conventions for dimensions that are not stable when transporting between tenants. If your perspective has this issue, the *Update Perspective for Transport* option is available at the bottom of its property sheet.
> 
> To make your perspective safe for transport, click this option and then click *Yes* to update its internal dimension names.
> 
> Updating the perspective will break any existing SAP Analytics Cloud stories that consume it, and you will need to reselect the dimension manually in each story.

<a name="task_w4m_nfy_qpb"/>

<!-- task\_w4m\_nfy\_qpb -->

## Define Perspectives From the Data Preview



<a name="task_w4m_nfy_qpb__steps_y4m_nfy_qpb"/>

## Procedure

1.  In your consumption model, choose *Data Preview*.

2.  The context menu <span class="FPA-icons-V3"></span> on a field has various options:

    -   To remove fields from the output but keep it in the perspective: choose *Remove from Output*.
    -   To remove or add fields: choose *Remove from Perspective* or *Add to Perspecive.* 
    -   To sort your fields: choose *Sort*.
    -   To define a filter on the fields: choose *Filter*.
    -   To move a field to a diffenrent position: choose *Move*.
    -   The *Association Context* shows you where the field comes from.

3.  You can also add or remove fields via drag&drop.

4.  To define a filter you can also choose <span class="FPA-icons-V3"></span> *Add Filter* the bar above the data preview. Here you can choose between the simple and the advanced editor.

5.  You can also select more than one field by choosing <span class="FPA-icons-V3"></span> *Multi Select* and then perform the action for multiple fields.

6.  You can also remove a field from the output by chhoosing <span style="font-size:16px;"><span class="FPA-icons-V3"></span></span> *Remove from Output*.

7.  You can define settings for your perspective by choosing <span class="FPA-icons-V3"></span> *Settings*:

    Define your preferences for the

    -   authorizations: this is only available if an authorization scenario has been assigned. You can only assign one authorization scenario per perspective. Assigning it to a perspective allows the authorization scenario to become effective. More information: [Authorization Scenario](authorization-scenario-46d8c42.md)
    -   preview mode: you can choose between the *Validate* and the *Explore* mode.
    -   refresh mode: the data can be refreshed automatically or manually.
    -   row limit: you can specify the number of rows to be retrieved.
    -   attribute display: you can choose it the text, the technical name or the ID is displayed.

8.  Save your perspective by choosing *Save New*. Enter a title and save it.

9.  When you make changes to your perspective, you can save the changes or you can save this changed perspective as a new perspective by choosing *Save As*. You can undo your changes by choosing *Reset*.

10. Switching to other perspectives: When you click on the title of your perspective, you can see the titles of the existing perspectives for this consumption model. From here, you can also open these perspectives.

11. In order to make your perspective consumable, you need to deploy it. Go back to your consumption model, choose the *Perspectives* tab and choose <span class="SAP-icons-V5"></span> *Deploy*. A perspective needs to be deployed in order to be used in a story.


<a name="task_ftv_vfy_qpb"/>

<!-- task\_ftv\_vfy\_qpb -->

## Define Perspectives on the Perspectives Tab



<a name="task_ftv_vfy_qpb__steps_gtv_vfy_qpb"/>

## Procedure

1.  Go to the *Perspectives* tab and choose<span class="FPA-icons-V3"></span> \(New Perspective\) .

2.  Enter a business purpose.

3.  Enter an authorization scenario, if required.

4.  Select your measures by choosing <span class="FPA-icons-V3"></span> \(New\)

5.  Select your attributes by choosing <span class="FPA-icons-V3"></span> \(New\)

6.  Select your hierarchies by choosing <span class="FPA-icons-V3"></span> \(New\)

7.  You can select *Run in Analytical Mode*. When you select this option, the `USE_OLAP_PLAN` hint is sent to the SQL optimizer.

    This may improve view performance, particularly if a union is performed. It is only available if *Expose for Consumption* is enabled.

    For more information, see [HINT Details](https://help.sap.com/viewer/c1d3f60099654ecfb3fe36ac93c121bb/latest/en-US/4ba9edce1f2347a0b9fcda99879c17a1.html) in the *SAP HANA Cloud, SAP HANA Database SQL Reference Guide*.

8.  Save your perspective by choosing *Save*.

9.  When you make changes to your perspective, you can save the changes or you can save this changed perspective as a new perspective by choosing *Save As*. You can undo your changes by choosing *Reset*.

10. In order to make your perspective consumable, you need to deploy it. Go back to the *Perspectives* tab and choose <span class="SAP-icons-V5"></span> *Deploy*. A perspective needs to be deployed in order to be used in a story.




<a name="task_ftv_vfy_qpb__result_bpm_nfy_qpb"/>

## Results

The perspective can be found in the *Repository Explorer*. You can use your perspective in stories in SAP Analytics Cloud.

**Related Information**  


[Previewing Data in Business Builder Objects](previewing-data-in-business-builder-objects-3c58d6e.md "You can check the data in your models in the data preview.")

