<!-- loio3f92b46fe0314e8ba60720e409c219fc -->

# Create OAuth2.0 Clients to Authenticate Against SAP Datasphere

Users with an administrator role can create OAuth2.0 clients and provide the client parameters to users who need to connect clients, tools, or apps to SAP Datasphere.

You can create OAuth2.0 clients with:

-   An *Interactive Usage* purpose:
    -   To use the `datasphere` command line interface \([Log into the Command Line Interface via an OAuth Client](https://help.sap.com/viewer/9b8363ae47c347de9a027c0e5567a37a/DEV_CURRENT/en-US/eb7228a171a842fa84e48c899d48c970.html "If an administrator has created an OAuth client (with Purpose set to Interactive Usage or Technical User) for datasphere command line interface users to log into, there are several methods for accessing it.") :arrow_upper_right:\).
    -   To consume data via the OData API \(see [Consume SAP Datasphere Data in SAP Analytics Cloud via an OData Service](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/9de2c660fd3b4db2b89ad25e584e8857.html "You can create an import data connection in SAP Analytics Cloud to consume data from an asset exposed via the SAP Datasphere OData API and consume it in an SAP Analytics Cloud model.") :arrow_upper_right:\).

-   An *API Access* purpose:
    -   To use the SCIM 2.0 API \(see [Create Users and Assign Them to Roles via the SCIM 2.0 API](../Managing-Users-and-Roles/create-users-and-assign-them-to-roles-via-the-scim-2-0-api-1ca8c4a.md)\).
    -   To transport content \(see [Transporting Your Content through SAP Cloud Transport Management](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/05383980f0704c71ab9872360ce45622.html "Integrate SAP Datasphere with SAP Cloud Transport Management service to transport content packages across different landscapes.") :arrow_upper_right: and [api/v1/content](https://help.sap.com/docs/SAP_ANALYTICS_CLOUD/14cac91febef464dbb1efce20e3f1613/eeace13cc37b4eed96064a7c5d8ee493.html) in the *SAP Analytics Cloud REST API Guide*\).
    -   To export a log of user activities to a CSV file \(see [api/v1/audit/activities/exportActivities](https://help.sap.com/docs/SAP_ANALYTICS_CLOUD/14cac91febef464dbb1efce20e3f1613/ca45363ac1de4d669ad4a18115401d5a.html) in the *SAP Analytics Cloud REST API Guide*\).
    -   To allow SAP Signavio to connect securely to SAP systems such as SAP S/4HANA \(see [SAP Signavio Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/4c367de075a44ad7b7a6db576a4a9c82.html "Use the connection to securely integrate SAP systems such as SAP S/4HANA on-premise with SAP Signavio using replication flows for efficient and scalable data replication to SAP Signavio Process Intelligence.") :arrow_upper_right:.\)
    -   To use the `datasphere` command line interface \(`marketplace` commands only\). See [Manage the Data Marketplace via the Command Line](https://help.sap.com/viewer/9b8363ae47c347de9a027c0e5567a37a/DEV_CURRENT/en-US/5a815f6c21e9468eb96d0be95b9d2def.html "Users with a modeler role can use the datasphere command line interface to manage the Data Marketplace.") :arrow_upper_right:


-   A *Technical User* purpose:
    -   To use the SCIM 2.0 API \(see [Create Users and Assign Them to Roles via the SCIM 2.0 API](../Managing-Users-and-Roles/create-users-and-assign-them-to-roles-via-the-scim-2-0-api-1ca8c4a.md)\).
    -   To transport content \(see [Transporting Your Content through SAP Cloud Transport Management](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/05383980f0704c71ab9872360ce45622.html "Integrate SAP Datasphere with SAP Cloud Transport Management service to transport content packages across different landscapes.") :arrow_upper_right: and [api/v1/content](https://help.sap.com/docs/SAP_ANALYTICS_CLOUD/14cac91febef464dbb1efce20e3f1613/eeace13cc37b4eed96064a7c5d8ee493.html) in the *SAP Analytics Cloud REST API Guide*\).
    -   To export a log of user activities to a CSV file \(see [api/v1/audit/activities/exportActivities](https://help.sap.com/docs/SAP_ANALYTICS_CLOUD/14cac91febef464dbb1efce20e3f1613/ca45363ac1de4d669ad4a18115401d5a.html) in the *SAP Analytics Cloud REST API Guide*\).
    -   To allow SAP Signavio to connect securely to SAP systems such as SAP S/4HANA \(see [SAP Signavio Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/4c367de075a44ad7b7a6db576a4a9c82.html "Use the connection to securely integrate SAP systems such as SAP S/4HANA on-premise with SAP Signavio using replication flows for efficient and scalable data replication to SAP Signavio Process Intelligence.") :arrow_upper_right:.\)
    -   To use the `datasphere` command line interface \(`marketplace` commands only\). See [Manage the Data Marketplace via the Command Line](https://help.sap.com/viewer/9b8363ae47c347de9a027c0e5567a37a/DEV_CURRENT/en-US/5a815f6c21e9468eb96d0be95b9d2def.html "Users with a modeler role can use the datasphere command line interface to manage the Data Marketplace.") :arrow_upper_right:
    -   To consume data via the OData API \(see [Consume Data via the OData API](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/7a453609c8694b029493e7d87e0de60a.html "You can connect to the OData API and consume data exposed as views or analytic models in SAP Analytics Cloud and other clients, tools, and apps that are capable of accessing an OData service and authenticating via an OAuth client.") :arrow_upper_right:\).


