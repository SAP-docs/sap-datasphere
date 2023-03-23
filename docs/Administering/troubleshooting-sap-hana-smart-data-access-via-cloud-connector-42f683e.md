<!-- loio42f683edbf6742b19cf15e7a18b8a607 -->

# Troubleshooting SAP HANA Smart Data Access via Cloud Connector

These are some of the most common issues that can occur when you use the Cloud Connector to connect to on-premise remote sources via SAP HANA Smart Data Access.



<a name="loio42f683edbf6742b19cf15e7a18b8a607__section_jy2_k3b_zpb"/>

## 1. The connectivity proxy is not enabled

The following error occurs if you try to connect to a remote source using the Cloud Connector, but the connectivity proxy hasn’t been enabled:

```
[LIBODBCHDB SO][HDBODBC] Communication link failure;-10709 Connection failed (RTE:[89001] 
Cannot resolve host name '<connectivity_proxy_host>' rc=-2: 
Name or service not known (<virtual_host>:<virtual_port>))
```

SAP Datasphere takes care of enabling the connectivity proxy. This might take a while.



<a name="loio42f683edbf6742b19cf15e7a18b8a607__section_c5m_k3b_zpb"/>

## 2. The connectivity proxy is enabled but not fully ready to serve requests

The following error occurs if the connectivity proxy has been enabled but is not yet ready to be used:

```
[LIBODBCHDB SO][HDBODBC] Communication link failure;-10709 Connection failed (RTE:[89006] 
System call 'connect' failed, rc=111:
Connection refused {<connectivity_proxy_ip>:<connectivity_proxy_port>)} {ClientPort:<client_port>} (<virtual_host>:<virtual_port>))
```

SAP Datasphere takes care of enabling the connectivity proxy. This might take a while.



<a name="loio42f683edbf6742b19cf15e7a18b8a607__section_ynn_k3b_zpb"/>

## 3. The virtual host specified in the connection details includes an underscore

The following error occurs if you’ve used a virtual host name with an underscore, for example, hana\_01:

```
[LIBODBCHDB SO][HDBODBC] General error;-10719 Connect failed (invalid SERVERNODE 'hana_01:<virtual_host>:<virtual_port>')
```

Virtual host names must not contain underscores.



<a name="loio42f683edbf6742b19cf15e7a18b8a607__section_e24_k3b_zpb"/>

## 4. The virtual host specified in the connection details is unreachable

The following error occurs if the specified virtual host cannot be reached:

```
[LIBODBCHDB SO][HDBODBC] Communication link failure;-10709 Connection failed (RTE:[89132] 
Proxy server connect: connection not allowed by ruleset (<virtual_host>:<virtual_port>))
```



<a name="loio42f683edbf6742b19cf15e7a18b8a607__section_kx4_k3b_zpb"/>

## 5. The selected location ID is invalid.

The following error occurs if an invalid location ID was specified in the *Data Source Configuration* of the SAP Datasphere *Administration*:

```
[LIBODBCHDB SO][HDBODBC] Communication link failure;-10709 Connection failed (RTE:[89132] 
Proxy server connect: Network unreachable (<virtual_host>:<virtual_port>))

```



<a name="loio42f683edbf6742b19cf15e7a18b8a607__section_yz2_n5z_fqb"/>

## 6. The Cloud Connector's IP is missing or is incorrectly specified in the SAP Datasphere IP allowlist for trusted Cloud Connector IPs

The following error occurs when the Cloud Connector's IP is not included in the allowlist list:

```
[LIBODBCHDB SO][HDBODBC] Communication link failure;-10709 Connection failed (RTE:[89133] 
Proxy server connect: Network unreachable (<virtual_host>:<virtual_port>))

```



<a name="loio42f683edbf6742b19cf15e7a18b8a607__section_kqv_gmt_kqb"/>

## 7. The Cloud Connector certificate has expired

The following error occurs when the subaccount certificate used in the Cloud Connector has expired:

```
[LIBODBCHDB SO][HDBODBC] Communication link failure;-10709 Connection failed (RTE:[89133] 
Proxy server connect: Network unreachable (<virtual_host>:<virtual_port>))

```

You can find the related logs in the `ljs_trace.log` file in the Cloud Connector. For example:

```
2021-07-29 04:50:42,131 +0200#ERROR#com.sap.core.connectivity.tunnel.client.notification.NotificationClient#notification-client-277-3# 
#Unable to handshake with notification server connectivitynotification.cf.sap.hana.ondemand.com/<virtual_host>:<virtual_port> 
javax.net.ssl.SSLException: Received fatal alert: certificate_expired

```

For information about renewing a subaccount certificate, see [Update the Certificate for a Subaccount](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/071708a655de4486b498cf5b16fb8ea8.html).



<a name="loio42f683edbf6742b19cf15e7a18b8a607__section_anp_k3b_zpb"/>

## 8. The on-premise backend system requires TCP SSL

The following error occurs if the on-premise backend system requires TCP SSL:

```
[LIBODBCHDB SO][HDBODBC] Communication link failure;-10709 Connection failed (RTE:[89008] 
Socket closed by peer (<virtual_host>:<virtual_port>))
```

