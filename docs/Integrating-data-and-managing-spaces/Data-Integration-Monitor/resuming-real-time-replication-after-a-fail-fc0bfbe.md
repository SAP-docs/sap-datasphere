<!-- loiofc0bfbe875cf4e2eb83a51aa00047f9c -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Resuming Real-Time Replication After a Fail

You want to resume a real-time replication after it has failed, once you have corrected the error.



## Context

It can occur that your real-time replication has been paused with errors. To resume your real-time replication, you need to check the relevant log in the details screen of the relevant remote table to identify what is the error and how to solve it. Once the error has been corrected, use the *Retry* button to resume the real-time replication:



## Procedure

1.  Go to the Details screen of the remote table using the button <span class="FPA-icons"></span> Remote Table Logs.

2.  Check the log details and correct the error.

3.  Click retry to resume the real-time replication.

4.  Refresh your screen.

    The status of your real-time replication is now back to active.

    > ### Note:  
    > The *Retry* button must be used once you’ve corrected the errors. It does not serve to correct the error itself but it serves to resume the real-time replication only. It corresponds to the RETRY statement as available in SAP HANA Smart Data Integration. For more information, see [PROCESS REMOTE SUBSCRIPTION EXCEPTION Statement](https://help.sap.com/viewer/d60a5abb34d246cdb4ab7a4f6b9e3c93/latest/en-US/cb07e41e35594070a877be6822ccb36a.html).

    > ### Tip:  
    > You might need to consider monitoring the delta queues in the ABAP backend in case of real-time replication exceptions raised in ABAP adapter-based connections \(ABAP, SAP BW, SAP ECC, SAP S/4HANA on premise\).


