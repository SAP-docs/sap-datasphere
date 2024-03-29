<!-- loio831a97714dfe4301918afece5a3b380b -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Request Help from SAP Support

You can request help from SAP Product Support by creating a support incident. In many cases, a support user is required to allow an SAP support engineer to log into and troubleshoot your system.

You can create an SAP support incident on the [SAP Support Portal](https://support.sap.com/) \(S-user login required\). For detailed information about what to include in an incident, see SAP Note [2854764](https://launchpad.support.sap.com/#/notes/2854764).

An administrator can make sure that a support user is created in your tenant. Two options are available:

-   An administrator creates the support user.

    Before creating an incident with SAP, proceed as follows:

    1.  In the shell bar, click <span class="SAP-icons-V5"></span> \(*Support*\).

    2.  In the *Support* dialog, click <span class="SAP-icons-V5"></span> *Create Support User* and then choose *OK* to confirm the support user creation.

        An email is automatically sent to SAP Support to notify them of the newly created support user, and it is listed with your other users at *Security* \> *Users*.

        The support user has minimum privileges and does not consume a user license.

        You can assign an appropriate role to the support user \(DW Administrator role\) and add it to the required space.

    3.  Delete the support user when your issue is resolved.


-   An administrator generally allows SAP Product Support to create support users based on incidents.

    Proceed as follows:

    1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** <span class="Belize-icons"></span> \(*Administration*\) ** \> *System Configuration*.

        > ### Note:  
        > If your tenant was provisioned prior to version 2021.03, click <span class="FPA-icons-V3"></span> \(Product Switch\) ** \> ** <span class="FPA-icons-V3"></span> *Analytics*** \> ** *System* \> *Administration* \> *System Configuration*.

    2.  Choose *Edit*.

    3.  Set the *Allow SAP support user creation* setting to *ON*.

    4.  Click *Save*.

        In case of an incident, a support engineer from SAP Product Support can now request and generate a personalized support user for the affected tenant. This user is enabled for multi-factor authentication.

        The support user either has read-only privileges \(DW Viewer role\) or, if requested by the support engineer and confirmed by the customer in the incident, the support user can have the DW Administrator role. The user does not consume a user license.

        The support user will be automatically deleted after two days or after the incident has been closed.



For more information about creating a support user, see SAP Note [2891554](https://launchpad.support.sap.com/#/notes/2891554).

