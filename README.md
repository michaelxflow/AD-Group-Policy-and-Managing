<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Group Policies and Managing Accounts!</h1>
This tutorial goes along wth my previous Lab https://github.com/michaelxflow/Active-Directory-Config In this tutorial we will be using the same lab with our two Virtual Machines we created to Assign roles to our users. We will aslo be simulating Lockouts of their Accounts and how to unlock them. Disable and Enable some Accounts, and Absurving Logins of our Employees!<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- Group Policy and Domain Controller

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>Highlights</h2>

- Configure Account Lockout Threshold in Group Policy
- Attempt to log in to Clients computer with a wrong password 10 times
- Unlock the Account in Active Directory and Reset Password for Client
- Disabling and Enabling Accounts in Active Directory
- Abserve logs in the Domain Controller of the User

<h2>Dealing with Account Lockouts</h2>

<p>

Log into "DC-1" so we can Configure our Clients Account Lockout threshold!
<p>
<img src="https://github.com/user-attachments/assets/a43e17e1-fb05-4570-8fe4-2249828fec9c" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go into "Active Directory and Comptuters" and locate your user you had before, or chose a different one if you'd like!
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/62057726-b2e6-4923-b28e-1558646efa09" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Right click the Windows Start button, click "Run" and type "gpmc.msc" for Group Policy!
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/3340fc3f-4006-4726-a1d9-5cc1a662e6b9" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Locate "Default Domain Policy" to configure the lockout threshold.
</p>
<br />


<p>
<img src="https://github.com/user-attachments/assets/17de3f1c-c83d-4566-a43f-e7e0e3333f3b" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click on it and drop down "Computer Configurations"> then "Policies" > "Windows Settings" > "Security Settings" > "Account Policies" > and "Account Lockout Policy".
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/ddb9a723-a3de-4d10-a5c4-cde34c253511" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click "Account Lockout Duration" to define the time limit the account is locked out for. I chose "30 min" for the duration.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/db987140-dcc6-4255-8e90-09e738f8b4a1" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now go to "Account lockout Threshold" to set the limit for how many attempts the incorrect login can be made. I chose "5" for the invalid attempts limit.
</p>
<br />


<p>
<img src="https://github.com/user-attachments/assets/ba45aa1a-c4f0-4f9f-9cc5-c49cf9be894b" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now lets try to login to "client-1" as your user "cob.tic" and attempt to login incorrectly 5 times.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/d3de27ec-bbdc-4bbc-b32a-5750df39ee27" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
An error screen will then pop up that the account is now locked out! We will then need to unlock the users account. You will be doing this proccess alot as an IT helpdesk Professional.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/001d2a2e-69cb-4fdd-905f-6975d4527ec2" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go back to uyour Domain controller on DC-1 and locate the user in the Active Directory page. Right click the user, go to "Properties" and under "Account" Check the "Box" to unlock the users account!
</p>
<br />


<p>
<img src="https://github.com/user-attachments/assets/11017d76-b8b1-4eb5-91c4-3f0fd9e54660" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now lets go back and try to login to the users account again with the correct password "Password1" and it works! The users account is now unlocked and able to get logged in.
</p>
<br />

<h2>Reset the Users Password</h2>


<p>
<img src="https://github.com/user-attachments/assets/eb4ac733-95e7-4ef3-af2b-7739802e7c9f" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Locate the users account in Active Directory, right click the user and select "Reset passwrord".
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/a2d8c50e-f8e2-418c-8a65-7cc582fccf61" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
You can reset the password to a new one, i picked "Password2" just to make it easy for this lab.
</p>
<br />


<h2>Enabling and Disabling Accounts</h2>


<p>
<img src="https://github.com/user-attachments/assets/973a4e04-b99a-4407-8d0a-6c0bc7c721c9" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
This is an easy and straight forward proccess. Locate the user again in Active Directory , right click thhe user and "Disable Account" 

This will most likely happen in a real life situation, like an employee has been terminatated and no longer works for the company. 
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/401ca847-c7ed-4e6b-811b-c337d0e8c971" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
You can then try to log into the clients computer and see a pop up that the account is disabled and needs to contact your system administrator.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/b85a6b9f-8b76-4aba-ae35-cc186c3c67bc" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To "Enable" the account go back to Active Directory and uder the user , select "Enable Account". In a real life situation make sure the reason for why the account is locked before enabling the users account for security reasons.
</p>
<br />



<h2>Observing Logs</h2>


<p>
<img src="https://github.com/user-attachments/assets/5a6530e5-406d-4fb2-a78e-390dff13e98b" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go to the Windows startbutton again under "Run". Type "eventvwr.msc" This will bring up the event viewer page so we can observe all logs of our users. 
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/dc248216-45eb-44e8-a47d-16ef24daff33" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Drop down "Windows logs" and go to "Security". Search up your user in the search bar and review all the logs that have been recorded.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/12750fca-2291-42b9-a7c6-ed0f260a672c" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
You can observe when and what time the user has logged in, to where the user has failed logn attempts. You can also see the "Event ID" for what code means for a "Failed login" attempt.
<p>

<h2>End of Lab!</h2>

<p> 
</p>
Congrats! You now know how to implement Group Policy in Active Directory for Administration! This will come in handy to know for real life cenarios, so practice this lab till it sticks!
</p>
<p>

</p>
<br />



