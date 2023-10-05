<!-- loio14aedf6cecce474b93b2d5187662a090 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Set a Password Policy for Database Users

Users with the *DW Administrator* role \(administrators\) can set a password policy to cause database user passwords to expire after a specified number of days.



<a name="loio14aedf6cecce474b93b2d5187662a090__context_y2d_1dr_1tb"/>

## Context

Users with the *DW Space Administrator* role \(space administrators\) can create database users in their spaces to allow the connection of ETL tools to write to and read from Open SQL schemas attached to the space schema \(see[Integrating Data via Database Users/Open SQL Schemas](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/3de55a78a4614deda589633baea28645.html "Create a database user in your space to read and write directly to the SAP HANA Cloud database on which SAP Datasphere runs. Each database user has an Open SQL schema, which is attached to a space schema and provides a secure method for exchanging data with the space.") :arrow_upper_right:\).



<a name="loio14aedf6cecce474b93b2d5187662a090__steps_t4h_lbr_1tb"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Security*.

2.  In the *Password Policy Configuration* section, enter the number of days after which a database user's password will expire.

    After this period, the user will be prompted to set a new password.

    > ### Note:  
    > The password policy applies only to database users where the *Enable Password Policy* property is selected. If a user does not log on with their initial password during this period, they will be deactivated until their password is reset.


