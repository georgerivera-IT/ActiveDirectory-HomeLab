# User Account Management

## Objective:
Demonstrating enterprise-level Active Directory user lifecycle management including configuring organizational units, user creation, group management, Group Policy configuration, and account offboarding.

## Environment:
- Hypervisor: VMware Workstation Pro
- Server OS: Windows Server 2022 Standard Evaluation
- Domain Controller: DC01 (corp.local)
- Tools Used: Active Directory Users and Computers, Group Policy Management Console

## Skills Demonstrated:
- Organizational Unit (OU) design
- User account creation
- Security group management
- Group Policy Object (GPO) configuration
- Account offboarding procedure

## Step 1 — Created Organizational Unit Structure
After opening Active Directory Users and Computers (ADUC), find the corp.local Domain and right-click, New, and create an Organizational Unit

<img width="1226" height="874" alt="UAM2" src="https://github.com/user-attachments/assets/7a102da4-06dc-4059-9617-5f9e0f7a2d9f" />

<br>
<br>


<img width="1223" height="876" alt="UAM3" src="https://github.com/user-attachments/assets/0f78be96-fbf0-4735-8e63-1da09398f3f4" />




## Step 2 — Manual User Creation
Created a user account for Jane Doe manually in the HR OU to demonstrate 
understanding of the individual account creation process including 
setting logon names, passwords, and forcing a password change at 
first login.

![Manual User Creation Form](../screenshots/lab2-manual-user-form.png)
![Jane Doe in HR OU](../screenshots/lab2-jane-doe-hr-ou.png)

---

## Step 3 — Bulk User Creation via PowerShell
Created a CSV file containing user data for 5 employees across 
multiple departments, then ran a PowerShell script to automatically 
create all accounts and place them in the correct OUs. This simulates 
how IT teams handle onboarding at scale.

**CSV Structure used:**
\```
FirstName,LastName,Department,JobTitle,Password
John,Smith,IT,Help Desk Technician,Welcome1!
\```

**PowerShell script output:**

![PowerShell Bulk Creation Output](../screenshots/lab2-powershell-output.png)
![Users Populated in OUs](../screenshots/lab2-users-in-ous.png)

---

## Step 4 — Security Group Creation and Membership
Created Security Groups for each department and assigned users to 
their appropriate groups. Security groups control resource access 
across the domain — a user's group membership determines what 
shared drives, printers, and resources they can access.

![Security Groups Created](../screenshots/lab2-security-groups.png)
![Group Members Tab](../screenshots/lab2-group-members.png)

---

## Step 5 — Password Policy GPO
Created and linked a Password Policy GPO to enforce minimum security 
standards across all domain accounts.

| Setting | Value |
|---|---|
| Minimum password length | 10 characters |
| Complexity requirements | Enabled |
| Maximum password age | 90 days |
| Minimum password age | 1 day |
| Password history | 5 passwords |

![Password Policy Settings](../screenshots/lab2-password-policy-gpo.png)

---

## Step 6 — Account Lockout Policy GPO
Created an Account Lockout Policy to protect against brute force 
login attempts by locking accounts after 3 failed attempts.

| Setting | Value |
|---|---|
| Lockout threshold | 3 attempts |
| Lockout duration | 15 minutes |
| Reset counter after | 15 minutes |

![Account Lockout Policy](../screenshots/lab2-lockout-policy-gpo.png)
![GPOs Linked to Domain](../screenshots/lab2-gpos-linked.png)

---

## Step 7 — Account Offboarding Procedure
Performed a complete offboarding workflow on a terminated user account 
using PowerShell. This follows security best practice — disabling rather 
than deleting accounts preserves audit history.

**Offboarding steps performed:**
1. Disabled the account
2. Removed from all security groups
3. Moved to Disabled_Accounts OU
4. Added termination date to account description

![PowerShell Offboarding Output](../screenshots/lab2-offboarding-powershell.png)
![Disabled Account in OU](../screenshots/lab2-disabled-account-ou.png)

---

## Outcome
Successfully demonstrated the full user lifecycle in Active Directory 
from account creation through offboarding. Automated bulk provisioning 
using PowerShell and enforced security standards through Group Policy.

## Lessons Learned
- PowerShell automation dramatically reduces onboarding time and 
  eliminates manual errors at scale
- Disabling accounts instead of deleting them is critical for 
  audit trails and potential account recovery
- Linking GPOs at the domain level applies them universally — 
  department-specific policies should be linked at the OU level instead
