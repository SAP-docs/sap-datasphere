<!-- loio274f2736465c4c48a091c675880502a2 -->

# Manage Tasks Using REST APIs

You can run task chains and review task logs using REST APIs.



## Introduction to Tasks APIs

The Task REST APIs allow you to run task and monitor task in SAP Datasphere. You can:

-   Run a task chain.
-   Retrieve task run details with log ID.
-   Retrieve existing history of object task logs.

To use the Tasks REST APIs, you must have the same roles and privileges that are required to run task chains and view task logs in SAP Datasphere. For more information, see [Creating a Task Chain](creating-a-task-chain-d1afbc2.md).

Obtain the following parameters for an OAuth client defined in your SAP Datasphere tenant with *Purpose* set to *Interactive Usage* or *Technical User*:


<table>
<tr>
<th valign="top">

Standard OAuth2 Authorization Flow

</th>
<th valign="top">

OAuth2SAMLBearer Principal Propagation Flow

</th>
</tr>
<tr>
<td valign="top">

-   *Client ID*
-   *Secret*
-   *Authorization URL* \(not required for clients with a *Technical User* purpose\)
-   *Token URL*

Users of a client with a *Technical User* purpose \(which includes its own privileges and permissions\) can then access their resource directly. Users of clients with other purposes must manually authenticate against the IDP in order to generate the authorization code before continuing with the remaining OAuth2.0 steps.

</td>
<td valign="top">

-   *Client ID*
-   *Secret*
-   *OAuth2SAML Token URL*
-   *OAuth2SAML Audience*

