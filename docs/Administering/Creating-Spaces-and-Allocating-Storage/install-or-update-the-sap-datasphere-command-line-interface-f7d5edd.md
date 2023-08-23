<!-- loiof7d5eddf20a34a1aa48d8e2c68a44e28 -->

# Install or Update the SAP Datasphere Command Line Interface

The SAP Datasphere command line interface \(`datasphere`\) is a `Node.js` package that you download using the Node Package Manager \(`npm`\).



## Context

`datasphere` is listed on [https://www.npmjs.com/](https://www.npmjs.com/) at [https://www.npmjs.com/package/@sap/datasphere-cli](https://www.npmjs.com/package/@sap/dwc-cli).

> ### Note:  
> The SAP Datasphere command line interface module has been renamed from `dwc` to `datasphere`. The command `dwc` will be decommissioned at the end of 2023: please use the new `datasphere` command instead.



### Prerequisites

You have installed the following on your system:

-   `Node.js` version \>= 18
-   `npm` version \>= 8

`npm` is distributed with `Node.js`. Therefore, when you download `Node.js`, `npm` is automatically installed. To download the `Node.js` installer, see [nodejs.org](https://nodejs.org/en/).

> ### Note:  
> You can test if `Node.js` and `npm` are installed on your system by executing the following commands:
> 
> -   `node -v`
> -   `npm -v`
> 
> If `Node.js` and `npm` are already installed, then their current versions will appear. If you receive an error, you have not installed them yet.



## Procedure

1.  Run the following command:

    ```
    npm install -g @sap/datasphere-cli
    ```

    > ### Note:  
    > To update `datasphere` to the latest version at any time, you just need to run `npm install -g @sap/datasphere-cli` again.

2.  Test if the installation was successful by running the following command:

    ```
    datasphere --version
    ```

3.  Run the following command to download the file of available `datasphere` commands:

    ```
    datasphere cache init --host "<url>"
    ```

    Where *<url\>* is the URL of your SAP Datasphere tenant. You can copy the URL of any page in your tenant.

    > ### Note:  
    > If new commands become available for `datasphere`, you will be prompted to run this command again.

4.  When prompted, enter the passcode to authorize the command.


