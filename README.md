<h1>Manage Users with Linux Commands</h1>

<h2>Description</h2>
This repository demonstrates the process of managing user accounts in Linux. It will outline the steps to add the user researcher9 to a designated team, modify the user's group affiliation to another team within the organization, and subsequently delete the user account along with the associated group using Linux commands.

<h2>Languages and Utilities Used</h2>

- <b>Shell Commands</b>

<h2>Environments Used</h2>

- <b>Linux</b>

<h2>Program Walk-through:</h2>

<h3>1. Adding User and Assigning File Ownership</h3>
<p align="center">
<img src="https://i.imgur.com/B9VMhiD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<code>sudo useradd researcher9</code>:  The sudo part ensures that the command is run with superuser (administrative) privileges, which are required for adding new users. This command creates a new user named researcher9. It's important to note that when a new user is created, a primary group with the same name is also created for that user.The newly created user is the only member of this group by default.

<code>sudo usermod -g research_team researcher9</code>: This command modifies the user researcher9 by changing their primary group(researcher9) to research_team. The -g option specifies the new group, and the user researcher9 is now a member of the research_team group.
<br/>
<p align="center">
<img src="https://i.imgur.com/OR23dud.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<code>sudo chown researcher9 project_r.txt</code>: This command uses chown which stands for change owner. It changes the ownership of the file <code>project_r.txt</code>, making the user researcher9 the new owner of that file.
<br/>
<br/>

**Cybersecurity Application:** Managing users and groups through these commands helps ensure that system access is tightly controlled, minimizing vulnerabilities and supporting secure, structured user management in Linux systems.
 
<h3>2. Adding User to a Secondary Group</h3>
<p align="center">
<img src="https://i.imgur.com/DoAuKZ7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<code>sudo usermod -a -G sales_team researcher9</code>: In this command we introduce -a and -G. -a stands for append. It ensures that the user is added to the specified group without removing them from any existing groups. Without the -a flag, the user would be removed from all other groups and only added to the specified group. -G specifies the group you want to add the user to. In this case, it’s the sales_team group. Multiple groups can be added at once by separating them with commas.
<br/>
<br/>

**Cybersecurity Application:** By adding researcher9 to multiple groups, I manage their access to different resources and directories that are shared among those groups. Each group may have different permissions, such as read, write, or execute, allowing me to control the user's access to sensitive data or applications.

<h3>3. Deleting a User</h3>
<p align="center">
<img src="https://i.imgur.com/5tYn57E.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<code>sudo userdel researcher9</code>: This command will delete the user researcher9. If researcher9 is the only user in the group named researcher9 (and it is also the user's primary group), then executing the command would indeed delete both the user and the associated group. However, the group with the same name was not deleted because the primary group of researcher9 was changed earlier to research_team. When deleting a user, it is good practice to also delete the empty group that is no longer in use.
<br/>
<code>sudo groupdel researcher9</code>: This command will delete the empty group researcher9 that was created by default when the user researcher9 was created.
<br/>
<br/>

**Cybersecurity Application:** Regularly managing user accounts, including their deletion when no longer needed, is a proactive approach to maintaining a secure environment.






<h2>Conclusion</h2>
Managing user accounts through adding, modifying, and deleting users is a fundamental practice in cybersecurity that directly impacts an organization's security posture. These actions contribute to maintaining a secure and compliant environment, safeguarding sensitive data from potential threats and ensuring that only authorized personnel have access to critical resources. Regularly auditing and updating user accounts is essential for a proactive cybersecurity strategy.
