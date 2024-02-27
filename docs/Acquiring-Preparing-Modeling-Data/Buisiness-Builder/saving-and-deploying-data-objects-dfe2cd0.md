<!-- loiodfe2cd0806ca44838d336aca47916e99 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Saving and Deploying Data Objects

When you save an object, it is stored in the SAP Datasphere repository, which contains the design-time definitions of all your objects. When you deploy it, you are creating a run-time version for use in the SAP Datasphere database.

Design-time objects do not contain any data, but you can preview the data they will contain when they are deployed to the run-time environment. You can save an object even if it contains validation errors.

In the Business Builder, all objects apart from the perspective are just saved.

To review the current status of a perspective, open it in its editor and look for the *Deployment Status* property, which can have the following values:

-   <span class="SAP-icons-V5"></span> \(Not Deployed\) - The object has never been deployed and exists only as a design-time artifact.
-   :clock3: - The object is deployed to the run-time database and its design-time and run-time versions are identical.
-   <span class="SAP-icons-V5"></span> \(Changes to Deploy\) - The design-time version of the object contains changes that need to be deployed to make them available in the run-time.
-   <span class="FPA-icons-V3"></span> \(Design-Time Error\) - The deployment process failed and you should try to deploy again.

When you deploy a perspective, you create a run-time version, which can be used by other run-time objects and consumed in stories in SAP Analytics Cloud, or any other BI client.

You can always save your changes but you can deploy only if your Space isn't locked. Your Space Administrator can unlock the Space.

The run-time database server might be unavailable under exceptional circumstances. In this case, a message strip is displayed informing you of the database status and the following features are disabled:

-   *Import from Connection*
-   *Deploy*
-   *Preview Data*
-   *Log Viewer*

You can solve this problem by waiting a few minutes and refreshing your web browser. If the problem persists, [open a support ticket](https://launchpad.support.sap.com/#incident/solution).

