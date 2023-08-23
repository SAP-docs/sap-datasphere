<!-- loio167c05c673dc4715baba8d5d305abb1e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating an Authorization Scenario

Authorization scenarios help you control data access for business entities leveraging data access controls.



## Context

Authorization scenarios help you filter the data available to specific business entities and their subsets based on existing data access controls.

For example, a manager wants to access their employees' data. They only should see employees from their team. An authorization scenario can help them make sure they only see data that is relevant to the team they manage.



## Procedure

1.  Go to the *Business Builder* and select *New Authorization Scenario*.

2.  Select a data access control. Make sure to select a deployed data access control to have access to data preview.

3.  Click *Create*.

4.  Go to the *Data Restrictions* tab and click <span class="FPA-icons"></span> *Data Restrictions*.

5.  Select a *Business Entity*.

6.  You have access to the business entity's key definitions. It gives you access to key members. For each business entity used as data restriction, you need to map each key member to the data access control's criteria column.

    To learn more about defining keys for a business entity, see [Define a Key](define-a-key-9748bab.md).

7.  Click *Save* to save your authorization scenario.

    You can define several restrictions on several business entities within the same authorization scenario.




<a name="loio167c05c673dc4715baba8d5d305abb1e__result_jfz_zy3_qmb"/>

## Results

Your new authorization scenario is ready to use. You can add as many *Data Restrictions* as you need within your authorization scenario.

Data Preview helps you make sure that the authorization scenario works. You can see the business entity's keys used as data restrictions and the data allowed by the underlying data access control that is relevant to the user.

**Related Information**  


[Assigning an Authorization Scenario](assigning-an-authorization-scenario-2e62354.md "Once you've created an authorization scenario, you can assign it to a business entity to tailor data access to different business contexts.")

[Using an Authorization Scenario in a Consumption Model](using-an-authorization-scenario-in-a-consumption-model-54839e8.md "Choose from your business entities which authorization scenarios to use in a consumption model.")

[Securing Data with Data Access Controls](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Data access controls allow you to apply row-level security to your objects. When a data access control is applied to a data layer view or a business layer object, any user viewing its data will see only the rows for which they are authorized, based on the specified criteria.") :arrow_upper_right:

