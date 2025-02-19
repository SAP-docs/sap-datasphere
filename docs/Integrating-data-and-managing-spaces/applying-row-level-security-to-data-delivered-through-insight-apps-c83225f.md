<!-- loioc83225fd195446f28c960671559c4a16 -->

# Applying Row-Level Security to Data Delivered through Insight Apps

All insight apps delivered through SAP Business Data Cloud are secured through data access controls. By default, no user can view any data presented in the provide SAP Analytics Cloud stories. To make data available to the users authorized to see it, you must upload your authorizations to the provided permissions table.

> ### Note:  
> When data is delivered to SAP Datasphere through SAP Business Data Cloud, any authorizations that are applied to the data in the source system are not imported. For general information about providing row-level security, see [Securing Data with Data Access Controls](https://help.sap.com/docs/SAP_DATASPHERE/be5967d099974c69b77f4549425ca4c0/a032e51c730147c7a1fcac125b4cfe14.html).



<a name="loioc83225fd195446f28c960671559c4a16__section_lcs_2x4_jdc"/>

## Procedure

1.  In your preparation space, identify the fact views and the permissions table.
2.  Prepare your permissions records in the `operator and values` format to provide row-level access to the data in your facts \(see [Create an "Operator and Values" Data Access Control](https://help.sap.com/docs/SAP_DATASPHERE/be5967d099974c69b77f4549425ca4c0/501594bf2afb4e49ab5ce254e35e3504.html)\).

    > ### Note:  
    > -   By default, users cannot see any data in the protected views. To enable them to see any data, you must have at least one permissions record in the permissions table.
    > -   To show all records to a selected user, use the ALL or \* operator.
    > -   For performance reasons, avoid having more than 5,000 permissions records for a single user.

3.  Upload the appropriately formatted `operator and values` permissions data as a CSV file \(see [Load or Delete Local Table Data](https://help.sap.com/docs/SAP_DATASPHERE/c8a54ee704e94e15926551293243fd1d/870401f211f94132909bd9f2fafd91b2.html)\).

    You can also maintain permissions data manually using the data editor \(see [Maintain Local Table Data](https://help.sap.com/docs/SAP_DATASPHERE/c8a54ee704e94e15926551293243fd1d/4bd5e641be48409c8c79336df0c4a3c7.html)\) .

4.  \[optional\] Review the data that are accessible to different users, using the **View as User** dialog \(see [Viewing Object Data](https://help.sap.com/docs/SAP_DATASPHERE/c8a54ee704e94e15926551293243fd1d/b338e4aa7e7e494eb68c383720ebfd3a.html)\).
5.  Maintain the permissions table as necessary.

