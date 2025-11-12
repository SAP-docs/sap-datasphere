<!-- loio7ff6a4e584a345a88d002c18c1fc321e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Configure Email Notification

Set up email notification of users for completion of task chain runs and, optionally, additional notification for completion of individual tasks in the task chain.



<a name="loio7ff6a4e584a345a88d002c18c1fc321e__prereq_fxg_y22_xfc"/>

## Prerequisites

You need to first deploy a task chain before you can set up email notification for its successful completion or failure. After setting up notification for the entire task chain run, you may also configure additional notifications for completion of individual tasks run within the task chain. For each of these additional notifications you can specify the subject and message body, however, these individual task notifications will reuse the email recipient list set up for notification of the complete task chain's run. To add these additional notifications, you can drag the Notification Task object \(<span class="SAP-icons-V5"></span>\) from the task chain toolbar to anywhere within the sequence of tasks already included in a task chain. You can then define the subject and message for this specific task notification within the *Email Notifications* section of the task chain's *Properties* panel.

> ### Note:  
> The DW Integrator role is required to set up email notification for completion of task chain runs. The *Email Notifications* section of the task chain's *Properties* panel will not appear if you do not have this privilege assigned. For more information, see [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. In addition to the DW Integrator role, when setting up email notifications, either the Team.Read or User.Read privilege is also required to display and add notification recipients from a list of current tenant members.



## Context

For security and data privacy reasons, when you export a task chain to a CSN/JSON file, the recipient list for email notification is not exported. For more information on exporting objects, see [Exporting Objects to a CSN/JSON File](../Creating-Finding-Sharing-Objects/exporting-objects-to-a-csn-json-file-3916101.md). Similarly, when you transport a task chain to another tenant, the recipient list for email notification is also not exported to the new tenant. For more information on transfering content between tenants, see [Transporting Content Between Tenants](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/df12666cf98e41248ef2251c564b0166.html "Users with an administrator or space administrator role can use the Transport app to transfer content between tenants via a private cloud storage area.") :arrow_upper_right:.



## Procedure

1.  In the *Email Notifications* section of the *Properties* panel, select when you want notifications to be sent for the current task chain. You can choose from the following options:

    -   Send email notification only when the run has completed with an error.

    -   Send email notification only when the run has completed successfully.

    -   Send email notification when the run has completed.


    The *Email Notifications* section expands to show details of the email notification message to be sent to users on completion of task chain runs.

    ![](images/Email_Notification_Setup_d5f7c97.png)

    The notification setup includes a default template you can customize for both the email message subject and body text. You can choose to send notifications to other tenant users or specify email addresses of other users to receive notifications \(up to 20 recipients total\). Email addresses must be in the same domain as the tenant owner.

    > ### Note:  
    > Task chains must also first be deployed before you can select or specify recipients to receive notifications. After setting up notification for the entire task chain run, you may also configure additional notifications for completion of individual tasks run within the task chain by dragging the Notification Task object \(<span class="SAP-icons-V5"></span>\) from the toolbar to anywhere within the sequence of tasks already included in a task chain. For each of these additional notifications you can specify the subject and message body, however, these individual task notifications will reuse the email recipient list set up for notification of the complete task chain's run. After creating a recipient list, you can even turn off notifications for the whole task chain afterwards and any notification tasks you've defined will still send out their notifications.

2.  Click the <span class="SAP-icons-V5"></span> link on the right side of the *Recipient Email Address* field to open a popup dialog in which you can add recipients of task chain notification email messages.

    ![](images/Recipients_List_527a05c.png)

    From this dialog, you can select member users of the same tenant or click the *Others* tab to specify email addresses of other users you want to receive notifications \(up to 20 total recipients\). Email addresses must match the domain of the tenant owner, for example, jdoe@sap.com. After saving your selections, the display returns to the *Properties* panel, showing the selected users in the *Recipient Email Address* field.

    > ### Note:  
    > When setting up email notification, either the Team.Read or User.Read privilege is required to be able to display and add notification recipients from the list of current tenant members. If you do not have this privilege assigned, you can still add recipients manually from the *Others* tab.

3.  Review the default email subject and message body text and make any updates to either the text or placeholder variables used in the notification email message sent for the current task chain.

    Placeholder variables within the subject and message fields are enclosed by $$ characters, for example, $$status$$. You can click the <span class="SAP-icons-V5"></span> icon to display a list of available placeholder variable names you may include in either the email subject or message body text fields.

    > ### Note:  
    > Changes you make to the email notification template are saved when you redeploy the updated task chain that has email notification subject and body text template changes. When the task chain is run and notification emails are sent out, placeholder variables in the notification template will be replaced with actual values available at runtime.

4.  After setting up notification for the entire task chain run, you may also configure additional notifications for completion of individual tasks run within the task chain by dragging the Notification Task object \(<span class="SAP-icons-V5"></span>\) from the toolbar to anywhere within the sequence of tasks already included in a task chain.

    For each of these additional notifications you can specify the subject and message body, however, these individual task notifications will reuse the email recipient list set up for notification of the complete task chain's run.


