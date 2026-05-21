<!-- loio1b3fe45f38df4db1a9cda97a5a7bcdaf -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Enable SAP Business AI for SAP Datasphere

SAP Business AI is a fully managed service by SAP that allows you to integrate artificial intelligence \(AI\) models in different business solutions. SAP Business AI provides a simple and easy-to-use API with various endpoints that you can use in your solution for different tasks such as text generation, summarization, language translation, creative content development. Enable SAP Business AI and Joule for SAP Datasphere to integrate AI content recommendations. This will simplify access to information, automate business processes, and generate AI content recommendations in various areas of SAP Datasphere.



## Prerequisites

-   To enable SAP Business AI, you must have a global role that grants you the following privileges:

    -   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
    -   *System Information* \(`-RU-----`\) - To access the *Configuration* area in the *System* tool.

    The *DW Administrator* global role, for example, grants these privileges. For more information, see [Privileges and Permissions](../Managing-Users-and-Roles/privileges-and-permissions-d7350c6.md) and [Standard Application RolesStandard Roles Delivered with SAP Datasphere](../Managing-Users-and-Roles/standard-application-rolesstandard-roles-delivered-with-sap-datasphere-a50a51d.md). 

-   SAP Datasphere tenant on a landscape supporting SAP Business AI. See SAP Note [0003437766](https://me.sap.com/notes/0003437766).
-   AI Units license purchased. For more information about AI units license, contact your Account Executive.
-   You could have access to the *AI Services* tab, but it's possible that the tenant has not been activated with SAP Business AI yet, or SAP Business AI features are not supported yet. For more information, see SAP Note [0003522010](https://me.sap.com/notes/0003522010).

<a name="loio194ad917defc4979b30bdf6b0dcb522e"/>

<!-- loio194ad917defc4979b30bdf6b0dcb522e -->

## Enable SAP Business AI Features

SAP Business AI is integrated to generate AI content recommendations in various areas of SAP Datasphere. The integration uses AI models with prompts that are preconfigured to use input parameters to generate AI content recommendations. For example, you might want to show all objects that have been created by a specific user in the past three months.



<a name="loio194ad917defc4979b30bdf6b0dcb522e__steps_nxc_hc4_sdc"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span>*System* \> *Configuration*.

2.  Click the *AI Services* tab.

3.  In the AI Features section, check the options that you want to use.


    <table>
    <tr>
    <th valign="top">

    Feature
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *AI-Assisted Catalog Content Generation - AI-Enhanced Metadata Enrichment*
    
    </td>
    <td valign="top">
    
    Generate asset summaries and descriptions, and assign tag relationships. See [Enriching and Managing Catalog Assets](https://help.sap.com/viewer/aca3ccb4b2f84eb8b6154e8fd2812c0e/cloud/en-US/7ed60a094f2a464da6a8d75e5bfed9d5.html "To help catalog users quickly find and evaluate assets, you can enrich the assets by editing their names, adding both short and long descriptions, and adding relationships with terms, KPIs, and tags. You can also review the functional and publication status of the assets to ensure they are well-maintained and accessible.") :arrow_upper_right: and [Manage Tag Relationships for Assets](https://help.sap.com/viewer/aca3ccb4b2f84eb8b6154e8fd2812c0e/cloud/en-US/bb608dd2a4dc402889351c4303a173a4.html "On the Semantic Enrichment tab of the asset details page, you can add, edit, or remove tags.") :arrow_upper_right:.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *AI-Assisted Natural Language Search - AI-Enhanced Metadata Discovery*
    
    </td>
    <td valign="top">
    
    Enter your search string in natural language and SAP Datasphere interprets your phrase and filters your results appropriately. See [Natural Language Search](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/04170c64c1004fc58d7f235aea0e4970.html "If natural language search is enabled on your tenant (and you have the appropriate role), the search field will propose example natural language strings that are appropriate to your current filter context. Select an example string or enter your own and SAP Datasphere will interpret it and filter your results accordingly.") :arrow_upper_right:.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *AI-Assisted Modeling - AI-Enhanced Enrichment of Entity and Column Semantics*
    
    </td>
    <td valign="top">
    
    Enrich your entities and their columns with semantic information to prepare them for consumption. See [Generate Semantic Information](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/2fc1d26ebff748e4905d724247d33531.html "Use the Generate Semantics command to request SAP Datasphere to suggest a Semantic Usage for your entity, identify measures and attributes, and apply appropriate semantic types to them.") :arrow_upper_right:
    
    </td>
    </tr>
    </table>
    
4.  Click *Save*.

5.  Grant the *Data Warehouse AI Consumer* global privilege to users whom you want to access SAP Business AI features \(see [Assign Users to a Role](../Managing-Users-and-Roles/assign-roles-to-usersassign-users-to-a-role-57a7880.md)\).


<a name="task_dzr_4cb_ldc"/>

<!-- task\_dzr\_4cb\_ldc -->

## Enable Joule for SAP Datasphere

Joule is a generative AI experience that enables intuitive, conversational access to data, models, and insights. It helps users explore, understand, and act on trusted business data using natural language. It supports tasks such as data discovery, insight generation, and contextual explanations.



<a name="task_dzr_4cb_ldc__prereq_llb_5cb_ldc"/>

## Prerequisites

You must complete the following Joule configuration procedures before activating Joule in SAP Datasphere.

-   [Joule Onboarding Guide](https://help.sap.com/docs/JOULE/6189c8655c484916bb8eb767126a653a/48e8f655470048c29555272578fbc2ce.html?version=CLOUD)
-   [Integration with SAP Datasphere](https://help.sap.com/docs/joule/integrating-joule/integration-with-sap-datasphere?version=CLOUD)



<a name="task_dzr_4cb_ldc__steps_xvk_vcb_ldc"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span>*System* \> *Configuration*.

2.  Click the *AI Services* tab.

3.  In the Joule section, click *Activate Joule*.

4.  On the Confirmation screen, click *Confirm*.

5.  Grant the *Data Warehouse Joule Consumption* global privilege to users whom you want to access Joule features \(see [Assign Roles to UsersAssign Users to a Role](../Managing-Users-and-Roles/assign-roles-to-usersassign-users-to-a-role-57a7880.md)\).

    Users who have been granted the privilege will see the *Joule* button available in the shell bar: <span class="SAP-icons-V5"></span> \(see [Navigating in SAP Datasphere](https://help.sap.com/viewer/d4f3c5a0bb074d09ae9b42b2b9bd7a08/cloud/en-US/bd79b74face14b17a4cfa844a2fd36c7.html "Use the left navigation area to access all the apps available in SAP Datasphere.") :arrow_upper_right:\).

    To explore what Joule can help you do, see [Joule in Datasphere](https://help.sap.com/docs/joule/joule-capabilities/joule-in-sap-datasphere).


