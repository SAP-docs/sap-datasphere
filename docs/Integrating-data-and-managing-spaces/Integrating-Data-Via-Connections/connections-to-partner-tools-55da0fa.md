<!-- loio55da0faa34d448f28f47021e99e18351 -->

# Connections to Partner Tools

Extend connectivity beyond SAP Datasphere standard remote connectivity and cover additional data sources that are available with partner tools.

Connections to partner tools are created differently compared to other connections in SAP Datasphere.

When creating a connection to a partner tool, an Open SQL schema is generated in SAP Datasphere and information about host, port and credentials of the Open SQL schema is transferred to the partner tool. To be able to send data to the Open SQL schema, during the connection creation process the partner tool on their side establishes a connection to the Open SQL schema.

To successfully validate a new connection and before data can be written to the Open SQL schema and you can use it in the Data Builder, the IP address or addresses of the partner tool need to be added to the IP allowlist in SAP Datasphere. To get the relevant IP addresses, depending on the partner tool you might need to contact the Account Manager or the support team \(for Adverity, for example\), or you can find and copy the IP addresses in the last step of the connection cration wizard \(for Precog, for example\).

After the connection has been created in the SAP Datasphere space, you can use it in the *Data Builder* to create a view.

> ### Note:  
> -   The Open SQL schema \(respectively the database user for which the schema has been created\) doesn't appear in the *Connections* app but only in the *Database Users* section in *Space Management*.
> 
> -   In the *Data Builder*, unlike other Open SQL schemas, the Open SQL schema generated with the partner connection doesn't appear in *Source Browser* \> *Sources*. Instead, you can find the corresponding partner connection in *Source Browser* \> *Sources* \> *Connections*.
> 
>     Once the partner tool fetches data from a source, in the *Data Builder* you can find the corresponding table in *Source Browser* \> *Sources* \> *Connections* \> *<partner connection name\>*. When importing the table into the *Data Builder*, a local table is created and deployed. You can use it the same way as any other table originating from an Open SQL schema.

You can access the Open SQL Schema that has been generated for the partner connection from a third-party BI client via ODBC. For more information, see [Consume Data in Power BI and Other Clients, Tools, and Apps via ODBC](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/4db6f5a329af44509ae422ad707877b2.html "You can consume data exposed as views in Microsoft Power BI and other third-party clients, tools, and apps via an Open SQL schema and ODBC.") :arrow_upper_right:.

**Related Information**  


[Adverity Connections](adverity-connections-63e9ff5.md "Extend connectivity beyond SAP Datasphere standard remote connectivity and cover additional data sources that are available with Adverity.")

[Precog Connections](precog-connections-6e5f225.md "Extend connectivity beyond SAP Datasphere standard remote connectivity and cover additional data sources that are available with Precog.")

