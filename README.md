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

1️⃣ Install Active Directory Domain Services
	•	Installed AD DS role on DC-1 using Server Manager.

📸 ![image](https://github.com/user-attachments/assets/adcd2307-fa42-4686-abc6-9a4335fa94b2)


2️⃣ Promote to DC
	•	Promoted the server as a new forest: mydomain.com
	•	Restarted and re-logged in using: mydomain.com\labuser

📸 ![image](https://github.com/user-attachments/assets/d62f199e-9b55-40ed-8adf-ce0f07213530)

📸 ![image](https://github.com/user-attachments/assets/83aa598c-0126-4ff7-956a-be9b847e4868)

⸻

👥 Phase 2: Create Domain Admin User & OUs

3️⃣ Create Organizational Units
	•	Created _EMPLOYEES and _ADMINS OUs using ADUC.

📸 ![image](https://github.com/user-attachments/assets/ea53fce7-38fb-40e0-8838-ddee5fbc77d7)


4️⃣ Create Domain Admin: jane_admin
	•	User: Jane Doe
	•	Username: jane_admin
	•	Password: Cyberlab123!
	•	Added to Domain Admins group

📸 15_create_user_jane_admin.png

5️⃣ Log in as jane_admin
	•	Used account mydomain.com\jane_admin going forward.

📸 16_logged_in_as_jane_admin.png

⸻

🔗 Phase 3: Join Client to Domain

6️⃣ Join Client-1 to mydomain.com
	•	Logged in as local admin labuser
	•	Joined domain through system settings
	•	Restarted when prompted

📸 17_join_client_to_domain.png
📸 18_client1_restarting_joining_domain.png

7️⃣ Move to OU _CLIENTS
	•	On DC-1, verified the computer appeared in ADUC
	•	Created _CLIENTS OU and moved Client-1 into it

📸 19_client1_in_ad_and_moved.png

⸻

🛜 Phase 4: Configure RDP for Domain Users

8️⃣ Enable Remote Desktop Access
	•	On Client-1, added Domain Users to Remote Desktop settings
	•	Allows non-admin logins over RDP

📸 20_rdp_access_for_domain_users.png

⸻

🚀 Phase 5: Bulk Create Users with PowerShell

9️⃣ Create Users in _EMPLOYEES OU
	•	Logged into DC-1 as jane_admin
	•	Ran PowerShell script in ISE to create test users:
	•	Names: Chris, Alex, Sam, Taylor, etc.
	•	Password: Cyberlab123!

📸 21_bulk_user_script_created.png
📸 22_bulk_user_script_run_success.png

⸻

👤 Phase 6: Test Login with New User

🔁 Log into Client-1 as Domain User
	•	Example: mydomain.com\alex
	•	Password: Cyberlab123!
	•	Confirmed successful domain login for standard users

📸 23_logged_in_as_new_user.png
