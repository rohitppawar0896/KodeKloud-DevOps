## Day 5: SElinux Installation and Configuration
SELinux (Security-Enhanced Linux) is a security layer in Linux that controls who can access what, even if normal permissions allow it.
### Solution 
    sestatus - to check status of SElinux
    sudo dnf install -y selinux-policy selinux-policy-targeted policycoreutils - This will install SElinux packages
    sudo vi /etc/selinux/config  - to change configuration
    Here task is to disable SElinux eveen after reboot, so we have changed in /etc/selinux/config file SELINUX=enforcing  to SELINUX=disabled
  Here We have used dnf insted of yum, but dnf is (Dandified YUM) Modern replacement of yum. Used in: RHEL 8+, CentOS 8 / StreamRocky / AlmaLinux
  yum (Yellowdog Updater Modified) Older package manager. Used in: CentOS 7, RHEL 7
