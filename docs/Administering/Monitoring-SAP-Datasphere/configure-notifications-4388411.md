<!-- loio4388411066ef476aa99e4f35ce64bab6 -->

# Configure Notifications

Configure notifications about system events and network connection issues, and define the SMTP server to be used for email deliveries.



<a name="loio4388411066ef476aa99e4f35ce64bab6__section_rkp_dvm_jrb"/>

## Notify All Users about Network Connection Issues

When there are problems with a system, your users would like to know whether it is something that they control or if the issues are related to the network. You can't create messages for all situations, but you can let them know when the network connection is unstable.

To turn on the connection notification:

1.  In the side navigation area, click *System* \> *Administration* \> *Notifications*.

2.  To enable editing of all settings on the page, click *Edit*.

3.  In the *Connections Notifications* section, change the toggle to *ON*.

4.  Click *Save* to commit your changes.


When the notification is on, everyone who uses the application on that tenant will see the notification in the top right corner of their application.



<a name="loio4388411066ef476aa99e4f35ce64bab6__section_bvv_tkc_fbc"/>

## Notify Users When They are Added to the Tenant

By default, when users are added to your SAP Datasphere tenant, they receive a welcome email which contains a link to the tenant so they can activate their account and log in for the first time. You can disable the welcome email from being sent to new users. You may want to do so in the following cases:

-   When SAML single sign-on \(SSO\) is setup and it's not necessary for the users to activate their account.

-   When you want to setup single sign-on \(SSO\) before users are given the go to access the system.

-   When the custom SAML Identity Provider \(IdP\) is changed.

-   When you need to import users from a public tenant to a private tenant.


To disable the welcome email notification:

1.  In the side navigation area, click *System* \> *Administration* \> *Notifications*.

2.  To enable editing of all settings on the page, click *Edit*.

3.  In the *Welcome Email* section, toggle the button to *Off*.

4.  Click *Save*.


> ### Note:  
> If you disable the welcome email and then add a user who doesn't have an activated account for SAP Datasphere, they will not be able to access the system. The new user needs to go to the tenant log-on page and click "Forgot password?". They must enter the email address associated with their account and follow the instructions of the received email to set up a password.



<a name="loio4388411066ef476aa99e4f35ce64bab6__section_yt1_vvm_jrb"/>

## Configure Custom SMTP Server

Configuring an email server of your choice ensures greater security and flexibility while delivering email for your business.

1.  In the side navigation area, click *System* \> *Administration* \> *Notifications*.

2.  To enable editing of all settings on the page, click *Edit*.

3.  In the *Email Server Configuration* section, select *Custom*, and complete the following properties.

4.  Click *Check Configuration* or *Save* to successfully validate the configuration details.


