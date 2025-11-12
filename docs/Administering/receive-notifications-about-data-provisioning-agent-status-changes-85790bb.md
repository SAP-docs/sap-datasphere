<!-- loio85790bbfb2644c758e5f2d5a50abfb53 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Receive Notifications About Data Provisioning Agent Status Changes

For a selected SAP HANA Smart Data Integration Data Provisioning Agent, you can configure to get notified when the agent’s status changes from connected to disconnected or the other way round.



<a name="loio85790bbfb2644c758e5f2d5a50abfb53__prereq_omt_z5w_w4b"/>

## Prerequisites

To run recurring scheduled tasks on your behalf, you need to authorize the job scheduling component of SAP Datasphere. In your profile settings under *Schedule Consent Settings*, you can give and revoke your consent to SAP Datasphere to run your scheduled tasks in the future. Note that when you don't give your consent or revoke your consent, tasks that you own won't be executed but will fail.

For more information, see [Changing SAP Datasphere Settings](https://help.sap.com/viewer/d4f3c5a0bb074d09ae9b42b2b9bd7a08/cloud/en-US/1084796d09464e78870f32cab8584dfc.html "To view and edit your user profile settings, click your user icon in the shell bar and select Settings. You can control various aspects of the user experience of SAP Datasphere and set data privacy and task scheduling consent options.") :arrow_upper_right:.



<a name="loio85790bbfb2644c758e5f2d5a50abfb53__context_zyk_qkb_3rb"/>

## Context

A recurring task will check for any status changes according to the configured frequency and send the notifications to the user who is the owner of the configuration. The initial owner is the user who created the configuration. Any user with the appropriate administration privileges can take over the ownership for this task if required, for example in case of vacation replacement or when the previous owner left the department or company.



## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Data Integration*.

2.  Go to the *On-Premise Agents* section and click <span class="SAP-icons-V5"></span> \(menu\) ** \> ** *Configure Sending Notifications*.

3.  If you haven't authorized SAP Datasphere yet to run your scheduled tasks for you, you will see a message at the top of the *Configure Sending Notifications* dialog asking for your consent. Give your consent.

4.  Switch on the *Send Notifications* toggle.

    An additional field *Owner* appears that shows that you have been automatically assigned as the owner of the task.

5.  Select the frequency in which the status of the Data Provisioning Agent should be checked.

6.  Save your configuration.

    This will start the first status check. After the first check, the status check will be performed according to the defined frequency.




<a name="loio85790bbfb2644c758e5f2d5a50abfb53__result_rp2_jnb_3rb"/>

## Results

If the status check finds any status change for the agent, a notification will be sent that you can find by clicking :bell: on the shell bar.

When you click on the notification, you’ll get to the *On-Premise Agents* section in <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Data Integration* where you can start searching for the root cause in case the agent is disconnected.



<a name="loio85790bbfb2644c758e5f2d5a50abfb53__postreq_jdc_g4b_3rb"/>

## Next Steps

If you need to take over the ownership and receive the notifications for an agent’s status changes, go the the *Configure Sending Notifications* dialog as described above, click *Assign to Me* and save the configuration. From now on you will receive the notifications about any status changes for the agent. If you haven’t done so yet, you need to provide your consent before you can take over the ownership.

