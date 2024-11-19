<!-- loio831a97714dfe4301918afece5a3b380b -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Request Help from SAP Technical Support

You can request help from SAP Technical Support by creating a support incident. In many cases, a support user is required to allow an SAP support engineer to log into and troubleshoot your system.

You can create an SAP support incident on the [SAP Support Portal](https://support.sap.com/) \(S-user login required\). For detailed information about what to include in an incident, see SAP Note [2854764](https://launchpad.support.sap.com/#/notes/2854764).

In SAP Datasphere, users with an administrator role can make sure that a support user is created in the tenant. Two options are available:



<a name="loio831a97714dfe4301918afece5a3b380b__section_pp1_sjc_fdc"/>

## Option 1: Allow SAP Technical Support to Create Support Users for Incidents

To generally allow SAP Technical Support to create support users based on incidents, proceed as follows:

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** <span class="Belize-icons"></span> \(*Administration*\) ** \> *System Configuration*.

    > ### Note:  
    > If your tenant was provisioned prior to version 2021.03, click <span class="FPA-icons-V3"></span> \(Product Switch\) ** \> ** <span class="FPA-icons-V3"></span> *Analytics*** \> ** *System* \> *Administration* \> *System Configuration*.

2.  Choose *Edit*.

3.  Set the *Allow SAP support user creation* setting to *ON*.

4.  Click *Save*.

    In case of an incident, the assigned support engineer from SAP Technical Support can request and generate a personalized support user for the affected tenant. This user is enabled for multi-factor authentication.

    Support engineers can request the support user with one of the following roles:

    -   the global extended role *DW Support User* along with the scoped role *DW Scoped Support User* 

        *DW Support User* gives support users read-only access privileges to all functionalities of SAP Datasphere, enabling them to analyze the incident.

        When support engineers request the *DW Scoped Support User* role, they can specify the spaces that need to be added as scopes to this role. This gives the support user read-only access to these spaces.

    -   the global *DW Administrator* role, if the customer confirms this in the incident


    The support user does not consume a user license, and it will be automatically deleted after two days or after the incident has been closed.




<a name="loio831a97714dfe4301918afece5a3b380b__section_r2h_sjc_fdc"/>

## Option 2: Create Support User for an Incident

Before creating an incident with SAP, proceed as follows:

1.  In the shell bar, click <span class="SAP-icons-V5"></span> \(*Support*\).

2.  In the *Support* dialog, click <span class="SAP-icons-V5"></span> *Create Support User* and then choose *OK* to confirm the support user creation.

    An email is automatically sent to SAP Support to notify them of the newly created support user, and it is listed with your other users at *Security* \> *Users*.

    The support user has minimum privileges and does not consume a user license.

    You can assign an appropriate scoped role to the support user and add the user to the required space, or assign the DW or Catalog Administrator role if required.

3.  Delete the support user when your issue is resolved.


For more information about creating a support user and assign appropriate roles, see SAP Note [2891554](https://launchpad.support.sap.com/#/notes/2891554).

