<!-- loioab885f05210f4a52aebe8306c8cad083 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Cancel a Transformation Flow Run

You want to cancel a transformation flow that is running.



## Context

You can use the *Cancel Run* button to stop a transformation flow run that is currently running. This button is available until the run ends.



## Procedure

1.  Navigate to *Data Integration Monitor* \> *Flows*.

2.  Navigate to the run details of your transformation flow by clicking <span class="SAP-icons-V5"></span> \(Details\) for the relevant flow.

    The *Run Details* page opens. It shows the runs of the flow in the left panel and their corresponding messages in the right panel. Under *Runs*, you can view the status of the transformation flow runs \(the *Run* activity\) and also the status of any attempts to cancel a transformation flow run \(the *Cancel* activity\).

3.  To stop a run that is currently running, select the relevant run and click the *Cancel Run* button.

    If the run has been canceled successfully, the status of the transformation flow run will have the value *Failed \(Canceled\)*.

    Canceling a transformation flow involves rolling back database transactions. Therefore, it might take some time until the transformation flow is canceled and the status changes to *Failed \(Canceled\)*.

    For a transformation flow in a file space, when you cancel a run, you can:

    -   *Cancel run with rollback*: The run will stop and what has already been processed will be canceled, including parallel changes from other apps. The data is restored to the version it had when the run started.
    -   *Cancel run without rollback*: The run will stop where it is and what has already been processed will be kept, including parallel changes from other apps. Data might be altered. If you restart the run later, it will resume from where it has stopped.

    > ### Caution:  
    > -   Cancelling a run with rollback may create duplicate records for the target table. If this table is used as source in another transformation flow, the run may fail because of duplicate delta records. Reset the watermark on the failing transformation flow to ensure that these changes are reflected in records that have already been transferred. For more information, see [Watermarks](watermarks-890897f.md).
    > -   Cancelling a transformation flow run in *Spark* runtime, if the target table is also used as a delta capture source table, can lead to duplicate records due to the rollback process. These duplicates are identified by the *Change* types. To resolve the issue, reset the watermark and restart the initial load to ensure data consistency and prevent further duplication.


