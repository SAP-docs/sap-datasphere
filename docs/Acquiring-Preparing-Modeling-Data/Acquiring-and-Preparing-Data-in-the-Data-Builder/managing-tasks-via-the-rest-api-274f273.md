<!-- loio274f2736465c4c48a091c675880502a2 -->

# Managing Tasks via the REST API

You can run task chains and review task logs via the REST API.



## Prerequisites

To run and manage tasks, you must have a scoped role granting access to the appropriate spaces with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Data Integration* \(`-R------`\) - To view data integration task logs in the *Data Integration Monitor* app.

-   *Data Warehouse Data Integration* \(`--U-----`\) - To manually run data integration tasks.

-   *Data Warehouse Data Integration* \(`----E---`\) - To schedule data integration tasks.

-   *Data Warehouse Data Builder* \(`------S-`\) - To share task chains to other spaces.
-   *User* \(`R-------`\) - To display and add notification recipients from a list of current tenant members, when setting up email notifications.

You must, in addition, obtain access to an appropriate OAuth client:


<table>
<tr>
<th valign="top">

OAuth Purpose

</th>
<th valign="top">

Interactive Usage

</th>
<th valign="top">

Technical User

</th>
</tr>
<tr>
<td valign="top">

Authorization Grant

</td>
<td valign="top">

Authorization Code

Three- Legged \(User-Client-Server\): Manually propagate authorization to another service.

</td>
<td valign="top">

Client Credentials

Two-Legged \(Client-Server\): Service to service communication via APIs.

</td>
</tr>
<tr>
<td valign="top">

Authentication

</td>
<td valign="top">

Manually authenticate to generate the authorization code.

> ### Note:  
> To run a task chain with Interactive Usage purpose using the REST API, you need authorized consent. Users with Interactive Usage purpose without consent can receive task run log details and history but will not be able to run a task chain. In the profile settings under *Authorized Consent Settings*, you can give and revoke consent. For more information see [Changing SAP Datasphere Settings](https://help.sap.com/viewer/d4f3c5a0bb074d09ae9b42b2b9bd7a08/cloud/en-US/1084796d09464e78870f32cab8584dfc.html "To view and edit your user profile settings, click your user icon in the shell bar and select Settings. You can control various aspects of the user experience of SAP Datasphere and set data privacy and task scheduling consent options.") :arrow_upper_right:.



</td>
<td valign="top">

None required. The OAuth client contains the necessary credentials and privileges.

> ### Note:  
> BW process chains cannot be run in task chains by a technical user. The technical user in SAP Datasphere does not have a mapped user on the BW side. Please use an approved business user role to run BW process chains in a task chain.



</td>
</tr>
<tr>
<td valign="top">

Parameters

</td>
<td valign="top">

-   Client ID
-   Secret
-   Authorization URL
-   Token URL



</td>
<td valign="top">

-   Client ID
-   Secret
-   Token URL



</td>
</tr>
</table>

For more information, see [Create OAuth2.0 Clients to Authenticate Against SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/3f92b46fe0314e8ba60720e409c219fc.html "Users with an administrator role can create OAuth2.0 clients and provide the client parameters to users who need to connect clients, tools, or apps to SAP Datasphere.") :arrow_upper_right:.



## Introduction to the Tasks API

The Tasks REST API allow you to run task and monitor task in SAP Datasphere. You can:

-   Run a task chain.
-   Retry a task chain .
-   Cancel a task chain.
-   Retrieve task run details with log ID.
-   Retrieve existing history of object task logs.

The detailed documentation of the Tasks REST API is available on the [SAP Business Accelerator Hub](https://api.sap.com/package/sapdatasphere/overview).



## Task Chains

Run task chains.

To run a task chain, use the POST request with the API <code>api/v1/datasphere/tasks/chains/<i class="varname">&lt;spaceid&gt;</i>/run/<i class="varname">&lt;objectid&gt;</i></code> endpoint and enter:

```
https://<tenant_url>/api/v1/datasphere/tasks/chains/<space_id>/run/<objectid>
```

Example:

> ### Sample Code:  
> ```
> {
>   "logId": 9999999
> }
> ```

Retry task chains.

To retry a failed task chain run, use the POST request with the API <code>api/v1/datasphere/tasks/chains/<i class="varname">&lt;spaceid&gt;</i>/retry/<i class="varname">&lt;objectid&gt;</i></code> endpoint and enter:

```
https://<tenant_url>/api/v1/datasphere/tasks/chains/<space_id>/retry/<objectid>
```

Example:

> ### Sample Code:  
> ```
> {
>   "logId": 9999999
> }
> ```

> ### Note:  
> Valid for FAILED or CANCELED task chains as long as they were the last run of the object.

Cancel task chains.

To cancel a task chain run, use the POST request with the API <code>api/v1/datasphere/tasks/chains/<i class="varname">&lt;spaceid&gt;</i>/cancel/<i class="varname">&lt;logid&gt;</i></code> endpoint and enter:

```
https://<tenant_url>api/v1/datasphere/tasks/chains/<spaceid>/cancel/<logid>
```

Example:

> ### Sample Code:  
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

