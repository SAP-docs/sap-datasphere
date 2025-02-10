<!-- loio2665ce1e83314dd396cea0b88ed5af40 -->

# Delete Your Service Instance in SAP BTP

Delete your SAP Datasphere service instance in SAP BTP.

To do so, you must have SAP BTP administration authorization on the subaccount that is entitled to SAP Datasphere.

> ### Note:  
> If you delete your service instance by accident, it can be recovered within seven days. After seven days have passed, the tenant and all its data will be deleted and cannot be recovered.

1.  In SAP BTP, select the subaccount and the space where the service instance was created.

2.  Navigate to *Instances and Subscriptions*.

3.  In the *Service Instances* page, find the SAP Datasphere service instance that you want to delete, click the button at the end of the row and select *Delete*, then click *Delete* in the confirmation dialog.

    You can view the progress of the deletion. The tenant stays in a suspended state for seven days. During that time, you cannot use the same tenant host name.


<a name="task_rzb_xhw_cbc"/>

<!-- task\_rzb\_xhw\_cbc -->

## Restore an Accidentally Deleted Service Instance



<a name="task_rzb_xhw_cbc__context_njz_b3w_cbc"/>

## Context

If you accidentally delete your SAP Datasphere service instance in SAP BTP, you can restore it within seven days. For more information, see [SAP Note 3455188](https://me.sap.com/notes/3455188).

> ### Note:  
> Restoring your service instance is only supported for standard service plans.



<a name="task_rzb_xhw_cbc__steps_j4s_pjw_cbc"/>

## Procedure

1.  Create a customer incident through ServiceNow using the component `DS-PROV`. Set the priority to *High*, and ask SAP support to restore impacted SAP Datasphere tenant. You must provide the tenant URL.

    Once completed, SAP Support informs you that the impacted tenant has been restored and unlocked successfully.

2.  Get the OAuth Client ID and OAuth Client Secret:

    1.  Log on to the impacted SAP Datasphere tenant.

    2.  From the side navigation, choose *System* \> *Administration*.

    3.  Choose the *App Integration* tab.

    4.  Select *Add a New OAuth Client*.

    5.  From the *Purpose* list, select *API Access*.

    6.  Choose at least one API option from the *Access* list.

    7.  Set *Authorization Grant* to *Client Credentials*.

    8.  Select *Save*.

    9.  Copy and save the *OAuth Client ID* and *OAuth Client Secret* for Step 3.


3.  Create an OAuth Client in the impacted SAP Datasphere tenant. You can name it something like `DSP_SERVICE_INSTANCE_LINKING`.

4.  Fetch your access token via http POST request to the OAuth Client Token URL.

    The *Token URL* is displayed on the *App Integration* tab, above the list of *Configured Clients*.

    1.  Provide the following information with your POST request:

        ```
        curl --location --request POST '<TokenURL>/oauth/token/oauth/token?grant_type=client_credentials' \
        --header 'Content-Type: application/json' \
        --header 'Authorization: Basic <OAuthClientSecret>' \
        --data''
        ```

        Replace *<TokenURL\>* with your OAuth Client Token URL. Replace *<OAuthClientSecret\>* with the OAuth Client Secret. The secret must be Base64 encoded.

    2.  Save the access token returned by the POST request.


5.  Get the UUID for your tenant.

    1.  Log on to the impacted tenant.

    2.  Go to *System* \> *About*.

    3.  Copy the ID under *Tenant*.


6.  Create a new BTP service instance for SAP Datasphere and link it to the impacted SAP Datasphere tenant.

    1.  Log on to the SAP BTP Cockpit.

    2.  Navigate to the subaccount where the deleted SAP BTP service instance was assigned.

    3.  Navigate to *Services* \> *Instances and Subscriptions*.

    4.  Click *Create*.

    5.  Select *Service*: SAP Datasphere.

    6.  Select *Plan*: *Standard*.

    7.  Select *Runtime Environment*: *Other*.

    8.  Enter a name for the service instance.

    9.  Click *Next*.

    10. In the parameters dialog, switch from *Form* to *JSON*.

    11. Maintain the following two parameters in JSON format:

        ```
        {
            "tenantUuid": "<TenantUUID>",
            "access_token": "<AccessToken>"
        }
        ```

        Replace *<TenantUUID\>* with the ID that you retrieved in Step 4c. Replace *<AccessToken\>* with the token that you fetched in Step 3b.

    12. Click *Next*.

    13. In the review dialog, click *Create*.

    14. Back in the SAP Datasphere tenant, go to *System* \> *Administration* and delete the OAuth Client named DSP\_SERVICE\_INSTANCE\_LINKING, previously created in Step 3.





<a name="task_rzb_xhw_cbc__result_scl_xrw_cbc"/>

## Results

A new service instance is created and linked to the SAP Datasphere tenant that was accidentally deleted. All tenant data is restored.

