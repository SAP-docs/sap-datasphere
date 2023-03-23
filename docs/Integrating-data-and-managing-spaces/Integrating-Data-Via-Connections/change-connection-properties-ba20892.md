<!-- loioba20892f25744b86a62ae571e3ea6ead -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Change Connection Properties

Select a connection and edit its business name or description, or change its properties if the setup for the source changed.

> ### Note:  
> You cannot change connections to partner tools.

Consider the following when editing a connection which uses a Data Provisioning Agent:

-   When the connection isn't used and its real-time replication status is *Inactive*, you can change any property except for the technical name.

-   When you use the connection and its real-time replication status is *Active*, you can only change the business name and description. Pause real-time replication to enable editing connection properties.

-   When the connection has real-time replication status *Active* but the Data Provisioning Agent is disconnected, you can only change the business name and description. Reconnect the agent and pause the connection to enable editing connection properties.

-   When the connection has real-time replication status *Paused*, you can only change a subset of the properties. It depends on the connection type if any properties can be changed at all and if yes which properties can be changed. Note that the user name cannot be changed in this case.

    When the Data Provisioning Agent is disconnected, you need to reconnect the agent or use a different agent to enable editing specific connection properties.


To change connection properties:

1.  In the side navigation area, click <span class="FPA-icons"></span> \(*Connections*\), select a space if necessary, and then click the *Local Connections* tab.

2.  Select the relevant connecton and click *Edit*.

3.  Do the required changes.

4.  Re-enter your credentials.

5.  Click *Save*.


