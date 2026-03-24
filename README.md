# KodeKloud-DevOps
100 days of devops learning.

## Day-01 - Linux User Setup with Non-Interactive Shell
  Created a user with Non-Interactive shell using 
  ### Solution
    sudo useradd -s /bin/false username
    -s - specifies the login shell for auser 
    /bin/false - special shell that doen not allow interactive login.
                 Immediately exits when user tries to log in

    cat /etc/passwd | grep username - Verify user Creation

## Day 2: Temporary User Setup with Expiry
  Created user with account expiry date
  ###  Solution
      sudo useradd -m -e 2026-04-01 username
      -m - Create home directory 
      -e yyyy-mm-dd - set account expiry date
      After this date account is not deleted, just disabled

      sudo chage -E -1 username  -> To remove expiry
      sudo chage -E 2026-04-01 username  -> To set expiry to existing account

## Day 3: Secure Root SSH Access
  Disabled ssh login of root user
  ### Solution
    sudo vi /etc/ssh/sshd_config
    change entry for PermitRootLogin yes to PermitRootLogin no
    after that restart the sshd service
    sudo systemctl restart sshd

## Day 4: Script Execution Permissions
Ensure all users can execute the script
### Solution
    sudo chmod 755 script.sh
    to add execute permission read permission is required.
    755 permits 
    Owener - read, write, execute
    group - read & execute 
    user - read & execute


## Day 5: SElinux Installation and Configuration
SELinux (Security-Enhanced Linux) is a security layer in Linux that controls who can access what, even if normal permissions allow it.
### Solution 
    sestatus - to check status of SElinux
    sudo dnf install -y selinux-policy selinux-policy-targeted policycoreutils - This will install SElinux packages
    sudo vi /etc/selinux/config  - to change configuration
    Here task is to disable SElinux eveen after reboot, so we have changed in /etc/selinux/config file SELINUX=enforcing  to SELINUX=disabled
  Here We have used dnf insted of yum, but dnf is (Dandified YUM) Modern replacement of yum. Used in: RHEL 8+, CentOS 8 / StreamRocky / AlmaLinux
  yum (Yellowdog Updater Modified) Older package manager. Used in: CentOS 7, RHEL 7

    
