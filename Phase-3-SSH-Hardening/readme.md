🔐 Phase 3 – SSH Hardening & Audit Logging (AWS EC2 Ubuntu)
📌 Objective

Harden SSH access on an AWS EC2 Ubuntu instance by enforcing key-based authentication, restricted user access, and privileged activity logging, while providing verifiable audit evidence suitable for security interviews and real-world operations.

🏗 Environment

Cloud Provider: AWS EC2

OS: Ubuntu 24.04 LTS

Instance Type: Free-tier compatible

Region: ap-southeast-2

Access Method: SSH (key-based)

🔒 SSH Hardening Configuration
1️⃣ Root Login Disabled
PermitRootLogin no


✔ Prevents direct root access via SSH

2️⃣ Password Authentication Disabled
PasswordAuthentication no
PubkeyAuthentication yes


✔ Enforces SSH key-based authentication only

3️⃣ Restricted SSH Users
AllowUsers secadmin ubuntu


✔ Only explicitly allowed users can connect
✔ Prevents lateral access attempts

Observed Result:

ubuntu → blocked

root → blocked

secadmin → allowed

🔑 SSH Key Validation
Directory & File Permissions
~/.ssh                 → 700
~/.ssh/authorized_keys → 600


✔ Prevents SSH from rejecting keys due to insecure permissions

🧪 Verification Evidence
✅ Successful Login
ssh -i aws-linux-lab.pem secadmin@<public-ip>


Result:
✔ Login successful via public key

❌ Failed Login Attempts (Expected)
ssh ubuntu@<public-ip>
ssh root@<public-ip>


Result:
✔ Connection rejected
✔ Logged in authentication logs

📜 SSH Authentication Logs
Failed Login Evidence
sudo grep "Failed" /var/log/auth.log


✔ Shows rejected users and IP addresses
✔ Demonstrates brute-force & policy enforcement visibility

🛡 Sudo Command Auditing
Sudo Logging Enabled

Custom sudoers file:

/etc/sudoers.d/logging

Logged Commands
sudo tail -n 20 /var/log/sudo.log


Captured Data Includes:

User

TTY

Working directory

Executed command

Timestamp

✔ Full accountability of privileged actions

📸 Evidence Screenshots
Screenshot	Description
P3-01	SSH configuration hardened
P3-02	SSH service running
P3-03	Hardened SSH verified
P3-04	SSH verbose authentication logging
P3-05	Sudo command audit logging
P3-06	Failed SSH login attempts
🔍 Security Outcomes

✔ Root SSH access eliminated
✔ Password attacks blocked
✔ Least-privilege user enforcement
✔ Full audit trail for sudo commands
✔ SSH brute-force attempts logged and traceable
