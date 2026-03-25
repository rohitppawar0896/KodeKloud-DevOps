## Day-01 - Linux User Setup with Non-Interactive Shell
  Created a user with Non-Interactive shell using 
  ### Solution
    sudo useradd -s /bin/false username
    -s - specifies the login shell for auser 
    /bin/false - special shell that doen not allow interactive login.
                 Immediately exits when user tries to log in

    cat /etc/passwd | grep username - Verify user Creation