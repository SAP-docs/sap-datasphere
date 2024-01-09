<!-- loio4b660c0395454bd0923f732eef4ee4b2 -->

# Take Over the Ownership of a Schedule

Per default, the user who creates a task schedule owns the schedule which means that the job scheduling component runs the task on the owner's behalf according to the defined schedule. You can assign the ownership of the schedule to yourself.



<a name="loio4b660c0395454bd0923f732eef4ee4b2__prereq_xp3_y2m_tnb"/>

## Prerequisites

-   With the `DW Integrator` role you can change the schedule and let the scheduling component run tasks on your behalf. For data flows, you need the `DW Integrator` role along with the `DW Viewer` or the `DW Modeler` role.
-   To let the job scheduling component of SAP Datasphere run scheduled tasks on your behalf, you need to give your consent. For more information, see [Changing SAP Datasphere Settings](https://help.sap.com/viewer/ac696daa26f0413db39626bc2971e6c2/DEV_CURRENT/en-US/1084796d09464e78870f32cab8584dfc.html "To view and edit your user profile settings, click your user icon in the shell bar and select Settings. You can control various aspects of the user experience of SAP Datasphere and set data privacy and task scheduling consent options.") :arrow_upper_right:.




<a name="loio4b660c0395454bd0923f732eef4ee4b2__context_llj_bsq_n4b"/>

## Context

Changing the owner of the schedule is required when the user owning the schedule until now left the organization and the user has been deleted, for example. In such a case the schedule isn't assigned to any user and can't be executed successfully.



## Procedure

1.  Go to *Data Integration Monitor*.

2.  Select your space.

3.  Open the monitor for the relevant object.

4.  If you haven't authorized SAP Datasphere yet to run your scheduled tasks for you, you will see a message at the top of the monitor asking for your consent. Give your consent.

5.  Select the object for which you want to schedule a task.

6.  Select *Schedule* \> *Assign Schedule to me*

7.  Click *OK* to save the schedule.




<a name="loio4b660c0395454bd0923f732eef4ee4b2__result_yc4_3nb_n4b"/>

## Results

The *Owner* field now shows your user ID as the new owner of the schedule. The scheduling component from now own will execute the task on your behalf.

