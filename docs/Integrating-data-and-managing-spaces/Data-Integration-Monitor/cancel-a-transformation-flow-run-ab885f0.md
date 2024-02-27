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


