<p align="center">
<img width="302" height="224" alt="Screenshot 2026-03-12 at 8 47 49 PM" src="https://github.com/user-attachments/assets/0c6c7ff6-0196-4d4b-9dc3-29ef1139c955" />
</p>

<h1>Automating Active Directory User Creation with PowerShell</h1>
In this section of the lab, Windows PowerShell ISE was used to automate the creation of large numbers of Active Directory user accounts. Instead of manually creating each user one at a time in Active Directory Users and Computers, a script was used to generate usernames, assign passwords, and place the accounts into the _EMPLOYEES Organizational Unit.<br />


<h2>Environments and Technologies Used</h2>

- Active Directory Users and Computers (ADUC)
- Windows PowerShell
- Active Directory PowerShell Module
- Remote Desktop Protocol (RDP)
  
<h2>Operating Systems Used </h2>

- Windows Server 2022 

<h2>Open and Review the PowerShell User Creation Script</h2>

<p>
![images/LabB5.png](images/LabB5.png)
</p>
<p>
 Step-by-step

1. Open Windows PowerShell ISE as Administrator.
2. Load the user creation script.
3. Review the configuration variables at the top of the script.
4. Confirm the password value and number of accounts to generate.
5. Confirm the script points to the correct Organizational Unit path.


Explanation: 
 This is the preparation stage. It ensures the script is configured correctly before user accounts are created in bulk.

<h2>Configuration Required After Installation</h2>
</p>
<br />

<p>
![images/Lab-B5.png](images/LabB5.png)
</p>
<p>
Step-by-step
  
- Waited for the installation to finish.
- Reviewed the completion message in the wizard.
- Confirmed that the message stated:
- installation succeeded
- additional steps are required
- Located the link:
- Promote this server to a domain controller
- Prepared to begin the post-deployment configuration process.

Explanation:
 Installing the AD DS role does not automatically create a domain. At this point, the role is installed, but the server still needs to be promoted to a Domain Controller before it can manage users, computers, and authentication.


<h2>Start the Domain Controller Promotion Process</h2>
<br />

<p>
<img width="1512" height="982" alt="LabA4" src="https://github.com/user-attachments/assets/94b0c6c2-2acb-4ba0-8751-4800df044dc5" />
</p>
<p>
Step-by-step

- Returned to Server Manager.
- Clicked the notification flag in the upper-right corner.
- Reviewed the post-deployment message for Active Directory Domain Services.
- Clicked Promote this server to a domain controller.
- Waited for the Active Directory Domain Services Configuration Wizard to open.


Explanation:
 This step begins the actual domain setup process. In a real IT environment, this is where the server transitions from being a basic Windows Server installation to becoming a Domain Controller.


<h2>Configure Domain Controller Options</h2>
<br />

<p>
<img width="1536" height="1024" alt="LabA6" src="https://github.com/user-attachments/assets/f5a3b19a-3c59-4c72-b092-452d153f1819" />
<p>
Step-by-step

Continued through the configuration wizard after selecting deployment settings.


- Reached the Domain Controller Options page.
- Set the Forest functional level.
- Set the Domain functional level.
- Left DNS Server checked.
- Left Global Catalog (GC) checked.
- Left Read Only Domain Controller (RODC) unchecked.
- Entered the Directory Services Restore Mode (DSRM) password.
- Confirmed the DSRM password.
- Clicked Next.

Explanation:
   These settings define how the Domain Controller will function in the environment. DNS is required because Active Directory depends heavily on name resolution, and the DSRM password is used for recovery and troubleshooting tasks if Active Directory needs to be restored.


<h2>Run the Prerequisites Check</h2>
<br />

<p>
<img width="1512" height="982" alt="LabA9" src="https://github.com/user-attachments/assets/9b4f8844-971a-4f73-b901-fd3b37461e68" />
</p>
<p>
Step-by-step

1. Continued through the remaining configuration pages.
2. Reached Prerequisites Check.
3. Waited while Windows validated the configuration.
4. Reviewed any warnings or informational notes.
5. Confirmed that the checks passed successfully.
6. Clicked Install to begin the Domain Controller promotion

Explanation:
 This validation step is important because it confirms that the server is properly configured for promotion. In a production environment, this helps prevent configuration problems before Active Directory is installed.

<h2>Domain Controller Promotion Completed</h2>
<br />

<p>
<img width="1512" height="982" alt="LabA21" src="https://github.com/user-attachments/assets/6f947d72-6a9b-426d-a007-65e1d9c532bf" />
</p>
<p>
Step-by-step

1. Waited for the installation and promotion process to complete.
2. Reviewed the final result message.
3. Confirmed that the message stated:
4. This server was successfully configured as a domain controller
5. Reviewed any final notes shown by the wizard.
6. Prepared for the automatic sign-out and restart.
                               

Explanation:
 This step confirms that Active Directory has been successfully deployed. At this point, the server is no longer just a Windows Server VM — it is now a working Domain Controller capable of managing the domain.
