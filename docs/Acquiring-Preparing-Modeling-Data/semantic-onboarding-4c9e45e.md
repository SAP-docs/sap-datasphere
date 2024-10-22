<!-- loio4c9e45e19ff14271a65f883e30023736 -->

# Semantic Onboarding

The *Semantic Onboarding* app provides a central entry point to import semantically-rich objects from your SAP systems and the Content Network, as well as the Public Data Marketplace and other marketplace contexts.

This topic contains the following sections:

-   [Import Entities from SAP Systems](semantic-onboarding-4c9e45e.md#loio4c9e45e19ff14271a65f883e30023736__section_sap_systems)
-   [Import Business Content from the Content Network](semantic-onboarding-4c9e45e.md#loio4c9e45e19ff14271a65f883e30023736__section_content_network)
-   [Acquire Data Products from the Public Data Marketplace and Other Contexts](semantic-onboarding-4c9e45e.md#loio4c9e45e19ff14271a65f883e30023736__section_data_products)



<a name="loio4c9e45e19ff14271a65f883e30023736__section_sap_systems"/>

## Import Entities from SAP Systems

Users with the *DW Modeler* role \(or equivalent privileges\) can can use the *Import Entities* wizard to import semantically-rich objects from your SAP S/4HANA Cloud, SAP S/4HANA on-premise, SAP BW∕4HANA, and SAP BW bridge connections. The wizard creates *Business Builder* and *Data Builder* entities \(along with all the objects on which they depend\) in SAP Datasphere.

Click a tile to open the *Import Entities* wizard for that connection type \(see [Importing Objects with Semantics from SAP S/4HANA, SAP BW∕4HANA and SAP BW Bridge](Acquiring-and-Preparing-Data-in-the-Data-Builder/importing-objects-with-semantics-from-sap-s-4hana-sap-bw-4hana-a-361729b.md)\).

Each tile shows the total number of connections of that type available to you across all the spaces you have access to. If you do not have access to a particular type of connection, you must create it or ask a colleague space administrator or integrator to do so:

-   *SAP S/4HANA Cloud* - See [SAP S/4HANA Cloud Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/a98e5ffdf47c44d9a845dca01a18bd82.html "Use an SAP S/4HANA Cloud connection to access or import extraction-enabled ABAP Core Data Services views (ABAP CDS views) from SAP S/4HANA Cloud.") :arrow_upper_right:.
-   *SAP S/4HANA On-Premise* - See [SAP S/4HANA On-Premise Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/a49a1e3cc50f4af89711d8306bdd8f26.html "Use an SAP S/4HANA On-Premise connection to access data from SAP S/4HANA on-premise systems.") :arrow_upper_right:.
-   *SAP BW/4HANA* - See [SAP BW∕4HANA Model Transfer Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/1caba954bc604e00bf8e82e383a46368.html "Use an SAP BW/4HANA Model Transfer connection to import analytic queries from SAP BW∕4HANA with their Composite Providers and InfoObjects.") :arrow_upper_right:.
-   *SAP BW Bridge* - See [SAP BW Bridge Connection](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/03cc8f27d3a44aabad3debaa79be0216.html "In the SAP BW bridge space, a SAP BW bridge connection is being generated.") :arrow_upper_right:.

Click *Open Import Logs* and select a space to view the results of imports in your space.

The left pane contains a list of imports with the start time, duration, and result. Select an import in the left pane to show its log messages.



<a name="loio4c9e45e19ff14271a65f883e30023736__section_content_network"/>

## Import Business Content from the Content Network

Users with the *DW Space Administrator* role \(or equivalent privileges\) can import business content and sample content from SAP and partners from the *Content Network*.

-   *Business Content*: End-to-end business scenarios created by SAP for various industries and lines of business.
-   *3rd Party Content*: End-to-end business scenarios created by SAP partners. Some third-party content has to be purchased in the *SAP Store*.
-   *Samples*: Sample content to get started with SAP Datasphere.

For more information, see [Importing SAP and Partner Business Content from the Content Network](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/400078d689bf4454b3fc977a4e201c2f.html "You can use the Semantic Onboarding app to import business content and sample content from SAP and partners published to the Content Network.") :arrow_upper_right:.



<a name="loio4c9e45e19ff14271a65f883e30023736__section_data_products"/>

## Acquire Data Products from the Public Data Marketplace and Other Contexts

Users with the *DW Modeler* role \(or equivalent privileges\) can acquire data products from data providers and import them into their space to combine with internal data.

Click a tile to open the context in the data marketplace \(see [Searching and Browsing](searching-and-browsing-2dfea3a.md)\).

