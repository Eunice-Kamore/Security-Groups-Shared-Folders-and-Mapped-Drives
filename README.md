<h1>Overview: Lab 7 Creating File Shares,Permissions and Mapping Drives</h1>

This section of my home lab documentation focuses on **Shared Files**, **Permissions**, and **Mapping Drives** in a domain environment. The project demonstrates how to create and configure shares on Server Manager, how to configure permissions for specific roles and how to map a network drive for each user.

<h2>Objectives</h2>

- Create 3 (HR, Finance, Sales) departments in form of **Organizational Units** in Active Directory to classify users by their roles, manage access to resources and network drives.
- Set up **Mapped Drives** to enable users to access shared resources across the network automatically.
- Modify Permissions ensuring only the required users have access to the shared folder
- Confirm the functionality of our configuration by logging in to the Windows PC each user at a time and confirm whether they have access or not.

<h2>Documentation</h2>

We shall begin by creating 3 new **Organizational Units** (HR, Finance and Sales) , and 3 new user accounts in each of the OUs (Billy Barnes, Bob Smith and Sarah Jakes) respectively.

1. <p align="center">
   <img src="https://github.com/Eunice-Kamore/Security-Groups-Shared-Folders-and-Mapped-Drives/blob/main/Images/1.png?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps 1"/>
   <br />
   <br />
</p>

2. <p align="center">
   <img src="https://github.com/Eunice-Kamore/Security-Groups-Shared-Folders-and-Mapped-Drives/blob/main/Images/2.png?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps 1"/>
   <br />
   <br />
</p>

3. <p align="center">
   <img src="https://github.com/Eunice-Kamore/Security-Groups-Shared-Folders-and-Mapped-Drives/blob/main/Images/3.png?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps 1"/>
   <br />
   <br />
</p>

We will create one file share and create folders for each department that will be accessed by the user accounts. To create a file share select **File and Storage Services** on the left-hand side, followed by **Shares**. Right-click and select **New Share**.

4. <p align="center">
   <img src="https://github.com/Eunice-Kamore/Security-Groups-Shared-Folders-and-Mapped-Drives/blob/main/Images/6.png?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps 1"/>
   <br />
   <br />
</p>

5. <p align="center">
   <img src="https://github.com/Eunice-Kamore/Security-Groups-Shared-Folders-and-Mapped-Drives/blob/main/Images/7.png?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps 1"/>
   <br />
   <br />
</p>

Choose "SMB Share - Quick", click Next until you reach the Specify Share Name screen. Name the share "shared files", then continue selecting Next until you reach the Create button. Click Create to finish setting up the shared folder.

6. <p align="center">
   <img src="https://github.com/Eunice-Kamore/Security-Groups-Shared-Folders-and-Mapped-Drives/blob/main/Images/8.png?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps 2"/>
   <br />
   <br />
</p>

7. <p align="center">
   <img src="2. <p align="center">
   <img src="https://github.com/Eunice-Kamore/Security-Groups-Shared-Folders-and-Mapped-Drives/blob/main/Images/10.png?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps 2"/>
   <br />
   <br />
</p>

Now that we have our shared folder, to confirm open File Explorer → This PC → Local C Drive → Shares to access the shared folder. Once you have accessed the folder, create 3 folders and name them HR, Finance and Sales. These are the folders that we shall share with the specific members associated to each department folder.

8. <p align="center">
   <img src="https://github.com/Eunice-Kamore/Security-Groups-Shared-Folders-and-Mapped-Drives/blob/main/Images/15.png?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps 4"/>
   <br />
   <br />
</p>


9. <p align="center">
   <img src="https://github.com/Eunice-Kamore/Security-Groups-Shared-Folders-and-Mapped-Drives/blob/main/Images/16.png?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps 4"/>
   <br />
   <br />
</p>


Now we are going to specify access permissions for the folders. Now right click on the "Finance" folder and click on "Properties". 

10.
  <p align="center">
   <img src="https://github.com/Eunice-Kamore/Security-Groups-Shared-Folders-and-Mapped-Drives/blob/main/Images/17.png?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps 5"/>
   <br />
   <br />
   </p>

Navigate to the "Security" tab and click on "Edit" to add "Sarah Jakes" as an authorized account for the "Finance" folder.

11.
    <p align="center">
   <img src="https://github.com/Eunice-Kamore/Security-Groups-Shared-Folders-and-Mapped-Drives/blob/main/Images/18.png?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps 5"/>
   <br />
   <br />
</p>

Type the name "Sarah Jakes" and click on check names. This searches the name from our domain. Once the name is found click "OK"


12. <p align="center">
   <img src="https://github.com/Eunice-Kamore/Security-Groups-Shared-Folders-and-Mapped-Drives/blob/main/Images/19.png?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps 6"/>
   <br />
   <br />
</p>
Now we need to delete the other "Users" user names because we need the folder to be accessed by Sarah Jakes and the Administrator only. To do this click on "Advanced"


12. <p align="center">
   <img src="https://github.com/Eunice-Kamore/Security-Groups-Shared-Folders-and-Mapped-Drives/blob/main/Images/20.png?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps 6"/>
   <br />
   <br />
</p>

To delete the "Users" we need to click on "Disable Inheritance" 


13. <p align="center">
   <img src="https://github.com/Eunice-Kamore/Security-Groups-Shared-Folders-and-Mapped-Drives/blob/main/Images/21.png?raw=true" height="70%" width="70%" alt="Disk Sanitization Steps 7"/>
   <br />
   <br />
