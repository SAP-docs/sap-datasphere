<!-- loio0d78ae0ed87c44ff8e8ca00fd981cdab -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Review Data Provisioning Agent Logs

Use the logs to monitor the agent and analyze issues with the agent.



<a name="loio0d78ae0ed87c44ff8e8ca00fd981cdab__prereq_omt_z5w_w4b"/>

## Prerequisites

The logs are written to the database of SAP Datasphere. For more information, see [Enable Access to Data Provisioning Agent Logs](enable-access-to-data-provisioning-agent-logs-9a00dde.md).



## Procedure

1.  From the <span class="SAP-icons"></span> main menu, open *Configuration* \> *Data Integration*.

2.  On the agent’s tile, click *Review Logs*.

    The *Review Agent Logs* dialog initially shows 50 log entries. To load another chunks of 50 entries each, scroll down to the bottom of the dialog and use the *More* button.

3.  To show the complete message for a log entry, click *More* in the *Message* column.

4.  You have the following options to restrict the results in the display of the logs:

    -   Search: In the *<agent name\>* field, enter a search string and click <span class="FPA-icons"></span> \(Search\) to search in the messages of the logs.

    -   Filters: You can filter based on time, message type and log file name. When you’ve made your selection, click *Apply Filters*.

        > ### Note:  
        > If your local time zone differs from the time zone used in the Data Provisioning Agent logs and you're applying a time-based filter, you might get other filter results than expected.


5.  \[optional\] Export the logs as CSV file to your local system. Note that filters and search restrictions will be considered for the exported file.


