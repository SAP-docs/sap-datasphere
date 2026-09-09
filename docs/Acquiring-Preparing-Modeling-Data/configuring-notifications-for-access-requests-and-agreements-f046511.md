<!-- loiof0465112e1394e0894dcb93f64e771c1 -->

# Configuring Notifications for Access Requests and Agreements

You can set up in-app and email notifications for your data product access requests and agreements.



## Prerequisites

To configure notifications for your data product access requests and agreements, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Catalog Asset* \(`–R–––--`\) - To access and edit the *Data Product Access* notification options.

The *Catalog Administrator* global role and the *DW Viewer* role template \(used directly as a global role\) applied together, for example, grant these privileges.For more information, see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 



## Context

You can set up in-app and email notifications for when your access requests have been approved or rejected, when your access agreements are going to expire or have expired, or when your access agreements have ended. Setting up email notifications allows you to know the activity of your access request or agreement even when you aren't using the SAP Datasphere.



## Procedure

1.  Select your user icon in the shell bar and choose *Settings*.

2.  In the *Settings* dialog, select *Notifications*.

3.  Under *Data Product Access*, turn on the *In-App* and *Email* options for the following types of notifications. By default, the in-app option is turned on.

    -   *Data Access Decision*: To receive notifications after a data steward approves or rejects your access requests and after they end your access agreements.
    -   *Expiring Access Agreements*: To receive notifications 30 days, 7 days, and 1 day before your access agreement expires and when they have expired.

4.  When you're done, close the dialog.




## Results

You receive notifications in the shell bar when you're using SAP Business Data Cloud cockpit, in your email inbox, or both.



## Next Steps

When you see the notifications, you can select them to open the *Data Product Access* page, where you can review the details of access request or agreement. See:

-   [Data Product Access Details](data-product-access-details-3145063.md)
-   [Installing Data Products](installing-data-products-605b734.md)

