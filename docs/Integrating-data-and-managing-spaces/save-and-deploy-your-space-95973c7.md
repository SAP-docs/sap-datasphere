<!-- loio95973c709373415ebf42f6446a909924 -->

# Save and Deploy Your Space

When you save a space, it is stored in the SAP Datasphere repository, which contains the design-time definitions of all your spaces. When you deploy a space, you are creating a run-time version for use in the SAP Datasphere database.



<a name="loio95973c709373415ebf42f6446a909924__section_ymj_g2j_42c"/>

## Prerequisites

To save and deploy the changes you've made in your space, you must have a scoped role that grants you access to your space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`-RU-----`\) - To open and update your space in the *Space Management* tool.
-   *Spaces Files* \(`-RU-----`\) - To read and update objects in your space.

The *DW Space Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 



<a name="loio95973c709373415ebf42f6446a909924__section_nyq_b2j_42c"/>

## Space Deployment

The current status of a space is shown in its *Deployment Status* property, which can have the following values:

-   *Not Deployed* - The space has never been deployed and exists only as a design-time version.

-   *Deployed* - The space is deployed to the run-time database and its design-time and run-time versions are identical.

-   *Deploying* - The space is currently being deployed.

-   *Changes to Deploy* - The design-time version of the space contains changes that need to be deployed to make them available in the run-time version.

-   *Design-Time Error* - The design-time version of the space is invalid. You can save a save with design-time errors, but you cannot deploy it. To correct design-time errors, review each of the validation messages in the editor, make the necessary changes, and then save the space.

-   *Run-Time Error* - The run-time version of the space is invalid and can no longer be used. To correct the errors, review each of the validation messages in the editor, make the necessary changes, and then save and deploy the space.


> ### Note:  
> For spaces that have been created before the deploy feature exists, the *Status* area will display “No Information”. Spaces are deployed anyway. If you click *Deploy*, the status will display *Deployed*.

You can also view the date of the last deployment in the *Deployed On* area.

> ### Note:  
> -   When you assign a user to the space, the user becomes active when you save the space. You can view this in the *Active* column of the *Users* area in your space.
> 
> -   Any change that you make in the *Time Data* area of your space is immediately deployed even if you haven’t saved nor deployed the space. A message is displayed in this area, which indicates that the changes are immediately applied
> -   The option *Expose for Consumption by Default* does not need a redeployment to be active.

> ### Note:  
> On rare occasions when the run-time database is not available, an information message is displayed and certain features that depend on the run-time are disabled:
> 
> -   The *Deploy*, *Delete* and *Monitor* buttons or commands are greyed out.
> 
> -   In the *Space Management* start page, dashes \(-\) appear instead of numbers in the bars \(for example, the *Used Disk* bar at the top of the page and in the space tiles\), in the space status area at the top of the page and space status colors are not displayed in the individual space tiles.
> 
> -   In a space page, the *Time Data* area is disabled.

