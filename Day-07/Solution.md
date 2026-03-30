## Day 7: Linux SSH Authentication
make these scripts work properly we need to make sure the thor user on jump host has password-less SSH access to all app servers through their respective sudo users (i.e tony for app server 1)

### Solution
    mkdir -p /home/thor/.ssh - create .ssh directory in thor home directory
    chmod 700 /home/thor/.ssh - assign read write and execute  permission to only owner

    ssh-keygen -t rsa -b 2048 -f /home/thor/.ssh/id_rsa --> it will create private and public key in .ssh folder

    ssh-copy-id tony@stapp01 --> it will copy public key from /home/thor/.ssh  on app server stapp02 at /home/tony/.ssh/authorized_keys

    Now tony can access stapp01 without password
    
