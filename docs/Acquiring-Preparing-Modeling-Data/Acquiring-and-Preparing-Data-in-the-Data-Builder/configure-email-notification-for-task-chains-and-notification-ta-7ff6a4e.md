<!-- loio7ff6a4e584a345a88d002c18c1fc321e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Configure Email Notification for Task Chains and Notification Tasks

Set up email notification of users for completion of task chain runs and, optionally, additional notification for completion of individual tasks in the task chain.



<a name="loio7ff6a4e584a345a88d002c18c1fc321e__prereq_fxg_y22_xfc"/>

## Prerequisites

You must consider the following prerequisites before you start:

-   Your task chain is successfully deployed.
-   The DW Integrator role is required to set up email notification for completion of task chain runs. The *Email Notifications* section of the task chain's *Properties* panel will not appear if you do not have this privilege assigned. For more information, see [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:.

    In addition to the DW Integrator role, when managing mail lists for email notifications, either the Team.Read or User.Read privilege is also required to display and add notification recipients from a list of current tenant members.

-   The configured email receiver must have enabled the settings "System Notifications" in the user profile settings \(see [Changing SAP Datasphere Settings](https://help.sap.com/viewer/d4f3c5a0bb074d09ae9b42b2b9bd7a08/cloud/en-US/1084796d09464e78870f32cab8584dfc.html "To view and edit your user profile settings, click your user icon in the shell bar and select Settings. You can control various aspects of the user experience of SAP Datasphere and set data privacy and task scheduling consent options.") :arrow_upper_right:\).




## Context

When a task chain run has completed, you can navigate to the *Data Integration Monitor* for *Task Chains* to check for detailed information. To proactively notify users when a task chain has completed successfully or with an error, you can configure to send an email message.

You can set up notification for the entire task chain run, and you can also configure additional notifications for completion of individual tasks run within the task chain.

For security and data privacy reasons, when you export a task chain to a CSN/JSON file, the recipient list for email notification is not exported. For more information on exporting objects, see [Exporting Objects to a CSN/JSON File](../Creating-Finding-Sharing-Objects/exporting-objects-to-a-csn-json-file-3916101.md). Similarly, when you transport a task chain to another tenant, the recipient list for email notification is also not exported to the new tenant. For more information on transferring content between tenants, see [Transporting Content Between Tenants](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/df12666cf98e41248ef2251c564b0166.html "Users with an administrator or space administrator role can use the Transport app to transfer content between tenants via a private cloud storage area.") :arrow_upper_right:.



## Procedure

1.  After you have deployed your task chain, in the *Email Notifications* section of the *Properties* panel, select when you want notifications to be sent for the current task chain. You can choose from the following options:

    -   Do not send any notifications. \(This is the default setting.\)

    -   Send email notification only when the run has completed with an error.

    -   Send email notification only when the run has completed successfully.

    -   Send email notification when the run has completed.


    The *Email Notifications* section expands to show details of the email notification message to be sent to users on completion of task chain runs.

    > ### Note:  
    > The notification setup includes a default template you can customize for both the email message subject and body text.

2.  Click the <span class="SAP-icons-V5"></span> link on the right side of the *Recipient Email Address* field to open the *Select Mail List* dialog in which you can add up to three mail lists containing the recipients of the task chain notification email messages. Select the mail list or mail lists and click *Apply*.

    If there's no appropriate mail list available, click *Manage Mail List* next to the *Recipient Mail List* field to open the *Manage Mail List* dialog. Here, you can create reusable mail lists, or update, or delete existing mail lists if required \(see *Manage Mail Lists* below\).

3.  Review the default email subject and message body text and make any updates to either the text or placeholder variables used in the notification email message sent for the current task chain.

    Placeholder variables within the subject and message fields are enclosed by $$ characters, for example, $$status$$. You can click *Placeholder Info* to display a list of available placeholder variable names you may include in either the email subject or message body text fields. When the task chain is run and notification emails are sent out, placeholder variables in the notification template will be replaced with actual values available at runtime.

    > ### Note:  
    > Changes you make to the email notification subject and body text template are saved when you redeploy the updated task chain.

4.  After setting up notification for the entire task chain run, you may also configure additional notifications for completion of individual tasks run within the task chain by dragging the Notification Task object \(<span class="SAP-icons-V5"></span>\) from the task chain toolbar to anywhere within the sequence of tasks already included in a task chain.

    For each of these additional notifications you can specify the subject and message body within the *Email Notifications* section of the notification's *Properties* panel. However, these individual task notifications will reuse the email recipient list set up for notification of the complete task chain's run.

    > ### Note:  
    > After creating a recipient list, you can even turn off notifications for the whole task chain afterwards and any notification tasks you've defined will still send out their notifications.


<a name="task_smn_22y_ckc"/>

<!-- task\_smn\_22y\_ckc -->

## Manage Mail Lists



## Context

You can create and update mail lists that you can reuse in task chains, notification tasks, and replication flows. You can also delete mail lists if they are not required anymore. You can do any of these tasks from within a task chain or from within a replication flow. The mail lists are centrally stored and available for all task chains, notification tasks, and replication flows in your tenant.



## Procedure

1.  To create a new mail list, click *Manage Mail List*, click *Create* in the *Manage Mail List* dialog, complete the following properties, and click *Save*:


    <table>
    <tr>
    <th valign="top">

    Properties
    
    </th>
    <th valign="top">

    Comments
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Business Name
    
    </td>
    <td valign="top">
    
    The maximum length is 250 characters.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Technical Name
    
    </td>
    <td valign="top">
    
    Displays the name used in scripts and code, synchronized by default with the *Business Name*. The name must be unique and its maximum length is 250 characters..

    > ### Note:  
    > Once the object is saved, the technical name can no longer be modified.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description
    
    </td>
    <td valign="top">
    
    Provide more information to help users understand the object. The maximum length is 1024 characters.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    List Members
    
    </td>
    <td valign="top">
    
    Add the members to your mail list. You can add up to 20 total members to a list. These can be:

    -   *Tenant Members* - Use the <span class="SAP-icons-V5"></span> link to select and add tenant users.
    -   *Others* - Specify the email addresses of users who should receive notifications. The email addresses must be in the same domain as the tenant owner, for example, jdoe@sap.com.

    > ### Note:  
    > Either the Team.Read or User.Read privilege is required to be able to display and add notification recipients from the list of current tenant members. If you do not have this privilege assigned, you can still add recipients manually from the *Others* section.


    
    </td>
    </tr>
    </table>
    
    You can now use and reuse the new mail list across task chains, notification tasks, and replication flows in your tenant.

2.  To update an existing mail list, in the *Manage Mail List* dialog click <span class="FPA-icons-V3"></span> \(Navigation\) for the list you want to update, make the required changes to the members of your list or to business name or description, and click *Update* to save your changes.

3.  To delete one or more mail lists, select them in the *Manage Mail List* dialog and click delete. Note that this will impact other activities where the mail list is used.


