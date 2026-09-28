<!-- loio5dc4db23d3894b10aca6ade3c666554d -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Configure Email Notification for Replication Flow Failure at Object Level

Set up email notifications to stay informed when individual replication objects fail in a running replication flow.



<a name="loio5dc4db23d3894b10aca6ade3c666554d__prereq_bng_bvq_dgc"/>

## Prerequisites

You must ensure that the following requirements are met:

-   Your replication flow is successfully deployed.
-   You must have the DW integrator role to configure the email notification. A user with a DW modeler will see the email configuration but will not be able to change it. For more information, see [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:.

    In addition to the DW Integrator role, when managing mail lists for email notifications, either the Team.Read or User.Read privilege is also required to display and add notification recipients from a list of current tenant members.

-   The configured email receiver must have enabled the settings "System Notifications" in the user profile settings \(see [Changing SAP Datasphere Settings](https://help.sap.com/viewer/d4f3c5a0bb074d09ae9b42b2b9bd7a08/cloud/en-US/1084796d09464e78870f32cab8584dfc.html "To view and edit your user profile settings, click your user icon in the shell bar and select Settings. You can control various aspects of the user experience of SAP Datasphere and set data privacy and task scheduling consent options.") :arrow_upper_right:\).



## Context

When a replication flow contains objects that could not be replicated because of an error, you must navigate to the *Data Integration Monitor* \> *Flows* monitor to check for detailed information. To proactively notify users whenever an individual object cannot be replicated, you can configure to send an email message.



## Procedure

1.  After you have deployed your replication flow, click the icon *Runtime Email Notification* in the toolbar.

    > ### Note:  
    > The icon is not displayed until you have deployed the replication flow.

2.  Configure the email notification:

    1.  Select *Send email notification when a replication flow object has failed* in the notification area.

        > ### Note:  
        > The notification setup includes a default template that you can customize for both the email message subject and body text.

    2.  Click the <span class="SAP-icons-V5"></span> link on the right side of the *Recipient Mail List* field to open the *Select Mail List* dialog in which you can add up to three mail lists containing the recipients of the replication flow notification email messages. Select the mail list or mail lists and click *Apply*.

        If there's no appropriate mail list available, click *Manage Mail List* next to the *Recipient Mail List* field to open the *Manage Mail List* dialog. Here, you can create reusable mail lists, or update, or delete existing mail lists if required \(see *Manage Mail Lists* below\).

    3.  Review the default email subject and message body text and make any updates to either the text or placeholder variables used in the notification email message sent for the current replication flow.

        Placeholder variables within the subject and message fields are enclosed by $$ characters, for example, $$status$$. You can click *Placeholder Info* to display a list of available placeholder variable names you may include in either the email subject or message body text fields. When notification emails are sent out, placeholder variables will be replaced with actual values available at runtime.

    4.  Click *Save*.


<a name="task_d24_byx_ckc"/>

<!-- task\_d24\_byx\_ckc -->

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


