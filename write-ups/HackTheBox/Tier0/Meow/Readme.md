<h1> Meow Lab </h1>

<img width="592" height="241" alt="image" src="https://github.com/user-attachments/assets/0b8f01a7-0428-4c79-a660-d5708c8d5b9d" />


Date 23/1/2026 | Difficulty: Very Easy

1. Target Ip (Discovery)

IP: 10.129.x.x

Nmap Command: nmap -sC -sV [IP]

Open Ports: Port 23 Telnet

2. Vulnerability
Login with root username and NO Password

Why does it work: Wrong configuration of the server

3. Exploitation

Tool : telnet "target IP"  


4.  (Flag)

User/Root Flag: **************************

5. REFLECTION
On the particular machine only port 23 is open thus we would not be able to acquire the flag otherwise.
Only by attacking another machine on the same network which has access to the particular machine.


7. REMEDITION

Deactivate Telnet: Telnet is insecure beacuse it sends usernames and passwords as plain text
Use Secure Password: Never allow root login without password
Root Login Restriction: Do not permit root login through net.

