<!-- loio1b3fe45f38df4db1a9cda97a5a7bcdaf -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Enable SAP Business AI for SAP Datasphere

SAP Business AI is a fully managed service by SAP that allows you to integrate artificial intelligence \(AI\) models in different business solutions. SAP Business AI provides a simple and easy-to-use API with various endpoints that you can use in your solution for different tasks such as text generation, summarization, language translation, creative content development.

<a name="loio194ad917defc4979b30bdf6b0dcb522e"/>

<!-- loio194ad917defc4979b30bdf6b0dcb522e -->

## Enable SAP Business AI

SAP Business AI is integrated to generate AI content recommendations in various areas of SAP Datasphere. The integration uses AI models with prompts that are preconfigured to use input parameters to generate AI content recommendations. For example, you might want to show all objects that have been created by a specific user in the past three months.



<a name="loio194ad917defc4979b30bdf6b0dcb522e__prereq_txf_gm1_2dc"/>

## Prerequisites

-   Your SAP Datasphere tenant is on a landscape that supports SAP Business AI. See SAP Note [0003437766](https://me.sap.com/notes/0003437766).
-   You've purchased the **AI units** license. For more information about **AI units** license, contact your Account Executive.
-   To activate an SAP Business AI feature, you need the*DW Administrator* role.
-   You could have access to the *AI Services* tab, but it's possible that the tenant has not been activated with SAP Business AI yet, or SAP Business AI features are not supported yet. For more information, see SAP Note [0003522010](https://me.sap.com/notes/0003522010).



<a name="loio194ad917defc4979b30bdf6b0dcb522e__steps_nxc_hc4_sdc"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span>*System* \> *Configuration*.

2.  Click the *AI Services* tab.

3.  In the AI Features section, check the options that you want to use.

    -   *AI-Assisted Catalog Content Generation - AI-Enhanced Metadata Enrichment* - Generate asset summaries and descriptions, and assign tag relationships. See [Enriching and Managing Catalog Assets](https://help.sap.com/viewer/aca3ccb4b2f84eb8b6154e8fd2812c0e/cloud/en-US/7ed60a094f2a464da6a8d75e5bfed9d5.html "To help catalog users quickly find and evaluate assets, you can enrich the assets by editing their names, adding both short and long descriptions, and adding relationships with terms, KPIs, and tags. You can also review the functional and publication status of the assets to ensure they are well-maintained and accessible.") :arrow_upper_right: and [Manage Tag Relationships for Assets](https://help.sap.com/viewer/aca3ccb4b2f84eb8b6154e8fd2812c0e/cloud/en-US/bb608dd2a4dc402889351c4303a173a4.html "On the Semantic Enrichment tab of the asset details page, you can add, edit, or remove tags.") :arrow_upper_right:.
    -   *AI-Assisted Natural Language Search - AI-Enhanced Metadata Discovery* - Enter your search string in natural language and SAP Datasphere interprets your phrase and filters your results appropriately. See [Natural Language Search](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/04170c64c1004fc58d7f235aea0e4970.html "If natural language search is enabled on your tenant (and you have the appropriate role), the search field will propose example natural language strings that are appropriate to your current filter context. Select an example string or enter your own and SAP Datasphere will interpret it and filter your results appropriately.") :arrow_upper_right:.

4.  Click *Save*.

5.  Grant the *DW AI Consumer* privilege to users whom you want to access SAP Business AI features \(see [Assign Users to a Role](../Managing-Users-and-Roles/assign-users-to-a-role-57a7880.md) \).

    Users who have been granted the privilege will see this icon in areas of SAP Datasphere where AI is available for use: <span class="SAP-icons-V5"></span>


