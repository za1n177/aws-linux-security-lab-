🔐 Phase 4 – Host Firewall Hardening (UFW)
Objective

Harden the EC2 Linux host by enabling and configuring UFW (Uncomplicated Firewall) as a second security layer in addition to AWS Security Groups.

This demonstrates defense-in-depth:

AWS Security Group = network perimeter

UFW = host-level firewall

Architecture

Cloud Provider: AWS EC2

OS: Ubuntu 24.04 LTS

Firewall: UFW

Admin User: secadmin (sudo-enabled)

SSH Access: Restricted via AWS SG + UFW

Step 1 – Verify AWS Security Group Restriction

Goal: Ensure SSH is restricted at the cloud layer before enabling host firewall.

SSH (TCP 22) allowed only from trusted IP

No public wide-open access

📸 Screenshot:

P4-01-aws-sg-ssh-restricted.png

✅ Result:
Only My IP (/32) is allowed to access port 22.

Step 2 – Verify UFW Initial State
sudo ufw status


Expected:

Status: inactive


📸 Screenshot:

P4-02-ufw-inactive.png

✅ Result:
Firewall is inactive by default (safe starting state).

Step 3 – Allow SSH Before Enabling Firewall
sudo ufw allow 22/tcp


Why this matters:

Prevents locking yourself out when UFW is enabled

Critical operational best practice

Step 4 – Enable UFW
sudo ufw enable


Confirmation:

Firewall is active and enabled on system startup

Step 5 – Verify Firewall Rules (Verbose)
sudo ufw status verbose


Expected:

Status: active
Default: deny (incoming), allow (outgoing)
22/tcp ALLOW IN Anywhere
22/tcp (v6) ALLOW IN Anywhere (v6)


📸 Screenshot:

P4-03-ufw-enabled.png

Security Controls Implemented
Layer	Control
Cloud	AWS Security Group (SSH restricted to /32)
Host	UFW enabled
Default Policy	Deny all incoming
Allowed Service	SSH (22/tcp)
Persistence	Firewall enabled on boot
