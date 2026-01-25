# Phase 0 – AWS Account & Cost Security Baseline

## Objective
This phase establishes a secure AWS account baseline before provisioning any resources. 
The focus is on protecting the root account, enforcing multi-factor authentication (MFA), 
and implementing cost controls to prevent unexpected spending.

---

## Steps Performed

### 1️⃣ AWS Account Creation
Created a new AWS account dedicated for security labs to isolate testing from production or personal environments.

📸 Evidence:  
P0-01-aws-account-created.png

---

### 2️⃣ Root Account MFA Enabled
Enabled Multi-Factor Authentication (MFA) on the AWS root account to protect against unauthorized access.

📸 Evidence:  
P0-02-root-mfa-enabled.png

---

### 3️⃣ Budget Alert Configuration
Configured AWS Budget alerts to monitor usage and prevent cost overruns during lab activities.

📸 Evidence:  
P0-03-budget-alert.png

---

## Security Best Practices Applied
- Root account access protected with MFA
- Reduced risk of account takeover
- Cost governance implemented early
- Separation of lab environment from production

---

## Why This Matters
Compromised root credentials or uncontrolled spending are common cloud risks. 
This phase ensures the AWS environment is secure and governed before any infrastructure is deployed.

---

## Next Phase
➡️ Phase 1 – EC2 Provisioning & Secure Access
