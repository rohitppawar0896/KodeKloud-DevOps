## Day 2: Temporary User Setup with Expiry
  Created user with account expiry date
  ###  Solution
      sudo useradd -m -e 2026-04-01 username
      -m - Create home directory 
      -e yyyy-mm-dd - set account expiry date
      After this date account is not deleted, just disabled

      sudo chage -E -1 username  -> To remove expiry
      sudo chage -E 2026-04-01 username  -> To set expiry to existing account