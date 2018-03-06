Installation Guide:

SQL Dump:
-Add your .sql dump to roles/db-config/files
-Change Ansible task to the name of your sql dump:
  - roles/db-config/tasks/main.yml line 17

Group Variables:
-Add developer email to group_vars/all/main.yml line 6
-Add postgres password to group_vars/all/main/yml line 12

Remote host configuration:
-Add remote host variables to inventory/remote
