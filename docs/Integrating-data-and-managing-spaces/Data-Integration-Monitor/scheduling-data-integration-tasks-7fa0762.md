<!-- loio7fa07621d9c0452a978cb2cc8e4cd2b1 -->

# Scheduling Data Integration Tasks

Schedule data integration tasks to run periodically at a specified date or time.

You can schedule or unschedule data integration tasks such as remote table replication, persisting views, and data flow or task chain execution. You may also pause and then later resume execution of scheduled tasks.

> ### Note:  
> For optimal performance, it is recommended that you consider staggering the scheduled run time of tasks such as data flows and task chains that may contain these tasks. There is a limit on how many tasks can be started at the same time. If you come close to this limit, scheduled task runs may be delayed and, if you go beyond the limit, some scheduled task runs might even be skipped.

Using a dedicated dialog box, you can specify the frequency and time range of the schedule by using a simple form or by directly entering a cron expression.

> ### Note:  
> When you click *Create*, the definition of the schedule that is created and saved is the one that is currently displayed \(either in the *Simple Schedule* area or the *Cron Expression* area\).

> ### Note:  
> Schedules are created in Coordinated Universel Time \(UTC\).

> ### Note:  
> If you create a schedule for a remote table whose data access is *Replicated \(Real-time\)*, the replication type will change from real-time replication to batch replication at the next run of the schedule. The data will no longer be updated in real-time.

