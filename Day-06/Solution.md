## Day 6: Create a Cron Job
Install cronie and start crond service and create task in cron/task */5 * * * * echo hello > /tmp/cron_text
### Solution
    sudo yum install -y cronie ---> Installing cronie
    sudo systemctl start crond ---> startting crind service
    sudo systemctl status crond ---> checking c=status of crond service by default it is enabled so after reboot it will start automatically
    sudo crontab -e ---> This will open an editor so add  entry */5 * * * * echo hello > /tmp/cron_text saveand close by :wq!
    sudo crontab -l  ---> it will dispaly all corns/tasks
  Cronie is a Linux package that provides the cron scheduling system. It is the software that lets Linux run tasks automatically at scheduled times
  crond is the service that Continuously runs and checks schedules
  crontab -e Used to create/edit scheduled jobs. This is the interface
     
      * * * * *  command_to_run
      │ │ │ │ │
      │ │ │ │ └── Day of week (0–7)
      │ │ │ └──── Month (1–12)
      │ │ └────── Day of month (1–31)
      │ └──────── Hour (0–23)
      └────────── Minute (0–59)

      eg.   */5 * * * * echo hello > /tmp/cron_text    
      Every 5 minutes, write ‘hello’ into /tmp/cron_text, replacing its previous content.
    