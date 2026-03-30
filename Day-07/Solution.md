## Day 7: Linux SSH Authentication
make these scripts work properly we need to make sure the thor user on jump host has password-less SSH access to all app servers through their respective sudo users (i.e tony for app server 1)

### Solution
    mkdir -p /home/thor/.ssh - create .ssh directory in thor home directory
    chmod 700 /home/thor/.ssh - assign read write and execute  permission to only owner

    ssh-keygen -t rsa -b 2048 -f /home/thor/.ssh/id_rsa --> it will create private and public key in .ssh folder

    ssh-copy-id tony@stapp01 --> it will copy public key from /home/thor/.ssh  on app server stapp02 at /home/tony/.ssh/authorized_keys

    Now tony can access stapp01 without password

##  Authentication Flow
ssh tony@stapp01

1. Connection established (secure SSH session)
2. Server checks /home/tony/.ssh/authorized_keys
3. Server sends challenge
4. Client signs using private key
5. Server verifies using public key
6. Match → login without password
7. No match → password required

---

## 🧠 Who is Connecting
- thor → client (initiates connection)
- tony → target user on server  
- thor logs in as tony

---

## 🔑 Core Concept
- Private key → client (identity proof)
- Public key → server (verification)
- Access granted if keys match

---

## ⚠️ Common Mistakes
- Using sudo ssh-copy-id (copies wrong key)
- Wrong .ssh ownership
- Incorrect permissions
- Copying key to wrong user

---

## 📌 Summary
Server trusts the public key, and client proves identity using private key → no password needed.

thor connects to the server and logs in as tony if his key is trusted.

