<!-- loio169ba34e19744362be25a4325de8d10c -->

# Schedule a Data Integration Task \(with Cron Expression\)

Schedule data integration tasks such as data replication, data persistence, or data flow runs or task chains runs, by entering directly a cron expression.



<a name="loio169ba34e19744362be25a4325de8d10c__prereq_xp3_y2m_tnb"/>

## Prerequisites

-   With the `DW Integrator` role you can create, change, or delete a schedule and let the scheduling component of SAP Datasphere run tasks on your behalf. For data flows, you need the `DW Integrator` role along with the `DW Viewer` or the `DW Modeler` role.

-   SAP Datasphere. In your profile settings under *Schedule Consent Settings*, you can give and revoke your consent to SAP Datasphere to run your scheduled tasks in the future. Note that when you don't give your consent or revoke your consent, tasks that you own won't be executed but will fail.

    > ### Note:  
    > Your consent is valid for 365 days. After the consent has expired, a log informs you that the tasks for which you own the schedule won’t be executed anymore. Renew your consent to resume task execution according to the schedules. Additionally, in To run recurring scheduled tasks on your behalf, you need to authorize the job scheduling component of *Data Integration Monitor*, a warning message appears 10 days before the expiry of consent.

    For more information, see [Changing SAP Datasphere Settings](https://help.sap.com/viewer/ac696daa26f0413db39626bc2971e6c2/DEV_CURRENT/en-US/1084796d09464e78870f32cab8584dfc.html "To view and edit your user profile settings, click your user icon in the shell bar and select Settings. You can control various aspects of the user experience of SAP Datasphere and set data privacy and task scheduling consent options.") :arrow_upper_right:.




<a name="loio169ba34e19744362be25a4325de8d10c__context_xqq_qft_m4b"/>

## Context

The job scheduling component of SAP Datasphere runs scheduled tasks on behalf of the owner of the schedule. By default, the user who creates a schedule is the owner of the schedule. You can takeover the ownership, however, if required. Scheduled tasks run in the background according to the settings defined in the schedule.

> ### Note:  
> By default, time in the monitors and in the scheduling dialog is specified in Coordinated Universal Time \(UTC\).



## Procedure

1.  Go to *Data Integration Monitor*.

2.  Select your space.

3.  Open the monitor for the object for which you want to schedule a task.

4.  If you haven't authorized SAP DatasphereTo run recurring scheduled tasks on your behalf, you need to authorize the yet to run your scheduled tasks for you, you will see a message at the top of the monitor asking for your consent. Give your consent.

5.  Select the object for which you want to schedule a task.

6.  Click *Schedule* \> *Create Schedule* 

    You can also use schedules to automate actions on objects created from the Data Builder

    The *Create Schedule* window opens.

    > ### Note:  
    > Tasks for which you own a schedule without having authorized SAP Datasphere to run scheduled tasks on your behalf before won't be executed but will fail.

7.  In the *Frequency* area, select *Cron Expression* from the *Enter As* dropdown list.

8.  Define when the task will be run by using the unix-cron string format \(\* \* \* \* \*\) in the five following fields: *Minute*, *Hour*, *Day \(Month\)*, *Month* and *Day \(Week\)*.

    Either enter the cron expression directly in the fields or copy it from another source to the cron expression area by selecting one of the five fields and pasting it.


    <table>
    <tr>
    <th valign="top">

    Syntax
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    x
    
    </td>
    <td valign="top">
    
    Where x is any number in the following range:

    -   *Minute* – 0-59

    -   *Hour* – 0-23

    -   *Day \(Month\)* – 1-31

    -   *Month* – 1-12

    -   *Day \(Week\)* – 0-6



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    x,y
    
    </td>
    <td valign="top">
    
    Where x and y are two or more values of a list separated by a comma.

    Example: 4,5,6 in the *Month* field is equivalent to "April, May and June".

    Valid in: All fields except *Minute*
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    x-y
    
    </td>
    <td valign="top">
    
    Where x and y are the first and last values of a range separated by a dash.

    Example: 1-5 in the *Day \(Week\)* field is equivalent to "from Monday to Friday".

    Valid in: All fields except *Minute*
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    \*/x
    
    </td>
    <td valign="top">
    
    Where \* is all possible values and x is the step value, separated by a slash.

    Example: \*/3 in the *Hour* field is equivalent to 0,3,6,9,12,15,18,21. The asterisk \(\*\) specifies "every hour" but the /3 means "every 3 hours".

    Valid in: All fields except *Minute*
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    a-b/x
    
    </td>
    <td valign="top">
    
    Where a and b are the first and last values of a range and where x is the step value.

    Example: 1-15/2 in the *Day \(Month\)* field is equivalent to 1,3,5,7,9,11,13,15. 1-15 specifies "from day 1 to day 15" of the month but /2 means "every 2 days".

    Valid in: All fields except *Minute*
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    \*
    
    </td>
    <td valign="top">
    
    Where the asterisk is all possible values for the field.

    Example: an asterisk in the *Hour* field is equivalent to "every hour."

    Valid in: All fields except *Minute*
    
    </td>
    </tr>
    </table>
    
    **Examples of cron expressions:**


    <table>
    <tr>
    <th valign="top">

    Expression
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    0 0 1-3 \* \*
    
    </td>
    <td valign="top">
    
    The task runs the first 3 days of each month at 00:00 \(UTC\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    0 18 1,15,25 \* \*
    
    </td>
    <td valign="top">
    
    The task runs every 1st, 15th and 25th of each month at 6:00 PM \(UTC\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    0 8 \*/1 \* 1-5
    
    </td>
    <td valign="top">
    
    The task runs from Monday to Friday at 8:00 AM \(UTC\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    0 2-8/2 \*/1 \* 1-5
    
    </td>
    <td valign="top">
    
    The task runs every 2 hours between 2:00 AM \(UTC\) and 8:00 AM \(UTC\), from Monday to Friday.
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > You can copy to the clipboard the cron expression you've entered by clicking the copy icon button next to the cron expression.

9.  In the *Start Date* area, specify a date if you want to the change the default start date, which is the current date.

10. Optionally, in the *End Date* area, specify a date. If you do not specify an end date, the schedule runs indefinitely.

11. In the right area of the dialog box, you can see a preview of the schedule and when the five next runs are planned. Schedules are created in Coordinated Universal Time \(UTC\) but you can also view the next runs in local time.

12. Click *Create* to create the schedule.




<a name="loio169ba34e19744362be25a4325de8d10c__result_lpd_421_k4b"/>

## Results

The column *Frequency* shows the status *Scheduled*. By clicking the status you can display the scheduling settings.

The column *Schedule Owners* displays the name of the current schedule owner.

The *Next Run* colums shows the start date and time of the next run according to the scheduling settings.

As long as the consent from the owner of the schedule hasn't expired the task will run in the background. You can access the log by selecting the relevant object and clicking ![](images/Remote_Table_Logs_Button_a6170ee.png).



<a name="loio169ba34e19744362be25a4325de8d10c__postreq_k4l_zlf_h4b"/>

## Next Steps

Once a schedule is defined, you can adjust the scheduling settings at any time selecting *Schedule* \> *Edit Schedule*. The next run of the task will use the adjusted scheduling settings.

The schedule can be removed at any time via the menu *Schedule* \> *Delete Schedule* with the result that no new run will start anymore for the task. The *Next Run* colum gets cleared.

You may also pause and then later resume execution of scheduled tasks via the menu *Schedule* \> *Pause Schedule* option. See [Pause or Resume a Scheduled Task](pause-or-resume-a-scheduled-task-5eb55cb.md) for more information.

