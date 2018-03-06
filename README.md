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

Import script:
-Configure askbot.rb import script for your user, host, and password.

Auth User Emails:
-For the development environment, all user emails are set to the developer's
email address + the user's id.
-Add dev email to roles/db-config/main.yml line 136
