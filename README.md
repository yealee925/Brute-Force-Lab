# Root Access Lab

## Objective
The Root Access Lab introduces the basics of hacking into a target Linux system (10.10.177.161). The hacking involved active reconnaissance to gather the information necessary to gain access to the user's files.

### Skills Learned
- Used nmap to see what ports were open in the target system
- 

- Advanced understanding of SIEM concepts and practical application.
- Proficiency in analyzing and interpreting network logs.
- Ability to generate and recognize attack signatures and patterns.
- Enhanced knowledge of network protocols and security vulnerabilities.
- Development of critical thinking and problem-solving skills in cybersecurity.

- Security Information and Event Management (SIEM) system for log ingestion and analysis.
- Network analysis tools (such as Wireshark) for capturing and examining network traffic.
- Telemetry generation tools to create realistic network traffic and attack scenarios.

## Steps
1. Start the terminal and use the **nmap** tool with the target's IP address (10.10.177.161) to begin the reconnaissance
   
   ![image](https://github.com/user-attachments/assets/55e59d16-bc5f-40c5-96dc-cfe9ab85eca7)
   - The open ports in the target's system are: FTP (insecure), SSH (secure), HTTP (insecure)
3. Focusing on the open FTP port, connect to the port by inputting the **ftp** command and the IP address
4. Log in by using the login **anonymous** (the FTP server in this scenario supports anonymous logins)
  
   ![image](https://github.com/user-attachments/assets/dc3df797-011e-47e2-ad47-fef4737fddb9)
5. Enter the **ls** command to get a list of all the files on the system and note the file titled *secret.txt*
6. Input **get secret.txt** to download the file then type **exit** to exit the FTP server
   
   ![image](https://github.com/user-attachments/assets/585d971e-8d60-4c44-923c-8685be3e78fb)
8. Now type **cat secret.txt** to see the contents of the file which appears to have a password that was unintentionally copied to the FTP server
9. Check to see if the contents could be the password to the root account by typing **ssh root@10.10.177.161** and inputting the password that was found earlier

   ![image](https://github.com/user-attachments/assets/00232fee-d5aa-4ad3-b0c0-1b3f28630992)
10. The password was indeed for the root account and have successfully gained access to the target's Linux system
