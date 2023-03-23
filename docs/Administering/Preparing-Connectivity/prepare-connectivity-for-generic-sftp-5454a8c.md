<!-- loio5454a8cfdb9845a9b6c772d63b8e92ec -->

# Prepare Connectivity for Generic SFTP

To create a Generic SFTP connection, the host's public key is required.



The host's public key should be provided through a trustable channel. If your Windows 10, Linux, or MacOS machine has such a channel, follow the steps below by replacing any occurence of `$HOST` with the host value of your connection, and `$PORT` with the port value.

Use the resulting file `host_key.pub.txt` \(found in the directory where you run the following command\) to upload the *Host Key* when creating your connection.

-   Windows 10: In PowerShell, run the following command:

    `(ssh-keyscan -t rsa -p $PORT $HOST 2>$null) -replace '^[^ ]* ','' > host_key.pub.txt`

-   Linux/MacOS: In a unix-compliant shell with both `ssh-keyscan` and `sed` commands \(both are usually already installed in your system\), obtain the key through the following command:

    `ssh-keyscan -t rsa -p $PORT $HOST 2>/dev/null | sed "s/^[^ ]* //" > host_key.pub.txt`


> ### Note:  
> If your machine doesn't have a trustable channel, we recommend asking your administrator for the public host key to avoid man-in-the-middle attacks.