</p>

Choose the first option "Convert inherited permissions into explicit permissions on this object". The send option will delete all permissions. After this select the "Users" accounts one at time and click on ""Remove" to delete them.


14. <p align="center">
   <img src="https://github.com/Eunice-Kamore/Security-Groups-Shared-Folders-and-Mapped-Drives/blob/main/Images/22.png?raw=true" height="70%" width="70%" alt="Disk Sanitization Steps 7"/>
   <br />
   <br />
</p>

Now we will explore another way to add Users. Right click on the "HR" folder → Properties → Advanced and arrive to this page. Then click "Add"


15. <p align="center">
   <img src="https://github.com/Eunice-Kamore/Security-Groups-Shared-Folders-and-Mapped-Drives/blob/main/Images/23.png?raw=true" height="60%" width="60%" alt="Disk Sanitization Steps 8"/>
   <br />
   <br />
</p>

Then click "Select a principal" and follow the same process we did with adding "Sarah Jakes" to add "Billy Barnes" 


16. <p align="center">
   <img src="https://github.com/Eunice-Kamore/Security-Groups-Shared-Folders-and-Mapped-Drives/blob/main/Images/24.png?raw=true" height="60%" width="60%" alt="Disk Sanitization Steps 8"/>
   <br />
   <br />
</p>

You can see the principal "Billy Barnes" has been added. Ensure that the "Modify" checkbox is checked and also delete the other "Users" accounts as we did earlier. 
We will complete the same process with the other "Sales" folder and add "Bob Smith"


17. <p align="center">
   <img src="https://github.com/Eunice-Kamore/Security-Groups-Shared-Folders-and-Mapped-Drives/blob/main/Images/25.png?raw=true" height="60%" width="60%" alt="Disk Sanitization Steps 8"/>
   <br />
   <br />
</p>

Now we will login the the "Windows PC" VM and login with Bob Smith's account and try to access the shared folder from the machine. 


18. <p align="center">
   <img src="https://github.com/Eunice-Kamore/Security-Groups-Shared-Folders-and-Mapped-Drives/blob/main/Images/27.png?raw=true" height="60%" width="60%" alt="Disk Sanitization Steps 9"/>
   <br />
   <br />
</p>

Open "File Explorer" → "This PC" and type "\\DC01\sharedfiles" and click "Enter" at the top to access the shared folder.


19. <p align="center">
   <img src="https://github.com/Eunice-Kamore/Security-Groups-Shared-Folders-and-Mapped-Drives/blob/main/Images/28.png?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps 10"/>
   <br />
   <br />
</p>



20. <p align="center">
   <img src="https://github.com/Eunice-Kamore/Security-Groups-Shared-Folders-and-Mapped-Drives/blob/main/Images/36.png?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps 10"/>
   <br />
   <br />
</p>

Now open the "Sales" folder and create a Test word document to make sure Bob has rights to Write as well.


21. <p align="center">
   <img src="https://github.com/Eunice-Kamore/Security-Groups-Shared-Folders-and-Mapped-Drives/blob/main/Images/29.png?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps 10"/>
   <br />
   <br />
</p>

Opening the other folders gives an error because we have Bob permissions for the "Sales" folder.


22. <p align="center">
   <img src="https://github.com/Eunice-Kamore/Security-Groups-Shared-Folders-and-Mapped-Drives/blob/main/Images/30.png?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps 11"/>
   <br />
   <br />
</p>


23. <p align="center">
   <img src="https://github.com/Eunice-Kamore/Security-Groups-Shared-Folders-and-Mapped-Drives/blob/main/Images/31.png?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps 11"/>
   <br />
   <br />
</p>

Now we are going Map the Drive for easy access for the user so that they do not have to type in the network path like we did before. To do this we will highlight and copy the Network Path "\\DC01\sharedfiles\".


24. <p align="center">
   <img src="https://github.com/Eunice-Kamore/Security-Groups-Shared-Folders-and-Mapped-Drives/blob/main/Images/32.png?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps 11"/>
   <br />
   <br />
</p>

Then Right-click on **This PC** in **File Explorer** and select **Map this Network drive**.


25. <p align="center">
   <img src="https://github.com/Eunice-Kamore/Security-Groups-Shared-Folders-and-Mapped-Drives/blob/main/Images/33.png?raw=true" height="60%" width="60%" alt="Disk Sanitization Steps 12"/>
   <br />
   <br />
</p>


In the **Map Network Drive** window, **Drive**, Choose a drive letter, such as **Z:**.
Then on the **Folder**: Paste the network path \\DC01\sharedfiles into the field. Finally click **Finish**.


26. <p align="center">
   <img src="https://github.com/Eunice-Kamore/Security-Groups-Shared-Folders-and-Mapped-Drives/blob/main/Images/34.png?raw=true" height="60%" width="60%" alt="Disk Sanitization Steps 12"/>
   <br />
   <br />
</p>

The network drive has been Mapped successfuly. Every time the user logs in they will find it here. You can repeat the process for the other 2 users.


27. <p align="center">
   <img src="https://github.com/Eunice-Kamore/Security-Groups-Shared-Folders-and-Mapped-Drives/blob/main/Images/35.png?raw=true" height="60%" width="60%" alt="Disk Sanitization Steps 13"/>
   <br />
   <br />
</p>


Congratulations we have successfully created a Shared Folder, configured access permissions and mapped network drives.

 👉 [Next Lab 8 : Group Policy Configuration]



