## Day 3: Secure Root SSH Access
  Disabled ssh login of root user
  ### Solution
    sudo vi /etc/ssh/sshd_config
    change entry for PermitRootLogin yes to PermitRootLogin no
    after that restart the sshd service
    sudo systemctl restart sshd