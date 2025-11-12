<!-- loio5dc4db23d3894b10aca6ade3c666554d -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Configure Email Notification for Replication Flow Failure at Object Level

Set up email notifications to stay informed when individual replication objects fail in a running replication flow.



<a name="loio5dc4db23d3894b10aca6ade3c666554d__prereq_bng_bvq_dgc"/>

## Prerequisites

You must ensure that the following requirements are met:

-   Your replication flow is successfully deployed
-   You must have the DW integrator role to configure the email notification. A user with a DW modeler will see the email configuration but will not be able to change it. For more information, see [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:.



## Context

When a replication flow contains objects that could not be replicated because of an error, you must navigate to the *Data Integration Monitor* \> *Flows* monitor to check for detailed information. To proactively be notified whenever an individual object cannot be replicated, you can configure to receive an email message.



## Procedure

1.  After you have successfully deployed your replication, click the icon *Runtime Email Notification* in the toolbar.

    > ### Note:  
    > The icon is not displayed until you have deployed the replication flow

2.  Configure the email notification:

    1.  Select *Send email notification when a replication flow object has failed* in the notification area.

        > ### Note:  
        > The notification setup includes a default template that you can customize for both the email message subject and body text.

    2.  Click the <span class="SAP-icons-V5"></span> link on the right side of the *Recipient Email Address* field to open a popup dialog in which you can add recipients of the replication flow notification email messages.

        > ### Note:  
        > From this dialog, you can select member users of the same tenant or click the *Others* tab to specify email addresses of other users you want to receive notifications \(up to 20 total recipients\). Email addresses must match the domain of the tenant owner, for example, jdoe@sap.com.

        > ### Tip:  
        > As a best practice, we recommend using Distribution Lists \(DLs\) instead of individual email addresses when configuring email notifications. This ensures continuity, as DLs are easier to manage and are not impacted when individuals leave the organization. Note that you must enable this setting in your email service.

        > ### Caution:  
        > When setting up email notification, either the Team.Read or User.Read privilege is required to be able to display and add notification recipients from the list of current tenant members. If you do not have this privilege assigned, you can still add recipients manually from the *Others* tab.

    3.  Review the default email subject and message body text and make any updates to either the text or placeholder variables used in the notification email message sent for the current replication flow.

        Placeholder variables within the subject and message fields are enclosed by $$ characters, for example, $$status$$. You can click the <span class="SAP-icons-V5"></span> icon to display a list of available placeholder variable names you may include in either the email subject or message body text fields.

    4.  Click *Save*.


