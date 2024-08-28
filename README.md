# Brute Force (Through FTP)

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
   - The scan reveals that the FTP port is open and an "Anonymous" login is allowed, so no password is necessary to enter the FTP server 
3. Connect to the port by inputting the **ftp** command and the target's IP address
4. Use the login name **anonymous** and clicking enter when prompted for a password to sucessfully login to the FTP server
  
   ![image](https://github.com/user-attachments/assets/44f38f50-40b0-4d6a-b2e2-23e913c62a2b)
5. Enter the **ls** command to get a list of all the files on the system and note the file titled *PUBLIC_NOTICE.txt*
6. Input **get PUBLIC_NOTICE.txt** to download the file then type **exit** to exit the FTP server
   
   ![image](https://github.com/user-attachments/assets/c12d6b46-6d25-4814-9fee-7a2209fa7503)
8. Now type **cat secret.txt** to see the contents of the file which appears to have a password that was unintentionally copied to the FTP server
9. Check to see if the contents could be the password to the root account by typing **ssh root@10.10.177.161** and inputting the password that was found earlier

   ![image](https://github.com/user-attachments/assets/00232fee-d5aa-4ad3-b0c0-1b3f28630992)
10. The password was indeed for the root account and have successfully gained access to the target's Linux system


[Lab was provided through **TryHackMe**]
