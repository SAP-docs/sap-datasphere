<!-- loio2e623549056943159e20bcc9240899b1 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Assigning an Authorization Scenario

Once you've created an authorization scenario, you can assign it to a business entity to tailor data access to different business contexts.



## Context

Authorization scenarios help you define different business authorization contexts that act as data filters. A manager wants to access their employees' data. They only want to see employees from their team. An authorization scenario can help them make sure they only see data that is relevant to the team they manage.



## Procedure

1.  In the *Business Builder*, select your business entity.

2.  In the *Authorization Scenario* tab, click <span class="FPA-icons"></span> *Add* and select your authorization scenario. You can add one or several authorization scenarios and use the ones that are relevant to your use-case.

3.  Under *Data Restriction Context*, click <span class="FPA-icons"></span> to open the *Select Context* dialog. You can see all available association contexts. They resolve your business entity defined as a restriction in the authorization scenario. Select your context and *Save*.

4.  In the *General* tab under *Public Data Access*, you can choose to make your model public or not. You can combine it to an authorization scenario. If you've switched on *Public Data Access* for your business entity, using an authorization scenario is optional. If you've switched off *Public Data Access* for your business entity, you have to use an authorization scenario. If your model has no authorization scenario or *Public Data Access*, you won't be able to use our model.




<a name="loio2e623549056943159e20bcc9240899b1__result_iy2_xpj_qmb"/>

## Results

You can see the different authorization scenarios you've created for your business entity in the data preview. In the Data Preview side panel, click <span class="FPA-icons"></span>. Under *Authorization Scenario*, you can directly switch from one authorization scenario to another. Authorizations are automatically applied on data.

**Related Information**  


[Creating a Consumption Model](creating-a-consumption-model-337fa99.md "Consumption models are the basis to consume your data.")

[Authorization Scenario](authorization-scenario-46d8c42.md "Authorization scenarios allow modelers to define which data is relevant to a user's context. They are made available through business entities and can be used in consumption models for specific use-cases.")

[Creating an Authorization Scenario](creating-an-authorization-scenario-167c05c.md "Authorization scenarios help you control data access for business entities leveraging data access controls.")

[Using an Authorization Scenario in a Consumption Model](using-an-authorization-scenario-in-a-consumption-model-54839e8.md "Choose from your business entities which authorization scenarios to use in a consumption model.")

