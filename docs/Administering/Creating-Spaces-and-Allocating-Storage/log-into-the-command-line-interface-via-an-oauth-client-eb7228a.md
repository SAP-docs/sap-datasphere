<!-- loioeb7228a171a842fa84e48c899d48c970 -->

# Log into the Command Line Interface via an OAuth Client

If an administrator has created an OAuth client for `datasphere` command line interface users to log into, there are several methods for accessing it.

For information about creating an OAuth client, see [Create OAuth2.0 Clients to Authenticate Against SAP Datasphere](../Creating-and-Configuring-Your-Tenant/create-oauth2-0-clients-to-authenticate-against-sap-datasphere-3f92b46.md).

This topic contains the following sections:

-   [Log in by Passing OAuth Client Information as Options](log-into-the-command-line-interface-via-an-oauth-client-eb7228a.md#loioeb7228a171a842fa84e48c899d48c970__section_secrets_options)
-   [Log in by Passing OAuth Client Information in a Secrets File](log-into-the-command-line-interface-via-an-oauth-client-eb7228a.md#loioeb7228a171a842fa84e48c899d48c970__section_secrets_file)
-   [Avoid Running a Login Command by Extracting Access and Refresh Tokens](log-into-the-command-line-interface-via-an-oauth-client-eb7228a.md#loioeb7228a171a842fa84e48c899d48c970__section_extracting_tokens)

> ### Note:  
> See the blog [@sap/datasphere-cli: Getting Rid of Passcodes Thanks to OAuth Client Support](https://blogs.sap.com/2022/09/21/sap-dwc-cli-getting-rid-of-passcodes-thanks-to-oauth-client-support/) \(published September 2022\) for more information about working the command line interface and OAuth.

> ### Note:  
> The SAP Datasphere command line interface module has been renamed from `dwc` to `datasphere`. The command `dwc` will be decommissioned at the end of 2023: please use the new `datasphere` command instead.



<a name="loioeb7228a171a842fa84e48c899d48c970__section_secrets_options"/>

## Log in by Passing OAuth Client Information as Options

You can log in by passing the OAuth client information as options on the command line.

> ### Note:  
> You must have write access to the CLI installation folder.

To log in, enter the following command and press [Return\]:

```
datasphere login 
    --client-id "<id>" 
    --client-secret "<secret>" 
    --authorization-url "<url>" 
    --token-url "<url>"
```

> ### Note:  
> You will be directed to log in with your SAP Datasphere username and password in a browser window once at the beginning of your OAuth session to determine your space permissions.

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

<code>--client-id "<i class="varname">&lt;id&gt;</i>"</code>



</td>
<td valign="top">

Enter the *OAuth Client ID* provided by your administrator.

> ### Note:  
> The client ID must be [encoded as a URI](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURIComponent) when passed as a parameter.



</td>
</tr>
<tr>
<td valign="top">

<code>--client-secret "<i class="varname">&lt;secret&gt;</i>"</code>



</td>
<td valign="top">

Enter the *Secret* provided by your administrator.

> ### Note:  
> The secret must be [encoded as a URI](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURIComponent) when passed as a parameter.



</td>
</tr>
<tr>
<td valign="top">

<code>--authorization-url "<i class="varname">&lt;url&gt;</i>"</code>



</td>
<td valign="top">

Enter the *Authorization URL* provided by your administrator.



</td>
</tr>
<tr>
<td valign="top">

<code>--token-url "<i class="varname">&lt;url&gt;</i>"</code>



</td>
<td valign="top">

Enter the *Token URL* provided by your administrator.



</td>
</tr>
</table>



<a name="loioeb7228a171a842fa84e48c899d48c970__section_secrets_file"/>

## Log in by Passing OAuth Client Information in a Secrets File

You can log in more securely by passing the OAuth client information in a secrets file instead of on the command line.

> ### Note:  
> You must have write access to the CLI installation folder.

To log in, enter the following command and press [Return\]:

```
datasphere login 
    --secrets-file <file>.json
```

> ### Note:  
> You will be directed to log in with your SAP Datasphere username and password in a browser window once at the beginning of your OAuth session to determine your space permissions.

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

<code>--secrets-file <i class="varname">&lt;file&gt;</i>.json</code>



</td>
<td valign="top">

Prepare a .json file with the following syntax:

```
{
    "client_id": "<client-id>",
    "client_secret": "<client-secret>",
    "authorization_url": "<authorization-url>",
    "token_url": "<token-url>"
  }
```

> ### Note:  
> Secrets files use versions of the options with underscores instead of hyphens.



</td>
</tr>
</table>



<a name="loioeb7228a171a842fa84e48c899d48c970__section_extracting_tokens"/>

## Avoid Running a Login Command by Extracting Access and Refresh Tokens

You can avoid running a `login` command \(and entering your SAP Datasphere username and password\) at the beginning of each OAuth session by extracting the personal access and refresh tokens and passing them either as options or in a secrets file.

To extract your tokens, log into `datasphere` as usual and then enter the following command and press [Return\]:

```
datasphere secrets show
```

Then copy the values for `access_token` and `refresh_token`. You can pass these values either as options on the command line or in an options file.

> ### Note:  
> Your access and refresh tokens are valid for 720 hours \(30 days\).

Having extracted your tokens, you no longer need to log in at the beginning of your session and can pass your tokens in a secrets file with any command.

For example, the following command, to read a space, can be run without having logged in beforehand:

```
datasphere spaces read --space My_SPACE --options-file <options-file>.json --secrets-file <secrets-file>.json
```

Where the <code><i class="varname">&lt;options-file&gt;</i>.json</code> contains appropriate options and the <code><i class="varname">&lt;secrets-file&gt;</i>.json</code> contains the following options:

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

