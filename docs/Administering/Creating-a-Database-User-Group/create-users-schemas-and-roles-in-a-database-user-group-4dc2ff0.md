<!-- loio4dc2ff03b37e482fb209dd08a9550826 -->

# Create Users, Schemas, and Roles in a Database User Group

A database user group administrator can create users, schemas, and roles to organise and staff their group. Creating schemas and roles and granting, revoking, and dropping roles require the use of SAP Datasphere stored procedures.

This topic contains the following sections:

-   [Log In With Your Database User Group Administrator](create-users-schemas-and-roles-in-a-database-user-group-4dc2ff0.md#loio4dc2ff03b37e482fb209dd08a9550826__section_log_in)
-   [Create a User](create-users-schemas-and-roles-in-a-database-user-group-4dc2ff0.md#loio4dc2ff03b37e482fb209dd08a9550826__section_create_user)
-   [Create a Schema](create-users-schemas-and-roles-in-a-database-user-group-4dc2ff0.md#loio4dc2ff03b37e482fb209dd08a9550826__section_create_schema)
-   [Grant a Role to a User or to Another Role](create-users-schemas-and-roles-in-a-database-user-group-4dc2ff0.md#loio4dc2ff03b37e482fb209dd08a9550826__section_grant_role)
-   [Revoke a Role](create-users-schemas-and-roles-in-a-database-user-group-4dc2ff0.md#loio4dc2ff03b37e482fb209dd08a9550826__section_revoke_role)
-   [Drop a Role](create-users-schemas-and-roles-in-a-database-user-group-4dc2ff0.md#loio4dc2ff03b37e482fb209dd08a9550826__section_drop_role)



<a name="loio4dc2ff03b37e482fb209dd08a9550826__section_log_in"/>

## Log In With Your Database User Group Administrator

To connect to SAP HANA Cloud with the administrator, select your newly created user group in the list, and click *Open Database Explorer*, enter the password when requested, and click *OK*.

The SAP HANA database explorer opens with your database user group at the top level. You can now use the SQL editor to create users, roles and schemas.

You can review your privileges with the following statement:

```
select * from effective_privileges where user_name = current_user;
```



<a name="loio4dc2ff03b37e482fb209dd08a9550826__section_create_user"/>

## Create a User

You can create a user in your user group with the following statement:

```
CREATE USER <user_name> PASSWORD <pwd> SET USERGROUP <DBgroup_name>
```

> ### Note:  
> To avoid possible conflicts, we recommend that you use the prefix <code>DWCDBGROUP#<i class="varname">&lt;DBgroup_name&gt;</i>#</code> when naming users, schemas, and roles in your group \(see [Rules for Technical Names](../Creating-Spaces-and-Allocating-Storage/rules-for-technical-names-982f9a3.md)\).

In our example, we create a new user, `DWCDBGROUP#DWMIGRATE#BOB`, in our `DWMIGRATE` group:

```
CREATE USER DWCDBGROUP#DWMIGRATE#BOB password “Welcome1” set usergroup “DWCDBGROUP#DWMIGRATE”;
```



<a name="loio4dc2ff03b37e482fb209dd08a9550826__section_create_schema"/>

## Create a Schema

You can create a schema in your database user group by using the following SAP Datasphere stored procedure:

```
CALL "DWC_GLOBAL"."CREATE_USERGROUP_SCHEMA"
(
	SCHEMA_NAME => '<schema_name>',
	OWNER_NAME => '<user_name>'
					);
```

> ### Note:  
> To avoid possible conflicts, we recommend that you use the prefix <code>DWCDBGROUP#<i class="varname">&lt;DBgroup_name&gt;</i>#</code> when naming users, schemas, and roles in your group \(see [Rules for Technical Names](../Creating-Spaces-and-Allocating-Storage/rules-for-technical-names-982f9a3.md)\).

The owner of the new schema must be a user of the database user group. If the owner name is set to null, then the database user group administrator is set as the owner.

In our example, we create a new schema, `DWCDBGROUP#DWMIGRATE#STAGING`, and set `BOB` as the owner:

```
CALL "DWC_GLOBAL"."CREATE_USERGROUP_SCHEMA"
(
	SCHEMA_NAME => 'DWCDBGROUP#DWMIGRATE#STAGING,
	OWNER_NAME => 'DWCDBGROUP#DWMIGRATE#BOB'
);
```



<a name="loio4dc2ff03b37e482fb209dd08a9550826__section_create_role"/>

## Create a Role

You can create a role in your database user group by using the following SAP Datasphere stored procedure:

```
CALL "DWC_GLOBAL"."CREATE_USERGROUP_ROLE"
(
	ROLE_SCHEMA_NAME => '<schema_name>',
	ROLE_NAME => '<role_name>'
);
```

> ### Note:  
> To avoid possible conflicts, we recommend that you use the prefix <code>DWCDBGROUP#<i class="varname">&lt;DBgroup_name&gt;</i>#</code> when naming users, schemas, and roles in your group \(see [Rules for Technical Names](../Creating-Spaces-and-Allocating-Storage/rules-for-technical-names-982f9a3.md)\).

Once the role is created, you can grant it to a user or to another role, revoke it, and drop it.

In our example, we create a new role, `DWCDBGROUP#DWMIGRATE#DWINTEGRATOR` in the schema `STAGING`:

```
CALL "DWC_GLOBAL"."CREATE_USERGROUP_ROLE"
(
	ROLE_SCHEMA_NAME => 'DWCDBGROUP#DWMIGRATE#STAGING',
	ROLE_NAME => 'DWCDBGROUP#DWMIGRATE#DWINTEGRATOR'
);
```



<a name="loio4dc2ff03b37e482fb209dd08a9550826__section_grant_role"/>

## Grant a Role to a User or to Another Role

You can grant a role to a user or to another role in your database user group by using the following SAP Datasphere stored procedure:

```
CALL "DWC_GLOBAL"."GRANT_USERGROUP_ROLE"
(
	ROLE_SCHEMA_NAME => '<schema_name>',
	ROLE_NAME => '<role_name>',
	GRANTEE => '<user_name>',
	GRANTEE_ROLE_NAME => NULL,
	WITH_ADMIN_OPTION => FALSE
);

```

The role schema, grantee, and grantee role must all be in the same database user group.

In our example, we grant the `DWCDBGROUP#DWMIGRATE#DWINTEGRATOR` role to our user, `BOB`:

```
CALL "DWC_GLOBAL"."GRANT_USERGROUP_ROLE"
(
	ROLE_SCHEMA_NAME => 'DWCDBGROUP#DWMIGRATE#STAGING',
	ROLE_NAME => 'DWCDBGROUP#DWMIGRATE#DWINTEGRATOR',
	GRANTEE => 'DWCDBGROUP#DWMIGRATE#BOB',
	GRANTEE_ROLE_NAME => NULL,
	WITH_ADMIN_OPTION => FALSE
);

```



<a name="loio4dc2ff03b37e482fb209dd08a9550826__section_revoke_role"/>

## Revoke a Role

You can revoke a role from a user by using the following SAP Datasphere stored procedure:

```
CALL "DWC_GLOBAL"."REVOKE_USERGROUP_ROLE"
(
	ROLE_SCHEMA_NAME => '<schema_name>',
	ROLE_NAME => '<role_name>',
	GRANTEE => '<user_name>',
	GRANTEE_ROLE_NAME => NULL
);

```

In our example, we revoke the `DWCDBGROUP#DWMIGRATE#DWINTEGRATOR` role from `BOB`:

```
CALL "DWC_GLOBAL"."REVOKE_USERGROUP_ROLE"
(
	ROLE_SCHEMA_NAME => 'DWCDBGROUP#DWMIGRATE#STAGING',
	ROLE_NAME => 'DWCDBGROUP#DWINTEGRATOR',
	GRANTEE => 'DWCDBGROUP#DWMIGRATE#BOB',
	GRANTEE_ROLE_NAME => NULL
);

```



<a name="loio4dc2ff03b37e482fb209dd08a9550826__section_drop_role"/>

## Drop a Role

You can drop a role by using the following SAP Datasphere stored procedure:

```
CALL "DWC_GLOBAL"."DROP_USERGROUP_ROLE"
(
ROLE_SCHEMA_NAME => '<schema_name>',
ROLE_NAME => '<role_name>'
        );


```

In our example, we drop the `DWCDBGROUP#DWMIGRATE#DWINTEGRATOR` role:

```
CALL "DWC_GLOBAL"."DROP_USERGROUP_ROLE"
(
ROLE_SCHEMA_NAME => 'DWCDBGROUP#DWMIGRATE#STAGING',
ROLE_NAME => 'DWCDBGROUP#DWMIGRATE#DWINTEGRATOR'
        );


```

