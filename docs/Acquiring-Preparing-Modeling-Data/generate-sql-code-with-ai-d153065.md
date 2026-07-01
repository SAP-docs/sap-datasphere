<!-- loiod1530656d42f44f68b6265666ec35531 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Generate SQL Code with AI

Use the *Generate SQL* command and prompt SAP Datasphere to generate code for your SQL views. You can create a view from scratch or modify existing SQL code.



## Prerequisites

For information about privileges and other prerequisites needed to use this feature, see the prerequisites listed in [Creating an SQL View](creating-an-sql-view-81920e4.md).



## Generate SQL Code

1.  Click <span class="SAP-icons-V5"></span> \(Generate\) ** \> *Generate SQL* \(or press [CTRL\] + [G\] \) to open the prompt panel.
2.  Drag the sources that you want SAP Datasphere to use from the *Source Browser*, and drop them in the prompt panel.
3.  \[optional\] Select SQL code for the AI to focus on.
4.  Enter your prompt describing the output that you want from your SQL view and then click *Send Prompt* \(or press [Enter\]\).

    > ### Note:  
    > You can use views with input parameters as sources and request to create new input parameters in your prompt. The parameter will be inserted into the code as requested, but you must then manually create the parameter in the side panel before the code can be validated. For more information, see:
    > 
    > -   [Create an Input Parameter in a Graphical View](create-an-input-parameter-in-a-graphical-view-53fa99a.md)
    > -   [Process Source Input Parameters in an SQL View](process-source-input-parameters-in-an-sql-view-58d8763.md)

    SAP Datasphere will generate SQL code in response to your prompt.

5.  Review the generated code. You can:

    -   Enter a new prompt to make further modifications.
    -   Manually modify the code.
    -   Click <span class="FPA-icons-V3"></span> \(Preview Data\) to preview the data output.
    -   Click *Reject* to reject and roll back the proposed changes.

    You can work iteratively with prompts and manual editing as necessary until you are satisfied with the code.

6.  Click <span class="FPA-icons-V3"></span> \(Save\)** \> *Save* to save your entity or click <span class="SAP-icons-V5"></span> \(Deploy\) to save and deploy it immediately. 

    For more information, see [Saving and Deploying Objects](saving-and-deploying-objects-7c0b560.md).


