Installation Guide:

1. SQL Dump

            Add your sql dump to group_vars/all/main.yml line 53. 

2. Dev email and postgres password

            Add developer email to group_vars/all/main.yml line 6.
  
            Add postgres password to group_vars/all/main/yml line 12.

3. Remote host configuration

            Add remote host variables to inventory/remote.

4. Import script

            Modify askbot.rb import script for your user, host, and password.

5. Auth User Emails
            
            If your sql dump has the same email for every user, then the askbot.rb import script will not create
            any users. This is fixed by setting all user emails to the developers email address + each user's id. 
            If your sql dump has unique emails for each user then skip this step. 
  
            Change update_auth_user as necessary in group_vars/all/main.yml line 58.
            
6. Run Ansible playbook
           
            sudo ansible-playbook -i inventory/remote -s -K -u <user> master.yml
            -replace <user> with your username.
            
7. Run development server
            
            sudo bundle exec rails s -b 0.0.0.0
            Access dev site through http://<ip>:3000