Users of a client with a *Technical User* purpose can then access their resource directly. Users of clients with other purposes must authenticate with their third-party app, which has a trusted relationship with the IDP, and do not need to re-authenticate \(see [Add a Trusted Identity Provider](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/ea0688aef2f94b35ae34d930b3cb0c10.html "If you use the OAuth 2.0 SAML Bearer Assertion workflow, you must add a trusted identity provider to SAP Datasphere.") :arrow_upper_right:\). See also the blog [Integrating with SAP Datasphere Consumption APIs using SAML Bearer Assertion](https://community.sap.com/t5/technology-blogs-by-sap/integrating-with-sap-datasphere-consumption-apis-using-saml-bearer/ba-p/13647905) \(published March 2024\). 

</td>
</tr>
</table>

The detailed documentation of the Data Sharing Cockpit REST APIs is available on the [SAP Business Accelerator Hub](https://api.sap.com/package/sapdatasphere/overview).




## Task Chains

Run task chains.

To run a task chain, use the POST request with the API <code>api/v1/datasphere/tasks/chains/<i class="varname">&lt;spaceid&gt;</i>/run/<i class="varname">&lt;objectid&gt;</i></code> endpoint and enter:

```
https://<tenant_url>/api/v1/datasphere/tasks/chains/<space_id>/run/<objectid>
```

**Prerequisite:** The task chain must be active and deployed before it can be run.

**Header:** Set `Content-Type: application/json` in the request header.

**Request Body:** You can optionally pass input parameters for the task chain. This works only if the task chain is defined with input parameters. If no input parameters are needed, you can send an empty JSON object `{}`.

Example:

> ### Sample Request:
> ```
> {
>   "inputParameters": {
>     "param1": "value1",
>     "param2": "value2"
>   }
> }
> ```

> ### Sample Response:
> ```
> {
>   "logId": 9999999
> }
> ```




## Logs

Get task log details and existing task log history of objects.

Get task log details. To retrieve task log details, use the GET request with the API <code>api/v1/datasphere/tasks/chains/<i class="varname">&lt;spaceid&gt;</i>/run/<i class="varname">&lt;objectid&gt;</i></code>endpoint and enter:

```
https://<tenant_url>/api/v1/datasphere/tasks/logs/<space_id><logid>
```

Details for a specific run identified by its log ID and space ID. The response format is controlled by the Accept header. If the Accept header is not provided, the endpoint returns the default status object response. Accept header options are:

-   Accept header `application/vnd.sap.datasphere.task.log.status.object+json`returns the log with the status of the object with the status:object format \(default\).

    Example:

    > ### Sample Code:  
    > ```
    > {
    >     "status": "COMPLETED"
    > }
    > ```

-   Accept header `application/vnd.sap.datasphere.task.log.status+json`returns the log with the status as a string.

    Example:

    > ### Sample Code:  
    > ```
    > {
    >     "COMPLETED"
    > }
    > ```

-   Application header `application/vnd.sap.datasphere.task.log.details+json`returns the detailed logs of a specified run including messages and task chain child nodes.

    Example:

    > ### Sample Code:  
    > ```
    > {
    >   "logId": 2295172,
    >   "status": "COMPLETED",
    >   "startTime": "2025-11-14T02:30:33.142Z",
    >   "endTime": "2025-11-14T02:31:36.059Z",
    >   "runTime": 62917,
    >   "objectId": "Notifications_TZ_330AM",
    >   "applicationId": "TASK_CHAINS",
    >   "activity": "RUN_CHAIN",
    >   "spaceId": "SPACE_ID",
    >   "user": "User Name",
    >   "children": [
    >     {
    >       "nodeId": 1,
    >       "logId": 2295190,
    >       "status": "COMPLETED",
    >       "objectId": "Invoices_view",
    >       "activity": "PERSIST",
    >       "applicationId": "VIEWS",
    >       "startTime": "2025-11-14T02:30:59.210Z",
    >       "endTime": "2025-11-14T02:31:13.082Z",
    >       "runTime": 13872
    >     }
    >   ],
    >   "messages": [
    >     {
    >       "messageNumber": 1,
    >       "severity": "INFO",
    >       "text": "Task 2295172 started.",
    >       "timestamp": "2025-11-14T02:30:33.145Z"
    >     },
    >     {
    >       "messageNumber": 2,
    >       "severity": "INFO",
    >       "text": "Loading task chain and prepared 1 tasks that are part of this chain.",
    >       "timestamp": "2025-11-14T02:30:33.597Z"
    >     },
    >     {
    >       "messageNumber": 3,
    >       "severity": "INFO",
    >       "text": "Node 1 with task VIEWS/PERSIST/SPACE_ID/Invoices_view is going to be started.",
    >       "timestamp": "2025-11-14T02:30:43.599Z"
    >     },
    >     {
    >       "messageNumber": 4,
    >       "severity": "INFO",
    >       "text": "Task 2295172 has finished at 2025-11-14T02:31:36.133Z with status COMPLETED",
    >       "timestamp": "2025-11-14T02:31:36.140Z"
    >     }
    >   ]
    > }
    > ```

-   Accept header `application/vnd.sap.datasphere.task.log.details.extended+json` returns the extended logs including all detailed log info and message details.

    Example:

    > ### Sample Code:  
    > ```
    > {
    >   "logId": 2295172,
    >   "status": "COMPLETED",
    >   "startTime": "2025-11-14T02:30:33.142Z",
    >   "endTime": "2025-11-14T02:31:36.059Z",
    >   "runTime": 62917,
    >   "objectId": "Notifications_TZ_330AM",
    >   "applicationId": "TASK_CHAINS",
    >   "activity": "RUN_CHAIN",
    >   "spaceId": "SPACE_ID",
    >   "user": "User Name",
    >   "children": [
    >     {
    >       "nodeId": 1,
    >       "logId": 2295190,
    >       "status": "COMPLETED",
    >       "objectId": "Invoices_view",
    >       "activity": "PERSIST",
    >       "applicationId": "VIEWS",
    >       "startTime": "2025-11-14T02:30:59.210Z",
    >       "endTime": "2025-11-14T02:31:13.082Z",
    >       "runTime": 13872
    >     }
    >   ],
    >   "messages": [
    >     {
    >       "messageNumber": 1,
    >       "severity": "INFO",
    >       "text": "Task 2295172 started.",
    >       "timestamp": "2025-11-14T02:30:33.145Z",
    >       "details": "{\"correlationId\":\"3e2619be-5a68-499e-a981-640d8a6aa235\",\"task\":\"TASK_CHAINS/RUN_CHAIN/SPACE_ID/Notifications_TZ_330AM\"}"
    >     },
    >     {
    >       "messageNumber": 2,
    >       "severity": "INFO",
    >       "text": "Loading task chain and prepared 1 tasks that are part of this chain.",
    >       "timestamp": "2025-11-14T02:30:33.597Z"
    >     },
    >     {
    >       "messageNumber": 3,
    >       "severity": "INFO",
    >       "text": "Node 1 with task VIEWS/PERSIST/SPACE_ID/Invoices_view is going to be started.",
    >       "timestamp": "2025-11-14T02:30:43.599Z"
    >     },
    >     {
    >       "messageNumber": 4,
    >       "severity": "INFO",
    >       "text": "Task 2295172 has finished at 2025-11-14T02:31:36.133Z with status COMPLETED",
    >       "timestamp": "2025-11-14T02:31:36.140Z",
    >       "details": "{\"correlationId\":\"26f0922a-c4e0-4b07-92cd-f6a939987cc8\"}"
    >     }
    >   ]
    > }
    > ```


Get all existing task log history of an object. To retrieve log history, use the GET request with the API <code>api/v1/datasphere/tasks/logs/<i class="varname">&lt;spaceid&gt;</i>/objects/<i class="varname">&lt;objectid&gt;</i></code>endpoint and enter:

```
https://<tenant_url>/api/v1/datasphere/tasks/logs/<space_id>/objects/<objectid>
```

Example:

> ### Sample Code:  
> ```
> [
>   {
>     "logId": 2329400,
>     "status": "RUNNING",
>     "startTime": "2025-11-18T21:28:56.705Z",
>     "runTime": 59441,
>     "objectId": "Nested_Chain_1",
>     "applicationId": "TASK_CHAINS",
>     "activity": "RUN_CHAIN",
>     "spaceId": "SPACE_ID",
>     "user": "User Name"
>   },
>   {
>     "logId": 2326060,
>     "status": "FAILED",
>     "startTime": "2025-11-18T10:25:19.216Z",
>     "endTime": "2025-11-18T10:27:49.471Z",
>     "runTime": 150255,
>     "objectId": "Nested_Chain_1",
>     "applicationId": "TASK_CHAINS",
>     "activity": "RUN_CHAIN",
>     "spaceId": "SPACE_ID",
>     "user": "User Name"
>   },
>   {
>     "logId": 2225105,
>     "status": "FAILED",
>     "startTime": "2025-11-03T12:26:23.360Z",
>     "endTime": "2025-11-03T12:28:38.620Z",
>     "runTime": 135260,
>     "objectId": "Nested_Chain_1",
>     "applicationId": "TASK_CHAINS",
>     "activity": "RUN_CHAIN",
>     "spaceId": "SPACE_ID",
>     "user": "User Name"
>   },
>   {
>     "logId": 2014586,
>     "status": "FAILED",
>     "startTime": "2025-09-18T21:19:21.724Z",
>     "endTime": "2025-09-18T21:22:14.289Z",
>     "runTime": 172565,
>     "objectId": "Nested_Chain_1",
>     "applicationId": "TASK_CHAINS",
>     "activity": "RUN_CHAIN",
>     "spaceId": "SPACE_ID",
>     "user": "User Name"
>   }
> ]
> ```

