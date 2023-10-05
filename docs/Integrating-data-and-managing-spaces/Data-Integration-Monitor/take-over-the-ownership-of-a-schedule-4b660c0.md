<!-- loio4b660c0395454bd0923f732eef4ee4b2 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Take Over the Ownership of a Schedule

Per default, the user who creates a task schedule owns the schedule which means that the job scheduling component runs the task on the owner's behalf according to the defined schedule. You can assign the ownership of the schedule to yourself.



<a name="loio4b660c0395454bd0923f732eef4ee4b2__prereq_xp3_y2m_tnb"/>

## Prerequisites

-   With the `DW Integrator` role you can change the schedule and let the scheduling component run tasks on your behalf. For data flows, you need the `DW Integrator` role along with the `DW Viewer` or the `DW Modeler` role.
-   To let the job scheduling component of SAP Datasphere run scheduled tasks on your behalf, you need to give your consent. For more information, see [Changing SAP Datasphere Settings](https://help.sap.com/viewer/d4f3c5a0bb074d09ae9b42b2b9bd7a08/cloud/en-US/1084796d09464e78870f32cab8584dfc.html "To view and edit your user profile settings, click your user icon in the shell bar and select Settings. You can control various aspects of the user experience of SAP Datasphere and set data privacy and task scheduling consent options.") :arrow_upper_right:.




<a name="loio4b660c0395454bd0923f732eef4ee4b2__context_llj_bsq_n4b"/>

## Context

Changing the owner of the schedule is required when the user owning the schedule until now left the organization and the user has been deleted, for example. In such a case the schedule isn't assigned to any user and can't be executed successfully.



## Procedure

1.  Go to *Data Integration Monitor*.

2.  Select your space.

3.  Open the monitor for the relevant object.

4.  If you haven't authorized SAP Datasphere yet to run your scheduled tasks for you, you will see a message at the top of the monitor asking for your consent. Give your consent.

5.  For remote tables and views: Select the object for which you want to schedule a task.

6.  Depending on the object perform the following action:


    <table>
    <tr>
    <th valign="top">

    Object


    
    </th>
    <th valign="top">

    Action


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    **Remote table**


    
    </td>
    <td valign="top">
    
    Select *Schedule Replication* \> *Edit Schedule*.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **View**


    
    </td>
    <td valign="top">
    
    Select *Schedule* \> *Edit Schedule*.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Data flow**


    
    </td>
    <td valign="top">
    
    Select :clock3: *Schedule* \> *Edit Schedule*.

    > ### Note:  
    > You can also find the :clock3: *Schedule* menu on the run details page of a data flow.


    
    </td>
    </tr>
    </table>
    
    The *Edit Schedule* window opens.

    For data flows, you first enter a dialog where you select the relevant data flow before you get to the *Edit Schedule* window.

7.  Click *Assign to Me* and confirm the following message.

8.  Click *OK* to save the schedule.




<a name="loio4b660c0395454bd0923f732eef4ee4b2__result_yc4_3nb_n4b"/>

## Results

The *Owner* field now shows your user ID as the new owner of the schedule. The scheduling component from now own will execute the task on your behalf.

