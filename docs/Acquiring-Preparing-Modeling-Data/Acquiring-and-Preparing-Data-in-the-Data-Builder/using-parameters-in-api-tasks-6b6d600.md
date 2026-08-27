<!-- loio6b6d6004c2c94a71a8a732718fed100c -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Using Parameters in API Tasks

Use input and output parameters in API tasks to allow for more flexibility.



## Input Parameters

You can define input parameters in an API task and use them to for example flexibly adjust the endpoint path based on your scenarios or to pass a job id.

1.  Open the properties panel of your API task, go to *Input Parameters* and click <span class="FPA-icons-V3"></span> \(Input Parameters\).
2.  On the *Input Parameters* dialog, add an input parameter by completing the following properties:


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Input Parameter
    
    </td>
    <td valign="top">
    
    Enter a name for your input parameter. The parameter name must be alphanumeric and digits are only allowed from the second position onwards.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Action
    
    </td>
    <td valign="top">
    
    Choose from the following:

    -   *Map To* - Map the source input parameter to the task chain.
    -   *Set Value* - Enter a value to resolve the input parameter.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Value
    
    </td>
    <td valign="top">
    
    Enter or select the value depending on what action you selected.
    
    </td>
    </tr>
    </table>
    
    For more information, see [Create Input Parameters in Task Chains](create-input-parameters-in-task-chains-c9906ec.md) step 5.

3.  You can now use parameter references in the *API Path* using the following syntax: <code>{{<i class="varname">&lt;parameter_name&gt;</i>}}</code>, for example:


    <table>
    <tr>
    <th valign="top">

    Method Used for API Invocation
    
    </th>
    <th valign="top">

    Example API Path with Parameter Reference
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    POST
    
    </td>
    <td valign="top">
    
    `/v1/invoke/{{resourceId}}/action/actionName`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    GET
    
    </td>
    <td valign="top">
    
    `/v1/status/{{jobId}}`
    
    </td>
    </tr>
    </table>
    
4.  Parameter references are not automatically replaced in the request body. You must reference parameters in the JSON request body using the following syntax: <code>"$ref": "#/user/<i class="varname">&lt;parameter_name&gt;</i></code>.

    On the top right above the request body, click the info button to open a list of the parameter references, and click the copy button for the one that you want to use to copy it with the correct syntax to the request body.

5.  When doing an API test run, you will be prompted to enter the values for the parameters you're using.

During runtime, the parameter reference will get replaced if the parameter exists. If it doesn't exist, the system will show a validation error.



## Output Parameters

You can define output parameters in an API task to pass information returned by the API to the next task in the task chain. This only works for APIs that return content type \`application/json\`.

1.  Open the properties panel of your API task, go to *Output Parameters* and click <span class="FPA-icons-V3"></span> \(Output Parameters\).
2.  On the *Output Parameters* dialog, add an output parameter by completing the following properties:


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Output Parameter
    
    </td>
    <td valign="top">
    
    Enter a name for your output parameter.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    JSON Path
    
    </td>
    <td valign="top">
    
    Enter the JSON path used to extract the output parameter from the API response.

    The path requires the following syntax: It needs to begin with $, use dots to navigate the structure, and use explicit array indexing.

    > ### Example:  
    > Example API response: `{"customer": {"name": "test" }}` → example JSON path: `$.customer.name`
    > 
    > Example for explicit array indexing: `$.data.orders[0].id`

    Unsupported syntax:

    -   Wildcards \(\*\)
    -   Filters \(?\(\)\)
    -   Deep scanning \(..\)

    If a JSON path is invalid or it doesn't match anything, the task will fail. A message will appear in the task log with information about the related issue.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Data Type
    
    </td>
    <td valign="top">
    
    Choose a JSON type that will be used to check the value of the output parameter:

    -   String
    -   Number
    -   Boolean
    -   Object
    -   Array
    -   Null
    -   \[default\] Any

    If the value doesn't match the selected type, the task will fail. If you select *Any*, the type check won't be performed.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Task Chain Parameter
    
    </td>
    <td valign="top">
    
    Map the output parameter to a task chain parameter by entering the required parameter name. The mapped output parameter of the API task can then be used as an input parameter for the following task.
    
    </td>
    </tr>
    </table>
    

