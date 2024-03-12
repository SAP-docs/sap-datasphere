<!-- copyab4db761b9c84ac3910648ec7cba1dc6 -->

# Additional Information About Remote Tables

You can add remote tables located in SAP BW bridge spaces to a transformation flow. Note that remote tables located in SAP BW bridge spaces must be shared with the SAP Datasphere space you are using to create your transformation flow.

> ### Note:  
> If you add a remote table located in SAP BW bridge spaces, it is not possible to preview the data being output by the view.

If you add a remote table located in an SAP BW bridge space that is configured to load delta changes, the system adds the following input parameters to the *Properties* panel of the view transform:

-   REQTSN\_LOW

    When loading delta changes, the value of this input parameter is the watermark. When loading all active records, the value of this input parameter is the minimum timestamp. For more information, see [Watermarks](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/890897f00a4944c7a6f90d3816a8d4c6.html "") :arrow_upper_right:.

-   REQTSN\_HIGH

    The value of this input parameter is the maximum timestamp.

-   EXTRACTION\_MODE

    The value of this input parameter is DELTA\_AI to indicate the loading of delta changes from the remote table.


