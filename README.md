# KodeKloud-DevOps
100 days of devops learning.

## Day-01 - Linux User Setup with Non-Interactive Shell
  Created a user with Non-Interactive shell using 
  ### sudo useradd -s /bin/false username
    -s - specifies the login shell for auser 
    /bin/false - special shell that doen not allow interactive login.
                 Immediately exits when user tries to log in

    cat /etc/passwd | grep username - Verify user Creation

## Day 2: Temporary User Setup with Expiry
  Created user with account expiry date
  ### sudo useradd -m -e 2026-04-01 username
      -m - Create home directory 
      -e yyyy-mm-dd - set account expiry date
      After this date account is not deleted, just disabled

      sudo chage -E -1 username  -> To remove expiry
      sudo chage -E 2026-04-01 username  -> To set expiry to existing account

