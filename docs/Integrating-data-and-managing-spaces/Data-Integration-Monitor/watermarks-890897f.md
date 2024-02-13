<!-- loio890897f00a4944c7a6f90d3816a8d4c6 -->

# Watermarks

When you run a transformation flow that loads delta changes to a target table, the system uses a watermark \(a timestamp\) to track the data that has been transferred.

On the *Delta Capture Settings* tab of the *Data Integration Monitor*, you can view the watermark for a source table. Note that if a transformation flow run does not load delta data to a target table, no source table information is displayed.



<a name="loio890897f00a4944c7a6f90d3816a8d4c6__section_jgb_dky_pzb"/>

## How the System Calculates the Watermark

When you run a transformation flow that loads delta changes to a target table, the system only transfers data that has a change timestamp greater than or equal to the watermark. Once the transformation flow run has completed successfully, the system sets the watermark to the start time of the transformation flow run. Note that if open transactions exist in the source table at the time the transformation flow run started, then the earliest start timestamp of these transactions is used as the watermark.



<a name="loio890897f00a4944c7a6f90d3816a8d4c6__section_jqd_2ky_pzb"/>

## Resetting the Watermark

If you reset a watermark, the system will transfer all data to the target table the next time the transformation flow runs \(using the load type *Initial and Delta*\). This means that you do not need to redeploy the transformation flow and use the load type *Initial Only*.

Resetting the watermark can make sense in the following situations:

-   If a table that can capture delta changes is joined with a second table, and columns in the second table have been updated, you can reset the watermark to ensure that these changes are reflected in records that have already been transferred.

-   If corrupt data is present in the target table, you can reset the watermark for the transformation flow to ensure that the latest data from the source table is loaded to the target table.


You can reset the watermark for a transformation flow in the *Data Integration Monitor*. Open your transformation flow and navigate to the *Delta Capture Settings* tab. To reset the watermark, choose the *Reset Watermark* button.

