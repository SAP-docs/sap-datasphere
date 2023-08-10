<!-- loio649465700ff14cd3ab7aebd72f370115 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Importing and Exporting Objects via the Command Line

You can use the SAP Datasphere command line interface, `datasphere`, to import objects to and export objects from your space.

The following sections are available in this topic:

-   [Prerequisites](importing-and-exporting-objects-via-the-command-line-6494657.md#loio649465700ff14cd3ab7aebd72f370115__section_prerequisites)
-   [Log Into an SAP Datasphere OAuth Client](importing-and-exporting-objects-via-the-command-line-6494657.md#loio649465700ff14cd3ab7aebd72f370115__section_oauth_login)
-   [List Spaces](importing-and-exporting-objects-via-the-command-line-6494657.md#loio649465700ff14cd3ab7aebd72f370115__section_list_spaces)
-   [Export Objects to a .json File](importing-and-exporting-objects-via-the-command-line-6494657.md#loio649465700ff14cd3ab7aebd72f370115__section_export_objects)
-   [Import Objects from a .json File](importing-and-exporting-objects-via-the-command-line-6494657.md#loio649465700ff14cd3ab7aebd72f370115__section_import_objects)
-   [Log Out of an SAP Datasphere OAuth Client](importing-and-exporting-objects-via-the-command-line-6494657.md#loio649465700ff14cd3ab7aebd72f370115__section_oauth_logout)



<a name="loio649465700ff14cd3ab7aebd72f370115__section_prerequisites"/>

## Prerequisites

To use `datasphere` to export and import objects you must install it \(see [Install or Update the SAP Datasphere Command Line Interface](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/f7d5eddf20a34a1aa48d8e2c68a44e28.html "The SAP Datasphere command line interface (datasphere) is a Node.js package that you download using the Node Package Manager (npm).") :arrow_upper_right:\) and have an SAP Datasphere user with the *DW Modeler* role or equivalent permissions \(see [Roles and Privileges by App and Feature](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/2d8b7d04dcae402f911d119437ce0a74.html "Review the standard roles and the privileges needed to access apps, tools, and other features of SAP Datasphere.") :arrow_upper_right:\).



<a name="loio649465700ff14cd3ab7aebd72f370115__section_oauth_login"/>

## Log Into an SAP Datasphere OAuth Client

We recommend that an administrator create an OAuth client for `datasphere` command line interface users to log into for authorization \(see [Create OAuth2.0 Clients to Authenticate Against SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/3f92b46fe0314e8ba60720e409c219fc.html "Users with the DW Administrator role can create OAuth2.0 clients and provide the client parameters to users who need to connect clients, tools, or apps to SAP Datasphere.") :arrow_upper_right:\).

> ### Note:  
> If an OAuth client is not available, users must provide a passcode for each command that they issue.

To log in, enter one of the following commands and press [Return\]:

-   To pass the OAuth client information as options, enter:

    ```
    datasphere login 
        --client-id "<id>" 
        --client-secret "<secret>" 
        --authorization-url "<url>" 
        --token-url "<url>"
    ```

    > ### Note:  
    > The *<client-id\>* and *<client-secret\>* may contain special characters, and should be [encoded as URIs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURIComponent) before being passed as options.

-   To pass the OAuth client information in a secrets file, enter:

    ```
    datasphere login 
        --secrets-file <file>.json
    ```

    Your secrets file must contain the OAuth client information and can optionally include the the following options:


    <table>
    <tr>
    <th valign="top">

    Client Information Only \(Log In at Beginning of Session\)


    
    </th>
    <th valign="top">

    Client Information and Tokens \(No Login Needed\)


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    ```
    {
        "client_id": "<client-id>",
        "client_secret": "<client-secret>",
        "authorization_url": "<authorization-url>",
        "token_url": "<token-url>"
      }
    ```


    
    </td>
    <td valign="top">
    
    ```
    {
        "client_id": "<client-id>",
        "client_secret": "<client-secret>",
        "authorization_url": "<authorization-url>",
        "token_url": "<token-url>",
        "access_token": "<access-token>",
        "refresh_token": "<refresh-token>"
      }
    ```


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    You are directed to log in with your SAP Datasphere username and password in a browser window once at the beginning of each OAuth session to determine your space permissions.


    
    </td>
    <td valign="top">
    
    You extract your OAuth access and refresh tokens,which are valid for 720 hours/30 days, and can run commands directly without any login during this period.


    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > Secrets files use versions of the options with underscores instead of hyphens.


For more information about these commands and how to extract your tokens, see [Log into the Command Line Interface via an OAuth Client](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/eb7228a171a842fa84e48c899d48c970.html "If an administrator has created an OAuth client for datasphere command line interface users to log into, there are several methods for accessing it.") :arrow_upper_right:.



<a name="loio649465700ff14cd3ab7aebd72f370115__section_list_spaces"/>

## List Spaces

To list the spaces available to you on the tenant, enter the following command and press [Return\]:

```
datasphere spaces list 
    [--host "<url>"] 
    [--pretty] 
    [--output <file>.json] 
    [--verbose] 
    [--options-file <file>.json] 
    [--secrets-file <file>.json] 
    [--passcode <code>]
```

Complete the parameters as follows:


<table>
<tr>
<th valign="top">

Parameter



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

<code>--host "<i class="varname">&lt;url&gt;</i>"</code>



</td>
<td valign="top">

Enter the URL of your SAP Datasphere tenant. You can copy the URL of any page in your tenant. Alternatively, set a host value \(see [Set a Host Value to Identify Your SAP Datasphere Tenant](https://help.sap.com/viewer/d0ecd6f297ac40249072a44df0549c1a/cloud/en-US/7aff63c8b8164c28908beb0b47dab3e0.html "If you specify the url to your SAP Datasphere tenant with the host set command, you can issue any number of other commands without the need to include the --host option.") :arrow_upper_right:\).



</td>
</tr>
<tr>
<td valign="top">

`--pretty`



</td>
<td valign="top">

\[optional\] Pretty-print the output.



</td>
</tr>
<tr>
<td valign="top">

<code>--output <i class="varname">&lt;file&gt;</i>.json</code>



</td>
<td valign="top">

\[optional\] Enter a path to a `.json` file to write the output to.

If you do not include this option, the output will be printed to the command line.



</td>
</tr>
<tr>
<td valign="top">

`--verbose`



</td>
<td valign="top">

\[optional\] Print detailed log information to the console.



</td>
</tr>
<tr>
<td valign="top">

<code>--options-file <i class="varname">&lt;file&gt;</i>.json</code>



</td>
<td valign="top">

\[optional\] Enter a path to a `.json` file containing all of some of your `datasphere` options, listed using the full option names.

A typical option file for a `list` command has the following syntax:

```
{
    "host": "<server-url>",
    "pretty": true
  }
```



</td>
</tr>
<tr>
<td valign="top">

<code>--secrets-file <i class="varname">&lt;file&gt;</i>.json</code>



</td>
<td valign="top">

\[optional\] Enter a path to a `.json` file containing the following OAuth options, using the full option names

```
{
    "client_id": "<client-id>",
    "client_secret": "<client-secret>",
    "authorization_url": "<authorization-url>",
    "token_url": "<token-url>",
    "access_token": "<access-token>",
    "refresh_token": "<refresh-token>"
  }
```

> ### Note:  
> Secrets files use versions of the options with underscores instead of hyphens.

Passing this file with the tokens allows you to run any command without having first to log in.



</td>
</tr>
<tr>
<td valign="top">

<code>--passcode <i class="varname">&lt;code&gt;</i></code>



</td>
<td valign="top">

\[optional\] If you are not logged into an OAuth client, you must provide a passcode that you have obtained from your SAP Datasphere tenant.

You can include a passcode with your command using the `--passcode` parameter. If you do not include the `--passcode` parameter, `datasphere` will prompt you to obtain a passcode:

1.  Enter [y\] and `datasphere` will open the passcode page for your tenant.
2.  If you are not already logged in, you must enter your username and password.
3.  When you arrive at the passcode page, copy the temporary authentication code and paste it into the command line.

> ### Note:  
> If you are not logged into an OAuth client, you must enter a new passcode for each command that you issue with `datasphere`.



</td>
</tr>
</table>



<a name="loio649465700ff14cd3ab7aebd72f370115__section_export_objects"/>

## Export Objects to a .json File

To export tables, views, and data access controls from your space to a `.json` file enter the following command with the `-D` option and press [Return\]:

```
datasphere spaces read 
    --space <id> 
    [--host "<url>"] 
    [--pretty] 
    [--definitions [<obj1>,<obj2>]] 
    [--no-space-definition] 
    [--output <file>.json] 
    [--verbose] 
    [--options-file <file>.json] 
    [--secrets-file <file>.json] 
    [--passcode <code>]
```

Complete the parameters as follows:


<table>
<tr>
<th valign="top">

Parameter



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

<code>--space <i class="varname">&lt;id&gt;</i></code>



</td>
<td valign="top">

Enter the *Space ID* of the space.



</td>
</tr>
<tr>
<td valign="top">

<code>--host "<i class="varname">&lt;url&gt;</i>"</code>



</td>
<td valign="top">

Enter the URL of your SAP Datasphere tenant. You can copy the URL of any page in your tenant. Alternatively, set a host value \(see [Set a Host Value to Identify Your SAP Datasphere Tenant](https://help.sap.com/viewer/d0ecd6f297ac40249072a44df0549c1a/cloud/en-US/7aff63c8b8164c28908beb0b47dab3e0.html "If you specify the url to your SAP Datasphere tenant with the host set command, you can issue any number of other commands without the need to include the --host option.") :arrow_upper_right:\).



</td>
</tr>
<tr>
<td valign="top">

`--pretty`



</td>
<td valign="top">

\[optional\] Pretty-print the output.



</td>
</tr>
<tr>
<td valign="top">

<code>--definitions [<i class="varname">&lt;obj1&gt;</i>,<i class="varname">&lt;obj2&gt;</i>]</code>



</td>
<td valign="top">

\[optional\] Read the object definitions contained in the space. You can use the `--definitions` parameter by itself to read all the objects, or specify a comma-separated list of object technical names.

Object definitions are read using the standard CSN syntax \(see [Core Data Services Schema Notation \(CSN\)](https://cap.cloud.sap/docs/cds/csn#entity-definitions)\). The following objects can be read \(exported\):

-   Local Tables - The definition of a local table contains the structure of the table only, and does not have dependencies on any other objects.
-   Remote Tables - The definition of a remote table contains information about its connection. Before importing a remote table, you must create the relevant connection with an identical technical name in the receiving space.

    > ### Note:  
    > Remote tables exported from one space can be imported into another only if they were originally imported from a connection created in v2021.19 or later.

-   Views - The definition of a view contains the definitions of all its sources and any used data access controls. When you export a view, these objects are exported too.
-   Data Access Controls - The definition of a data access control contains the definition of its permissions entity. When you export a data access control, the permissions entity is exported too.

> ### Note:  
> You can also export content from and import content to your space via:
> 
> -   The <span class="FPA-icons"></span> \(*Transport*\) app \(see [Transporting Content Between Tenants](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/df12666cf98e41248ef2251c564b0166.html "Users with the Administrator or Space Administrator role can use the Transport app to transfer content between tenants via a private cloud storage area.") :arrow_upper_right:\).
> -   *Export to CSN/JSON File* buttons in selected *Data Builder* editors \(see [Importing and Exporting Objects in CSN/JSON Files](importing-and-exporting-objects-in-csn-json-files-f8ff062.md)\).



</td>
</tr>
<tr>
<td valign="top">

`--no-space-definition`



</td>
<td valign="top">

\[optional\] Suppress the display of the `spaceDefinition` property. When used with the `--definitions` option, this allows you to read object definitions without seeing the other properties of the space.



</td>
</tr>
<tr>
<td valign="top">

<code>--output <i class="varname">&lt;file&gt;</i>.json</code>



</td>
<td valign="top">

\[optional\] Enter a path to a `.json` file to write the output to.

If you do not include this option, the output will be printed to the command line.



</td>
</tr>
<tr>
<td valign="top">

`--verbose`



</td>
<td valign="top">

\[optional\] Print detailed log information to the console.



</td>
</tr>
<tr>
<td valign="top">

<code>--options-file <i class="varname">&lt;file&gt;</i>.json</code>



</td>
<td valign="top">

\[optional\] Enter a path to a `.json` file containing all of some of your `datasphere` options, listed using the full option names.

A typical option file for a `read` command has the following syntax:

```
{
    "host": "<server-url>",
    "space": "<space-id>",
    "pretty": true,
    "definitions": true
    "no-space-definition": false,
    "output": "<filepath>.json",
    "verbose": false,
  }
```



</td>
</tr>
<tr>
<td valign="top">

<code>--secrets-file <i class="varname">&lt;file&gt;</i>.json</code>



</td>
<td valign="top">

\[optional\] Enter a path to a `.json` file containing the following OAuth options, using the full option names

```
{
    "client_id": "<client-id>",
    "client_secret": "<client-secret>",
    "authorization_url": "<authorization-url>",
    "token_url": "<token-url>",
    "access_token": "<access-token>",
    "refresh_token": "<refresh-token>"
  }
```

> ### Note:  
> Secrets files use versions of the options with underscores instead of hyphens.

Passing this file with the tokens allows you to run any command without having first to log in.



</td>
</tr>
<tr>
<td valign="top">

<code>--passcode <i class="varname">&lt;code&gt;</i></code>



</td>
<td valign="top">

\[optional\] If you are not logged into an OAuth client, you must provide a passcode that you have obtained from your SAP Datasphere tenant.

You can include a passcode with your command using the `--passcode` parameter. If you do not include the `--passcode` parameter, `datasphere` will prompt you to obtain a passcode:

1.  Enter [y\] and `datasphere` will open the passcode page for your tenant.
2.  If you are not already logged in, you must enter your username and password.
3.  When you arrive at the passcode page, copy the temporary authentication code and paste it into the command line.

> ### Note:  
> If you are not logged into an OAuth client, you must enter a new passcode for each command that you issue with `datasphere`.



</td>
</tr>
</table>

The space definition is written to the console or to the specified file.



<a name="loio649465700ff14cd3ab7aebd72f370115__section_import_objects"/>

## Import Objects from a .json File

To import tables, views, and data access controls into a space, you must first prepare a space definition file containing valid CSN object definitions \(see [The Space Definition File Format](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/3fcbf619f2774b849fa7df58163b3609.html "Space properties are set and retrieved in the space definition file format and stored as a .json file.") :arrow_upper_right:\).

When your file is ready, enter the following command and press [Return\]:

```
datasphere spaces create 
    --file-path <file>.json 
    [--host "<url>"] 
    [--force-definition-deployment] 
    [--verbose] 
    [--options-file <file>.json] 
    [--secrets-file <file>.json] 
    [--passcode <code>]
```

Complete the parameters as follows:


<table>
<tr>
<th valign="top">

Parameter



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

<code>--host "<i class="varname">&lt;url&gt;</i>"</code>



</td>
<td valign="top">

Enter the URL of your SAP Datasphere tenant. You can copy the URL of any page in your tenant. Alternatively, set a host value \(see [Set a Host Value to Identify Your SAP Datasphere Tenant](https://help.sap.com/viewer/d0ecd6f297ac40249072a44df0549c1a/cloud/en-US/7aff63c8b8164c28908beb0b47dab3e0.html "If you specify the url to your SAP Datasphere tenant with the host set command, you can issue any number of other commands without the need to include the --host option.") :arrow_upper_right:\).



</td>
</tr>
<tr>
<td valign="top">

<code>--file-path <i class="varname">&lt;file&gt;</i>.json</code>



</td>
<td valign="top">

Enter a path to a file with a .json extension containing your space definition.



</td>
</tr>
<tr>
<td valign="top">

`--force-definition-deployment`



</td>
<td valign="top">

\[optional\] Deploy changes to objects even if they will generate validation messages warning of impacts to objects that depend on them. Using this option is equivalent to clicking the *Deploy Anyway* button in the *Validation Messages* dialog \(see [Modifying Objects That Have Dependent Objects](modifying-objects-that-have-dependent-objects-f315863.md)\).



</td>
</tr>
<tr>
<td valign="top">

<code>--input '<i class="varname">&lt;stringified-json&gt;</i>'</code>



</td>
<td valign="top">

\[optional\] Provide your space definition in stringified json format instead of via the `--file-path` option. For example:

```
--input '{"MY_SPACE":{"spaceDefinition":{"version":"1.0.4"}}}'
```



</td>
</tr>
<tr>
<td valign="top">

`--verbose`



</td>
<td valign="top">

\[optional\] Print detailed log information to the console.



</td>
</tr>
<tr>
<td valign="top">

<code>--options-file <i class="varname">&lt;file&gt;</i>.json</code>



</td>
<td valign="top">

\[optional\] Enter a path to a `.json` file containing all of some of your `datasphere` options, listed using the full option names.

A typical option file for a `create` command has the following syntax:

```
{
    "host": "<server-url>",
    "space": "<space-id>",
    "verbose": false,
    "file-path": "<filepath>.json"
  }
```



</td>
</tr>
<tr>
<td valign="top">

<code>--secrets-file <i class="varname">&lt;file&gt;</i>.json</code>



</td>
<td valign="top">

\[optional\] Enter a path to a `.json` file containing the following OAuth options, using the full option names

```
{
    "client_id": "<client-id>",
    "client_secret": "<client-secret>",
    "authorization_url": "<authorization-url>",
    "token_url": "<token-url>",
    "access_token": "<access-token>",
    "refresh_token": "<refresh-token>"
  }
```

> ### Note:  
> Secrets files use versions of the options with underscores instead of hyphens.

Passing this file with the tokens allows you to run any command without having first to log in.



</td>
</tr>
<tr>
<td valign="top">

<code>--passcode <i class="varname">&lt;code&gt;</i></code>



</td>
<td valign="top">

\[optional\] If you are not logged into an OAuth client, you must provide a passcode that you have obtained from your SAP Datasphere tenant.

You can include a passcode with your command using the `--passcode` parameter. If you do not include the `--passcode` parameter, `datasphere` will prompt you to obtain a passcode:

1.  Enter [y\] and `datasphere` will open the passcode page for your tenant.
2.  If you are not already logged in, you must enter your username and password.
3.  When you arrive at the passcode page, copy the temporary authentication code and paste it into the command line.

> ### Note:  
> If you are not logged into an OAuth client, you must enter a new passcode for each command that you issue with `datasphere`.



</td>
</tr>
</table>

The objects are created or updated as you have specified.

> ### Note:  
> If any parameters are set incorrectly, the creation or update is canceled and an error message is written to the console.



<a name="loio649465700ff14cd3ab7aebd72f370115__section_oauth_logout"/>

## Log Out of an SAP Datasphere OAuth Client

To log out at the end of your session enter the following command:

```
datasphere logout
```

