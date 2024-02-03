# Managing-Users-On-Linux
<p align="center">
<img src="https://github.com/bryuan47/Managing-Users-On-Linux/assets/76184628/eef4ea4b-7492-4ee6-9925-e11f9854c74c"
/>
</p>

<h1>Managing Users on Linux with the Linux Ubuntu Command Line</h1>
</br>In this tutorial, we go through the basics of managing users on a system such as creating new users and resetting passwords! <br />



<h2>Environments and Technologies Used</h2>

- Various Command-Line Tools

<h2>Operating Systems Used </h2>

- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Analyzing current users on a system
- Creating Users
- Deleting Users
- Creating Passwords for Users
- Observe Users Password Details
- Creating Password Expiration for Users
- Creating Expiration Date for User accounts
- Lab Cleanup!

<h2>Actions and Observations</h2>


<p>
<img src="https://github.com/bryuan47/Managing-Users-On-Linux/assets/76184628/9a82855b-368e-4bb9-b7ed-c867b4b870b5"/>
</p>
<p>
1) Firt step is to analyze the amount of users we have on our current system with the "cat /etc/passwd command" in the command line. To get a an eact count of how many users there are in the system you can do the "cat /etc/passwd | wc -l" command and it will return the number of user lines displayed. 
</p>
<br />

<p>
<img src="https://github.com/bryuan47/Managing-Users-On-Linux/assets/76184628/d364ea97-ebb5-4d37-bbe7-7e028f346ef1"/>
</p>
<p>
2) To crate new users on a system simlpy use the "sudo useradd -m (username)" Adding the -m attribute also creats a home directory for the profile, which is neccasary for new users.Otherwise you ca just use the "sudo useradd (username)" command. Also be sure to add sudo to gain root privleges to do so, otherwise it will not work!
</p>
<br />

<img src="https://github.com/bryuan47/Managing-Users-On-Linux/assets/76184628/5367ade7-cf16-4b23-91b3-b6c745854a04"/>

<p>
3) Now lets find the user you just created! To find the user Mike2423 and see some password details type the "sudo cat /etc/passwd | grep Mike2423". This will retun the user you just created from that huge list we generated in Step 1.  
</p>

<img src="https://github.com/bryuan47/Managing-Users-On-Linux/assets/76184628/71aec559-5de2-409c-9968-bd92ad53819e"/>

<p> 
4) To delete users lets use the "sudo userdel Mike2423".When you delete users unless you add the -r attribute the home direcory will remian while the user is deleted.  
</p>

<img src="https://github.com/bryuan47/Managing-Users-On-Linux/assets/76184628/52ea2109-c5ea-4024-91c4-322d2e02910d"/>

<p>
5) Great! Now our new user needs a password for security. To create password for the user you created type the "sudo passwd Mike2423" Be sure to make a complex secure password or you will get a "BAD PASSWORD" reply back. Dont forget to put sudo for root privleges! 
</p>

<img src="https://github.com/bryuan47/Managing-Users-On-Linux/assets/76184628/54724312-a6ab-48a7-bfc0-22c5474a9087"/>

<p>
6) To observe details about password such as the last time a password was changed or when does it expire type the "sudo chage -l Mike2423" command". 
</p>

<img src="https://github.com/bryuan47/Managing-Users-On-Linux/assets/76184628/91e2cbc5-3b95-43ce-9aa9-ac629768bd11"/>

<p>
7) Now its time to add a password expiration date for users. You can do this by typing the "sudo chage -M 40 Mike2423". This command will make the password expire in 40 days from the days from the current day.
</p>

<img src ="https://github.com/bryuan47/Managing-Users-On-Linux/assets/76184628/21b1416c-7a6a-4c96-87af-daac21f90ba8"/>

<p> 
8) Lastly, lets create an account expiration for some temporary employees. To do this type the "sudo chage -E 2024-08-01 Mike2423" Make sure to type the sudo command to grant yourself root privleges. This command will make sure the account will be deleted August 1st 2024. 
</p>
<p>
9) Time to clean up! Just simply type clear on the command line to clear the terminal and close the window. 
</p>
<br />
