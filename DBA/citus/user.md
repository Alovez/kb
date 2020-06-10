### Create role

`CREATE ROLE role_name;`

`SELECT run_command_on_workers($$ CREATE ROLE role_name NOLOGIN; $$);`

### Grant access

`GRANT SELECT ON ALL TABLES IN SCHEMA schema_name TO role_name;`

`SELECT run_command_on_workers($$ GRANT SELECT ON ALL TABLES IN SCHEMA schema_name TO role_name; $$);`

### Role map

`grant group_role to user;`

`SELECT run_command_on_workers($$ grant group_role to user; $$);`
