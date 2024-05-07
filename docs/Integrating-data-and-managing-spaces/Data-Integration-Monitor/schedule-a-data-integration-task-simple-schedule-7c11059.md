<!-- loio7c11059ed3314e1fb753736b7867512c -->

# Schedule a Data Integration Task \(Simple Schedule\)

You can schedule or unschedule data integration tasks such as remote data replication, data persistence, data flow, replication flow, or task chains runs. You may also pause and then later resume the run of scheduled tasks.



<a name="loio7c11059ed3314e1fb753736b7867512c__prereq_xp3_y2m_tnb"/>

## Prerequisites

-   With the `DW Integrator` role you can create, change, or delete a schedule and let the scheduling component of SAP Datasphere run tasks on your behalf. For data flows, you need the `DW Integrator` role along with the `DW Viewer` or the `DW Modeler` role.

-   For replication flows, scheduling is possible if all objects in the flow have load type *Initial Only*.

-   To run recurring scheduled tasks on your behalf, you need to authorize the job scheduling component of SAP Datasphere. In your profile settings under *Authorized Consent Settings*, you can give and revoke your consent to SAP Datasphere to run your scheduled tasks in the future. Note that when you don't give your consent or revoke your consent, tasks that you own won't be executed but will fail.

    > ### Note:  
    > Your consent is valid for 365 days. If your consent will expire within the next four weeks, when you attempt to schedule new tasks, SAP Datasphere displays a message warning that your consent is approaching its expiration date. After the consent has expired, a log message informs you that the tasks for which you own the schedule won’t be executed anymore. Renew your consent to resume task execution according to the schedules. Additionally, in *Data Integration Monitor*, a warning message appears four weeks before the expiry of consent.

    For more information, see [Changing SAP Datasphere Settings](https://help.sap.com/viewer/ac696daa26f0413db39626bc2971e6c2/DEV_CURRENT/en-US/1084796d09464e78870f32cab8584dfc.html "To view and edit your user profile settings, click your user icon in the shell bar and select Settings. You can control various aspects of the user experience of SAP Datasphere and set data privacy and task scheduling consent options.") :arrow_upper_right:.




<a name="loio7c11059ed3314e1fb753736b7867512c__context_xqq_qft_m4b"/>

## Context

The job scheduling component of SAP Datasphere runs scheduled tasks on behalf of the owner of the schedule. Per default, the user who creates a schedule is the owner of the schedule. You can takeover the ownership, however, if required. Scheduled tasks run in the background according to the settings defined in the schedule.

> ### Note:  
> By default, time in the monitors and in the scheduling dialog box is specified in your browser's timezone whereas the time specified in the audit log is specified in Coordinated Universal Time \(UTC\).



<a name="loio7c11059ed3314e1fb753736b7867512c__steps_xx4_vyd_h4b"/>

## Procedure

1.  Go to *Data Integration Monitor*.

2.  Select your space.

3.  Open the monitor for the object for which you want to schedule a task.

4.  If you haven't authorized SAP Datasphere yet to run your scheduled tasks for you, you will see a message at the top of the monitor asking for your consent. Give your consent.

5.  Select the object for which you want to schedule a task.

6.  Click *Schedule* \> *Create Schedule* 

    You can also use schedules to automate actions on objects created from the Data Builder

    The *Create Schedule* window opens.

    > ### Note:  
    > Tasks for which you own a schedule without having authorized SAP Datasphere to run scheduled tasks on your behalf before won't be executed but will fail.

7.  Define your scheduling options:


    <table>
    <tr>
    <th valign="top">

    Categories
    
    </th>
    <th valign="top">

    Possible Values
    
    </th>
    <th valign="top">

    Examples
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Frequency*
    
    </td>
    <td valign="top">
    
    -   *Minutes*: Define how often per hour that you want to trigger the scheduled run during the designated time or date range. You can specify scheduled runs every 10, 15, 20, or 30 minutes.
    -   *Hourly*: Define how often you want to trigger the schedule per day \(every 1 to 23 hours of the day\) and the start time.

        Optionally, you can specify an offset from which the tasks will run. For example, so that a task runs every 2 hours starting from 1:30 AM, specify 2 in *Every* and 1:30 in *Starting at \(UTC\)*.

    -   *Daily*: Define how often you want to trigger the schedule per month \(every 1 to 28 days per month\) and the start time.

        By default, the option *Reset Every Month* is not selected, which means that you schedule daily tasks with a fixed frequency \(for example, every two days\) that is not reset on the first day of each month. You can select the option so that the run cycle is reset every month.

    -   *Weekly*: Select which day\(s\) of the week the schedule must be triggered \(multiple selection is allowed\) and the start time.
    -   *Monthly*: Define how often you want to trigger the schedule per year \(every 1 to 11 months of the year\), which day of the month where the schedule must start, and define the start time.


    
    </td>
    <td valign="top">
    
    Let's take a few examples. Imagine that we are in April 14, 2021, it's 9:00 am and you define your schedule without a start and end date:

    -   *Minutes*: You set frequency of scheduled task runs to 15 minutes. Tasks will now be triggered to run every 15 minutes within designated time/date range.
    -   *Hourly*: You select every "5" hours "00" minutes. You need to consider that a cycle run reset will occur every day at 0:00. Next runs will be:

        -   Apr 14, 2021 10:00
        -   Apr 14, 2021 15:00
        -   Apr 14, 2021 20:00
        -   Apr 15, 2021 0:00
        -   Apr 15, 2021 5:00

        If you define that the schedule must run at 0:15 mn, then the next runs will be

        -   Apr 14, 2021 10:15
        -   Apr 14, 2021 15:15
        -   Apr 14, 2021 20:15
        -   Apr 15, 2021 0:15
        -   Apr 15, 2021 5:15

    -   *Daily*: You select every "4" days at "0:00" hours.

        Next runs will be:

        -   April 17, 2021
        -   April 21, 2021
        -   April 25, 2021
        -   April 29, 2021
        -   May 1st, 2021 \(if the option *Reset Every Month* is selected\) or May 3 \(if the option is not selected\)
        -   May 5, 2021 \(if the option *Reset Every Month* is selected\) or May 7 \(if the option is not selected\)

    -   *Monthly*: You select every "5" months on "1"st day of month. You will have a cycle run reset at 1st day of the year. Next runs will be:
        -   Jun 1, 2021 0:00

        -   Nov 1, 2021 0:00
        -   Jan 1, 2022 0:00 \(Cycle run reset\)
        -   Jun 1, 2022 0:00



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Time Range*
    
    </td>
    <td valign="top">
    
    -   *Start Date*: Specify a date if you want to the change the default start date, which is the current date.
    -   *End Date*: Optionally you can specify an end date. Otherwise, the schedule runs indefinitely.


    
    </td>
    <td valign="top">
    
    Now imagine we are still in April 14, 2021, but you set as start date "May 2, 2020" and as end date "March 31, 2021". If we take the same examples as above the next runs will be:

    -   *Daily*:
        -   May 6, 2021
        -   May 11, 2021
        -   May 16, 2021
        -   May 21, 2021
        -   May 26, 2021

    -   *Monthly*:
        -   Jun 1, 2021 0:00
        -   Nov 1, 2021 0:00
        -   Jan 1, 2022 0:00 \(Cycle run reset\)



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Preview*
    
    </td>
    <td valign="top">
    
    You can see a preview of the schedule and when the five next runs are planned.
    
    </td>
    <td valign="top">
    
    Schedules are created in Coordinated Universal Time \(UTC\) but you can also view the next runs in local time.
    
    </td>
    </tr>
    </table>
    
8.  Click *Create* to create the schedule.




<a name="loio7c11059ed3314e1fb753736b7867512c__result_lpd_421_k4b"/>

## Results

The column *Frequency* shows the status *Scheduled*. By clicking the status you can display the scheduling settings.

The column *Schedule Owners* displays the name of the current schedule owner.

The *Next Run* colums shows the start date and time of the next run according to the scheduling settings.

As long as the consent from the owner of the schedule hasn't expired the task will run in the background. You can access the log by selecting the relevant object and clicking ![](images/Remote_Table_Logs_Button_a6170ee.png)*\(Remote Table Logs\)*,*\(Views Logs\)*, or *\(Details\)*.



<a name="loio7c11059ed3314e1fb753736b7867512c__postreq_k4l_zlf_h4b"/>

## Next Steps

Once a schedule is defined, you can adjust the scheduling settings at any time selecting *Schedule* \> *Edit Schedule*. The next run of the task will use the adjusted scheduling settings.

The schedule can be removed at any time via the menu *Schedule* \> *Delete Schedule* with the result that no new run will start anymore for the task. The *Next Run* colum gets cleared.

You may also pause and then later resume execution of scheduled tasks via the menu *Schedule* \> *Pause Schedule* option. See [Pause or Resume a Scheduled Task](pause-or-resume-a-scheduled-task-5eb55cb.md) for more information.

**Related Information**  


[Take Over the Ownership of a Schedule](take-over-the-ownership-of-a-schedule-4b660c0.md "Per default, the user who creates a task schedule owns the schedule which means that the job scheduling component runs the task on the owner's behalf according to the defined schedule. You can assign the ownership of the schedule to yourself.")

