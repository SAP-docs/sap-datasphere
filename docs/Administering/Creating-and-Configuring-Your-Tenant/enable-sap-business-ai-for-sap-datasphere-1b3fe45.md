<!-- loio1b3fe45f38df4db1a9cda97a5a7bcdaf -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Enable SAP Business AI for SAP Datasphere

SAP Business AI is a fully managed service by SAP that allows you to integrate artificial intelligence \(AI\) models in different business solutions. SAP Business AI provides a simple and easy-to-use API with various endpoints that you can use in your solution for different tasks such as text generation, summarization, language translation, creative content development.

<a name="loio194ad917defc4979b30bdf6b0dcb522e"/>

<!-- loio194ad917defc4979b30bdf6b0dcb522e -->

## Enable SAP Business AI

SAP Business AI is integrated to generate AI content recommendations in various areas of SAP Datasphere. The integration uses AI models with prompts that are preconfigured to use input parameters to generate AI content recommendations.



<a name="loio194ad917defc4979b30bdf6b0dcb522e__prereq_txf_gm1_2dc"/>

## Prerequisites

> ### Note:  
> Conversations using Joule in SAP DatasphereSAP Datasphere are available in English only.

-   Your SAP Datasphere tenant is on a landscape that supports SAP Business AI. See SAP Note [https://me.sap.com/notes/0003491182](https://me.sap.com/notes/https://me.sap.com/notes/0003491182).
-   You've purchased the **SAP AI Units** license. For more information about **SAP AI Units** license, contact your Account Executive.
-   To activate an SAP Business AI feature, you need the tenant administrator role.
-   You could have access to the *AI Services* tab, but it's possible that the tenant has not been activated with SAP Business AI yet, or SAP Business AI features are not supported yet. For more information, see SAP Note [https://me.sap.com/notes/0003522010](https://me.sap.com/notes/https://me.sap.com/notes/0003522010).



<a name="loio194ad917defc4979b30bdf6b0dcb522e__steps_nxc_hc4_sdc"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span>*System* \> *Configuration*.

2.  Click the *AI Services* tab.

3.  In the AI Features section, check the options that you want to use.

    -   *AI-Assisted Catalog Content Generation - AI-Enhanced Metadata Enrichment* - Generate asset summaries and descriptions, and assign tag relationships. See [Enriching and Managing Catalog Assets](https://help.sap.com/viewer/97d1d2f0e35d410c893e95a5ff3bee6f/DEV_CURRENT/en-US/7ed60a094f2a464da6a8d75e5bfed9d5.html "To help catalog users quickly find and evaluate assets, you can enrich the assets by editing their names, adding both short and long descriptions, and adding relationships with tags, terms, and KPIs. You can also review the functional and publication status of the assets to ensure they are well-maintained and accessible.") :arrow_upper_right: and [Manage Tag Relationships for Assets](https://help.sap.com/viewer/97d1d2f0e35d410c893e95a5ff3bee6f/DEV_CURRENT/en-US/bb608dd2a4dc402889351c4303a173a4.html "On the Semantic Enrichment tab of the asset details page, you can add, edit, or remove tags.") :arrow_upper_right:.
    -   *AI-Assisted Natural Language Search - AI-Enhanced Metadata Discovery* - Enter your search string in natural language and SAP Datasphere interprets your phrase and filters your results appropriately. See [Natural Language Search](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/04170c64c1004fc58d7f235aea0e4970.html "If natural language search is enabled on your tenant (and you have the appropriate role), the search field will propose example natural language strings that are appropriate to your current filter context. Select an example string or enter your own and SAP Datasphere will interpret it and filter your results appropriately.") :arrow_upper_right:.

4.  Click *Save*.




<a name="loio194ad917defc4979b30bdf6b0dcb522e__postreq_mmz_t1c_tdc"/>

## Next Steps

You can see this icon indicating that SAP Business AI is available for authorized users in the header area: <span class="SAP-icons-V5"></span>

To use SAP Business AI features, users need to have the *DW AI Consumer* role or another global role that grants the *Data Warehouse AI Consumption* privilege \(see [Assign Users to a Role](../Managing-Users-and-Roles/assign-users-to-a-role-57a7880.md)\).

