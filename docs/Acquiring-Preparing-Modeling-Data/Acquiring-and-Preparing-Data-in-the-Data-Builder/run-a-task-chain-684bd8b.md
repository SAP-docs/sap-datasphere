<!-- loio684bd8b0e5644a38952167f1f112204f -->

# Run a Task Chain

Run a task chain or create a schedule for running a task chain.



## Context

For a task chain to be available for you to run, it must have already been deployed.



## Procedure

1.  Once a task chain has been deployed, you can click the*Run* button to immediately run the task chain.

2.  After you've started a task chain run, you can choose *Task Chains* from the Data Integration Monitor to check its status. For more information, see [Monitoring Task Chains](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/4142201ec1aa49faad89a688a2f1852c.html "Monitor the status and progress of running and previously run task chains.") :arrow_upper_right:.

3.  To create a schedule to run a task chain periodically, at specific times or intervals, you can select the*Schedule* option from the Data Integration Monitor. For more information on scheduling task chain runs, see [Scheduling Data Integration Tasks](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/7fa07621d9c0452a978cb2cc8e4cd2b1.html "Schedule data integration tasks to run periodically at a specified date or time.") :arrow_upper_right:.

    Once a task chain run has started, it will continue running until it has completed all included tasks, unless you cancel the task chain run. Until all tasks in the chain have been completed and are in a non-running state, the task chain itself is considered to be "running". When finished, the overall state or status of the task chain will be reported as “failed” if any task in the chain has "failed". The final status of COMPLETED for a task chain is reported only if all tasks are COMPLETED.

    > ### Note:  
    > After starting a task chain run, you can also choose to cancel it from the *Run Details* display in the *Data Integration Monitor*. For more information, see [Monitoring Task Chains](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/4142201ec1aa49faad89a688a2f1852c.html "Monitor the status and progress of running and previously run task chains.") :arrow_upper_right:.

    When a task chain is run that includes a parallel task chain branch, all the branch tasks are triggered to be run in parallel. The ANY or ALL condition applied to the branch specifies whether ANY or ALL branch tasks must be completed successfully to continue running remaining tasks in the chain.

    For a task chain that includes one or more parallel task branches, after the task run is complete, it may be possible that one or more tasks may be reported in an error state \(in each branch\). For example, in branches where completion of tasks is evaluated with the ANY operator. In that case, if you restart or retry the task chain, SAP Datasphere will then restart previously-failed tasks and run all subsequent tasks that had not yet run. In particular, this means that if a failed task is in a parallel branch which was evaluated with the ANY operator, those tasks in the same branch which had run successfully will not be run again. Only those tasks that have failed will be retried or run again.


