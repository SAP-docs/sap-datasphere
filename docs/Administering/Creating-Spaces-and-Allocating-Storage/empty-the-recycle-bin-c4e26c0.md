<!-- loioc4e26c09325a45d3ab7011a600c8fc6c -->

# Empty the Recycle Bin

To recover the disk storage used by the data in spaces, you must delete them from the *Recycle Bin* area.

Once a space has been deleted and moved to the recycle bin \(see [Delete Your Space](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/3eb19b96e6ba41dfbffd759c5c8370bb.html "Delete a space if you are sure that you no longer need any of its content or data.") :arrow_upper_right:\), you can permanently delete it from the database.

Be aware that the following content will also be **permanently** deleted:

-   All objects and data contained in the space.
-   All connections defined in the space.
-   All objects and data contained in any Open SQL schema associated with the space.
-   All audit logs entries generated for the space, including audit log entries related to any Open SQL schema associated with the space.



<a name="loioc4e26c09325a45d3ab7011a600c8fc6c__section_vqc_dkz_dcc"/>

## Delete Spaces Permanently

> ### Caution:  
> This action cannot be undone.

1.  In the side navigation area, click ![](../images/Space_Management_a868247.png) \(*Space Management*\).

2.  In the *Recycle Bin* area, locate and select one or more spaces and click the *Delete* button.

3.  In the confirmation message, enter DELETE if you are sure that you no longer need the spaces and any of their content or data, then click the *Delete* button.

    The spaces are permanently deleted from the database and cannot be recovered.


