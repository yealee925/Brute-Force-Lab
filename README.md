# Brute Force (FTP Server)

## Objective
The Brute Force Lab demonstrated the steps hackers may use to hack into an account through active reconnaissance and take advantage of insecure practices. The lab's goal was to gain a deeper understanding of both hacking tactics and the ability to examine whether insecure practices are being used in one's system.

### Skills Learned
- Advanced knowledge of working with a Linux system and practiced inputting Linux commands
- Enhanced understanding of hacking techniques
- Development of critical thinking and problem-solving skills in cybersecurity.

### Tools Used
-  Hydra, a brute force tool used to crack passwords 

## Steps
1. Begin the terminal and scan the top 1000 ports on the target's IP address (10.10.59.245) using the **nmap** command
   
   ![image](https://github.com/user-attachments/assets/5f7c6e90-0639-4ed8-b1e1-8ba9d2b4f67b)
   - The scan reveals the FTP port is open and an "Anonymous" login is allowed, so no password is necessary to enter the FTP server 
3. Connect to the port by inputting the **ftp** command and the target's IP address
4. Use the login name *anonymous* and clicking enter when prompted for a password to sucessfully login to the FTP server
  
   ![image](https://github.com/user-attachments/assets/44f38f50-40b0-4d6a-b2e2-23e913c62a2b)
5. Enter the **ls** command to get a list of all the files on the system and note the file titled *PUBLIC_NOTICE.txt*
6. Input **get PUBLIC_NOTICE.txt** to download the file then type **exit** to exit the FTP server
   
   ![image](https://github.com/user-attachments/assets/84ed20a4-8699-443f-a7af-33fa93bd7ac3)
8. Now type **cat PUBLIC_NOTICE.txt** to see the contents of the file which appears to have a potential username to an account (mike)

   ![image](https://github.com/user-attachments/assets/2ebf88f9-86da-44e0-9231-2b8b311a684c)
9. Ensure Hydra is installed on the system, which will be used to crack the password. Insert **hydra -t 4 -l mike -P /usr/share/wordlists/rockyou.txt -vV 10.10.59.245 ftp** into the terminal

   ![image](https://github.com/user-attachments/assets/e6a0d535-0aed-4cd1-bb6b-784bbd61878a)
   - The password was discovered after five attempts as *password*
11. Enter the FTP server through **ftp 10.10.59.245**. Login using the username and password that were identified earlier to successfully gain access
   
    ![image](https://github.com/user-attachments/assets/70955229-bfd6-4fb8-9240-478ef4ee92f1)



Lab was provided through **TryHackMe**
