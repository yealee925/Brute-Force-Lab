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
1. Start the terminal and use the **nmap** tool with the target's IP address to begin reconnaissance
   
   ![image](https://github.com/user-attachments/assets/55e59d16-bc5f-40c5-96dc-cfe9ab85eca7)
- The open ports in the target's system are: FTP (insecure), SSH (secure), HTTP (insecure)
2. Focusing on the open FTP port, connect to the port by inputting the **ftp** command
3. Log in by using the login **anonymous** (the FTP server in this scenario support anonymous logins)

  ![image](https://github.com/user-attachments/assets/dc3df797-011e-47e2-ad47-fef4737fddb9)
4. Enter the **ls** command to get a list of all the files on the system
5. Download the secret.txt file using the **get** command then input **exit** to exit the FTP server
