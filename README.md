Installation Guide:

1. SQL Dump

            Add your .sql dump to roles/db-config/files.
  
            Change Ansible task to the name of your sql dump:
  
                  roles/db-config/tasks/main.yml line 17

2. Group Variables

            Add developer email to group_vars/all/main.yml line 6.
  
            Add postgres password to group_vars/all/main/yml line 12.

3. Remote host configuration

            Add remote host variables to inventory/remote.

4. Import script

            Configure askbot.rb import script for your user, host, and password.

5. Auth User Emails

            For the development environment, all user emails are set to the developer's email address + the user's id.
  
            Add dev email to roles/db-config/main.yml line 136.
            
6. Run Ansible playbook
           
            sudo ansible-playbook -i inventory/remote -s -K -u <user> master.yml
            -replace <user> with your username.
            
7. Run development server
            
            sudo bundle exec rails s -b 0.0.0.0
            Access dev site through http://<ip>:3000
