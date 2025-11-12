<!-- loio5454a8cfdb9845a9b6c772d63b8e92ec -->

# Prepare Connectivity for Generic SFTP

To connect to the SFTP server, a public host key is required to verify the server's identity. Additionally, to successfully validate and use a Generic SFTP connection to an on-premise SFTP server, Cloud Connector is required.



<a name="loio5454a8cfdb9845a9b6c772d63b8e92ec__section_fpc_2bx_jbc"/>

## Replication Flows

Before you can use the connection for replication flows, the following is required:



### Expected Format for Host Key

The expected format of the file provided in the host key is one or more lines, each composed of the following elements:

`<server host key algorithm> <SHA-256 fingerprint> <optional-comment>`

> ### Example:  
> The following is a valid file with two entries:
> 
> ```
> ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIEMXBFYDfcYMW0dccgbJ/TfhpTQhc5oR06jKIg+WCarr myuser@myhost
> ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAACAQDRqWbaMxSetrsAtTHFaxym4rVqV1yb4umqhDJbJ0H63T+wn8lm+Ev/i/u+8BZT9nvzXZqbn1rezWZvXK234SkfDFzTIb37vqlgPagrZlUc9DGAey6F4irQcgEQjiSAczsjNzYun2yrpsL/9QBahFdeCKUPNQIXYU8ctbEOxqiOzvsNH4EsobiAS+leteRA0Pe2hiOaTODj4o3e5Pug4hugr8p/tJPFVC5z7MBX9XPs6qpSAs81oZ0hZYdF4bjfHmaTNJTjrJCfg4RHTBVPsBKOLFBxwPhjcQlccNQ33voYF59bM37IyqV6h+Mz8up/GrMVA7ka6np3fAyJhGhRPsLEZZY8h6KK633HLDqglkisQP87ewz8SRrcIHnhrP3hTBClx484XxCBMWl4pUElQ+p32322v+KbwCEHpYj5pitnieekiXpsMNXOCZdyA/llToPqzlGkbcI3z8ScOLvoX2qsrjOWMJlKOpwIcA/NzwU/9LlFsecQvFzGowYYFHMnDypAnhCcwQz9BvqmjRRJGbMONmzq39HTBMd0rfyoui8KCOGkN/d89aZERzH6jZa9ft6qzaBuhKc1TND/m1+IBEUoWZUX3XurYaJu/0awACjVeyB0dhGafSRGhskBy2oOlX97ZOoErkIoc5BQRCLpa3OjHywzd6BLnTKKJRS6pvfG9w==
> ```



### Obtain Host Key

Provide the host public key through a trusted channel. If your Windows 10, Linux, or MacOS machine has a trusted channel, perform the following steps by replacing the following elements with the specified values:

-   `$HOST` with the host name value of your connection
-   `$PORT` with the port value of your connection

Use the resulting file `host_key.pub.txt`, in the directory where you run the specified command, as the Host Key for your connection. The specified commands are as follows:

-   **Windows 10:** In PowerShell, run the following command:

    `(ssh-keyscan -p $PORT $HOST 2>$null) -replace '^[^ ]* ','' > host_key.pub.txt`

-   **Linux/MacOS:** In a unix-compliant shell with both `ssh-keyscan` and `sed` commands \(both are installed in your system\), obtain the key through the following command:

    `ssh-keyscan -p $PORT $HOST 2>/dev/null | sed "s/^[^ ]* //" > host_key.pub.txt`


> ### Note:  
> If your machine doesn't have a trusted channel, we recommend asking your administrator for the public host key to avoid man-in-the-middle attacks.



### Cloud Connector for On-Premise SFTP Servers

An administrator has installed and configured Cloud Connector to connect to your on-premise source.

For more information, see [Configure Cloud Connector](configure-cloud-connector-f289920.md).

**Related Information**  


[Generic SFTP Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/b645de78a8374c24871ab6169be40d35.html "Use a Generic SFTP connection to connect to and access files on a Secure File Transfer Protocol (SFTP) server.") :arrow_upper_right:

