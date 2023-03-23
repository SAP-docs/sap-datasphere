<!-- loioa864530a2cbf4b95abdf8c6a851ad392 -->

# Pausing and Resuming a Replication Flow Run

You can pause a replication flow run to stop it temporarily and then resume it at any time.

You may want to pause a replication flow run, for example, while a system update is running. When you do so, the flow is stopped in SAP Datasphere, but not in the source. Consequently, the system still keeps track of changes in the source, but does copy them to the target.

> ### Note:  
> If you have many data changes in your source, and if you pause the replication flow for a longer time \(such as several hours\), the logging tables can become quite big.

When you resume the flow, the system replicates all source data changes that happened while the replication flow was paused, which means that the first replication flow run after a pause can take considerably longer than usual.

