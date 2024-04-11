<!-- loioba20892f25744b86a62ae571e3ea6ead -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Edit a Connection

Edit a connection, for example if the setup of the connected remote system changed, if the connection has been imported from another tenant, or if a new feature is available for the connection type after you have created your connection.



This topic contains the following sections:

-   [Use Cases for Editing a Connection](edit-a-connection-ba20892.md#loioba20892f25744b86a62ae571e3ea6ead__section_connection_editing_use_cases)
-   [Restrictions When Editing Connections](edit-a-connection-ba20892.md#loioba20892f25744b86a62ae571e3ea6ead__section_connection_editing_restrictions)
-   [Edit a Connection](edit-a-connection-ba20892.md#loioba20892f25744b86a62ae571e3ea6ead__section_connection_editing)
-   [Add a Connection to a Package](edit-a-connection-ba20892.md#loioba20892f25744b86a62ae571e3ea6ead__section_connection_adding_package)



<a name="loioba20892f25744b86a62ae571e3ea6ead__section_connection_editing_use_cases"/>

## Use Cases for Editing a Connection

You need to edit connections in various cases, for example:

-   In case of password or credential rotation.

-   When there's changes in the setup of the connected remote system

    Changes in the remote system setup must also be made in the connection by updating the corresponding properties, for example changes in the authentication method, host changes, changes in security settings, or changes in the Data Provisioning Agent.

-   When the connection has been imported

    When a connection has been imported into the tenant, it cannot directly be used. You must first complete the connection configuration and provide the credentials to create a runtime version for the connection before you can use it.

-   When you want to add the connection to a package to facilitate transport between tenants

-   When a new feature is supported by the connection type

    For an existing connection that has been created before the connection type supported a new feature, you must re-enter the credentials before you can use the new feature.

-   When you want to change the business name or description




<a name="loioba20892f25744b86a62ae571e3ea6ead__section_connection_editing_restrictions"/>

## Restrictions When Editing Connections



### Connections to Partner Tools

You cannot edit connections to partner tools.



### Connections Using a Data Provisioning Agent

Consider the following when editing a connection which uses a Data Provisioning Agent:

-   When the connection isn't used and its real-time replication status is *Inactive*, you can change any property except for the technical name.

-   When you use the connection and its real-time replication status is *Active*, you can only change the business name and description. If no package has been assigned yet, you can select a package. Note that credential changes are not considered when saving the connection.

    If you want to change other connection properties, pause real-time replication in the *Connections* app, or if required disable real-time replication for all affected remote tables in the *Data Integration Monitor*.

-   When the connection has real-time replication status *Active* but the Data Provisioning Agent is disconnected, you can only change the business name and description. If no package has been assigned yet, you can select a package. Note that credential changes are not considered when saving the connection.

    If you want to change other connection properties, you must first reconnect the agent and pause real-time replication in the *Connections* app, or if required disable real-time replication for all affected remote tables in the *Data Integration Monitor*.

-   When the connection has real-time replication status *Paused*, you can only change a subset of the properties. It depends on the connection type if any properties can be changed at all and if yes which properties can be changed. Note that the user name cannot be changed in this case.

    When the Data Provisioning Agent is disconnected, you need to reconnect the agent or use a different agent to enable editing specific connection properties.




<a name="loioba20892f25744b86a62ae571e3ea6ead__section_connection_editing"/>

## Edit a Connection

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Connections*\), select a space if necessary, and then click the *Local Connections* tab.

2.  Select the relevant connection and click *Edit*.

    > ### Tip:  
    > For imported connections, for example, and for other connections with warning messages, you can click the warning button on the top right corner of the app to select the connection by then clicking the corresponding message title.

3.  Make the required changes.

4.  Re-enter your credentials.

5.  Click *Save*.

6.  Select the connection and click *Validate* to receive detailed status information.




<a name="loioba20892f25744b86a62ae571e3ea6ead__section_connection_adding_package"/>

## Add a Connection to a Package

Users with the *DW Space Administrator* role \(or equivalent privileges\) can create packages in the *Packages* editor. Once a package is created in your space, you can select it when editing a connection.

Packages are used to group related objects in order to facilitate their transport between tenants.

> ### Note:  
> Once a package is selected, it cannot be changed here. Only a user with the DW Space Administrator role \(or equivalent privileges\) can modify a package assignment in the *Packages* editor.

For more information, see [Creating Packages to Export](../Transporting-Content-Between-Tenants/creating-packages-to-export-24aba84.md).

