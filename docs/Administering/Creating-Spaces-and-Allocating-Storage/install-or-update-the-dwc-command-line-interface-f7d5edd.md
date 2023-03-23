<!-- loiof7d5eddf20a34a1aa48d8e2c68a44e28 -->

# Install or Update the `dwc` Command Line Interface

The SAP Datasphere command line interface \(`dwc`\) is a `Node.js` package that you download using the Node Package Manager \(`npm`\).



## Context

`dwc` is listed on [https://www.npmjs.com/](https://www.npmjs.com/) at [https://www.npmjs.com/package/@sap/dwc-cli](https://www.npmjs.com/package/@sap/dwc-cli).



### Prerequisites

You have installed the following on your system:

-   `Node.js` version \>= 12.21.0
-   `npm` version \>= 6

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
    npm install -g @sap/dwc-cli
    ```

    > ### Note:  
    > To update `dwc` to the latest version at any time, you just need to run `npm install -g @sap/dwc-cli` again.

2.  Test if the installation was successful by running the following command:

    ```
    dwc -v
    ```

3.  Run the following command to download the file of available `dwc` commands:

    ```
    dwc cache init -H "<server-url>"
    ```

    Where *<server-url\>* is the URL of your SAP Datasphere tenant. You can copy the URL of any page in your tenant.

    > ### Note:  
    > If new commands become available for `dwc`, you will be prompted to run this command again.

4.  When prompted, enter the passcode to authorize the command.


