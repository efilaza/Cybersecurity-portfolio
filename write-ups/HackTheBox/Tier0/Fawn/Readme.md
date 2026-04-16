This Machine explores vulnerabilities on FTP Protocol Port 21

<img width="615" height="242" alt="image" src="https://github.com/user-attachments/assets/e514e779-e9b9-4316-9832-213bc3d9a9a5" />

Date 24/1/2026 | Difficulty: Very Easy

1. Target Ip (Discovery)

IP: 10.129.35.203

Nmap Command: nmap -sC -sV [IP]

Open Ports: Port 21 FTP 

2. Vulnerability
Login with username : anonymous,password: 1234

Why does it work: Wrong configuration of the server

3. Exploitation

Tool : ftp " targetIp" 


4.  (Flag)

User/Root Flag: **************************

5. REFLECTION
On the particular machine only port 21 is open thus we would not be able to acquire the flag otherwise.
Only by attacking another machine on the same network which has access to the particular machine.


7. REMEDITION

Deactivate anonymous Login
Use Secure Password
Restrict Access(Chroot):Configuration so as the user is not able to access the whole file system, but only his directory.
Use SFTP.

