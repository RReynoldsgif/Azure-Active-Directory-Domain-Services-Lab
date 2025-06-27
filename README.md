# Azure AD Domain Services Lab – Promote DC, Create OUs & Admins

Advanced Domain Setup, User Management, and Remote Access

This lab builds on the initial setup of a Windows Server Domain Controller (DC-1) and Windows 10 Client (Client-1) in Microsoft Azure. In this phase, we:
	•	Promote the server to a Domain Controller
	•	Configure domain structure with OUs and user roles
	•	Join a Windows client to the domain
	•	Create multiple users via PowerShell
	•	Enable Remote Desktop access for domain users
--

🔧 Phase 1: Promote to Domain Controller

# 1️⃣ Install Active Directory Domain Services
	•	Installed AD DS role on DC-1 using Server Manager.

📸 ![image](https://github.com/user-attachments/assets/adcd2307-fa42-4686-abc6-9a4335fa94b2)


# 2️⃣ Promote to DC
	•	Promoted the server as a new forest: mydomain.com
	•	Restarted and re-logged in using: mydomain.com\labuser

📸 ![image](https://github.com/user-attachments/assets/d62f199e-9b55-40ed-8adf-ce0f07213530)

📸 ![image](https://github.com/user-attachments/assets/83aa598c-0126-4ff7-956a-be9b847e4868)

⸻

👥 Phase 2: Create Domain Admin User & OUs

# 3️⃣ Create Organizational Units
	•	Created _EMPLOYEES and _ADMINS OUs using ADUC.

📸 ![image](https://github.com/user-attachments/assets/ea53fce7-38fb-40e0-8838-ddee5fbc77d7)

![image](https://github.com/user-attachments/assets/254eda5d-6353-4e32-81d8-78576ee111b5)


# 4️⃣ Create Domain Admin: jane_admin
	•	User: Jane Doe
	•	Username: jane_admin
	•	Password: Cyberlab123!
	•	Added to Domain Admins group

📸 ![image](https://github.com/user-attachments/assets/901db730-255d-48d7-b46a-ebd778496296)

📸 ![image](https://github.com/user-attachments/assets/7b76959d-5cd7-494c-a577-8958c6ccc38a)


# 5️⃣ Log in as jane_admin
	•	Used account mydomain.com\jane_admin going forward.


⸻

🔗 Phase 3: Join Client to Domain

# 6️⃣ Join Client-1 to mydomain.com
	•	Logged in as local admin labuser
	•	Joined domain through system settings
	•	Restarted when prompted

📸 ![image](https://github.com/user-attachments/assets/2cfa13f2-284f-4d6c-8284-c16f2b604c63)

# 7️⃣ Move to OU _CLIENTS
	•	On DC-1, verified the computer appeared in ADUC
	•	Created _CLIENTS OU and moved Client-1 into it

📸 ![image](https://github.com/user-attachments/assets/96402a76-6969-4f2d-a192-ccdddb695934)


⸻

🛜 Phase 4: Configure RDP for Domain Users

# 8️⃣ Enable Remote Desktop Access
	•	On Client-1, added Domain Users to Remote Desktop settings
	•	Allows non-admin logins over RDP

📸 ![image](https://github.com/user-attachments/assets/b026662f-b44d-4258-a1a2-271e096722f6)


⸻

🚀 Phase 5: Bulk Create Users with PowerShell

# 9️⃣ Create Users in _EMPLOYEES OU
	•	Logged into DC-1 as jane_admin
	•	Ran PowerShell script in ISE to create test users:
	•	Names: Chris, Alex, Sam, Taylor, etc.
	•	Password: Cyberlab123!

📸 ![image](https://github.com/user-attachments/assets/8a290591-1f28-4ea1-8dcf-53a5dec475c2)
📸 ![image](https://github.com/user-attachments/assets/080a2ed3-8c40-4d65-822b-aacf415d3c7d)


⸻

👤 Phase 6: Test Login with New User

🔁 Log into Client-1 as Domain User
	•	Example: mydomain.com\alex
	•	Password: Cyberlab123!
	•	Confirmed successful domain login for standard users

📸 ![image](https://github.com/user-attachments/assets/56394060-1f9a-4e30-9329-5fc1f632601a)
📸 ![image](https://github.com/user-attachments/assets/22a3e589-20a2-495b-b73c-ab2843862ec9)


