Steps to Set up Virtual Machine

  1. Go to https://www.virtualbox.org/wiki/Downloads. Clicked "Windows hosts" to begin download.

     <img src="/assets/screenshots/Download_VirtualBox_1.png" alt="Screenshot" style="cursor: default; pointer-events: none;">
  
  2. Install VirtualBox. Follow the prompts.

     <img src="/assets/screenshots/Begin_Install_2.png" alt="Screenshot" style="cursor: default; pointer-events: none;">
     
  3. Go to https://www.microsoft.com/en-us/evalcenter/download-windows-server-2022. Download "64-bit Edition" ISO.

     <img src="/assets/screenshots/Download_WIN_Server_2022_3.png" alt="Screenshot" style="cursor: default; pointer-events: none;">  

  4. In VirtualBox, create a Windows Server.

     <img src="/assets/screenshots/Create_WIN_Server_4.png" alt="Screenshot" style="cursor: default; pointer-events: none;">

  5. Configure the server by adding roles and features.

     <img src="/assets/screenshots/Configure_Server_5.png" alt="Screenshot" style="cursor: default; pointer-events: none;">

  6. Install Active Directory. Afterwards, this is where the system asked if I wanted to make my server a Domain Controller. I did, so I set my static IP address and named it "DC-01". This would allow me to connect my Client VM's to the DC.

     <img src="/assets/screenshots/Install_AD_6.png" alt="Screenshot" style="cursor: default; pointer-events: none;">
    
  7. System will restart and now is officially a DC!

     <img src="/assets/screenshots/Domain_Controller_7.png" alt="Screenshot" style="cursor: default; pointer-events: none;">

  8. Log in with Admin credentials and search Active Directory to confirm the installation worked.

     <img src="/assets/screenshots/Verify_AD_Install_8.png" alt="Screenshot" style="cursor: default; pointer-events: none;">

  9. Now let's create an Organizational Unit and a new User.

      <img src="/assets/screenshots/Create_OU_User_9.png" alt="Screenshot" style="cursor: default; pointer-events: none;">

  10. To get new User "John H Smith"'s account set up I need to set him up with a temporary password. Once he logs in, he'll set up his own password.

      <img src="/assets/screenshots/Set_Temp_Pass_10.png" alt="Screenshot" style="cursor: default; pointer-events: none;">

  11. And even as an Admin I failed to follow the requirements regarding password creation. Whoops!

      <img src="/assets/screenshots/New_Pass_Fail_11.png" alt="Screenshot" style="cursor: default; pointer-events: none;">

  12. This was a great opportunity to go into the Group Policy Editor and see what the password requirements are.

      <img src="/assets/screenshots/Lookup_Pass_Policy_12.png" alt="Screenshot" style="cursor: default; pointer-events: none;">

  13. Here are the password requirements for users. This is nice to know in case I want to adjust these in the future to make my homelab company more secure.

      <img src="/assets/screenshots/Pass_Policy_13.png" alt="Screenshot" style="cursor: default; pointer-events: none;">

  14. Now that my DC is set up, I went to https://www.microsoft.com/en-us/software-download/windows11 to download Windows 11 for my Client VM.

      <img src="/assets/screenshots/Download_WINOS_14.png" alt="Screenshot" style="cursor: default; pointer-events: none;">

  15. Now, back in VirtualBox, I set up my Client VM with Windows 11 OS.

      <img src="/assets/screenshots/Create_Clinet_VM_15.png" alt="Screenshot" style="cursor: default; pointer-events: none;">

  16. This is another speed bump I ran into. After a couple hours of trying to connect my Client's VM to the DC, troubleshooting, researching why it wasn't working, I realized that I had mistakenly created my Client's VM with Windows 11 HOME OS. To my frustration, The HOME version doesn't support being connected with Active Directory.

      <img src="/assets/screenshots/Incorrect_OS_Install_16.png" alt="Screenshot" style="cursor: default; pointer-events: none;">

  17. Lesson learned. I had to recreate my Client VM with the Windows 11 PRO OS. (The PRO, ENTERPRISE, and EDUCATION versions are compatible with Active Directory)
  18. Now that my Client VM was properly set up. It was time to link it to the static IP address of my DC to ensure they were in the same network.

      <img src="/assets/screenshots/Link_VM_DC_18.png" alt="Screenshot" style="cursor: default; pointer-events: none;">
      

    
