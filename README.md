📁 Phase 2 – User and Access Management (Linux Security)
🎯 Objective

This phase focuses on Linux user management and access control hardening, a critical foundation for securing AWS EC2 Linux instances. The goal is to demonstrate least privilege, secure privilege escalation, and controlled SSH access in a real-world cloud environment.

🧩 Scope of This Phase

In this phase, the following security tasks were performed:

System update and patching

Secure user creation

Controlled privilege escalation using sudo

SSH hardening by restricting direct root access

Validation of secure administrative access

🛠️ Environment

Platform: AWS EC2

OS: Ubuntu Server (Linux)

Access Method: SSH

Security Principle: Least Privilege

🔐 Steps Performed
1️⃣ System Update & Patching

Ensured the system is up to date to reduce exposure to known vulnerabilities.

📸 Evidence:
P2-01-system-update.png

2️⃣ Secure User Creation

Created a non-root administrative user for day-to-day operations instead of using the root account.

📸 Evidence:
P2-02-user-created.png

3️⃣ Sudo Group Assignment

Granted administrative privileges using the sudo group rather than enabling root login.

📸 Evidence:
P2-03-sudo-group.png

4️⃣ SSH Hardening (Disable Root Login)

Modified SSH configuration to prevent direct root SSH access, reducing brute-force and privilege escalation risks.

📸 Evidence:
P2-04-secadmin-ssh.png

5️⃣ Validation of Secure SSH Access

Confirmed successful SSH login using the newly created admin user with sudo privileges.

📸 Evidence:
P2-05-secadmin-ssh-success.png

🔎 Security Best Practices Applied

✅ Least privilege access

✅ No direct root SSH login

✅ Use of sudo for accountability

✅ Secure administrative access

✅ Change validation after hardening

📚 Why This Matters (Real-World Relevance)

These controls directly align with:

Cloud security best practices

SOC and incident response readiness

CIS Linux Benchmarks

AWS security hardening guidelines

Misconfigured user access is one of the top causes of cloud breaches. This phase demonstrates how to prevent that.

📌 Next Phase

➡️ Phase 3 – Logging, Auditing & Monitoring
(Focus: auditd, logs, intrusion detection, and visibility)

👤 Author

Muamad Zaini Bin Rani
Senior IT / Cloud & Security Enthusiast
📍 Singapore
