Step 1 : Connect to PwnBox 
Step 2: Spawn the trarget Machine to acquire its IP Address
Target IP: 10.129.25.177

Step 3: Ping the target Machine <img width="1224" height="433" alt="image" src="https://github.com/user-attachments/assets/ffb78286-1fc6-4261-a9c2-0fb07a4babc3" />


Step 4: nmap -sV 10.129.25.177
<img width="1206" height="501" alt="image" src="https://github.com/user-attachments/assets/fa3f35b1-59ba-4200-bcec-179f4e23d251" />


<h3>Open telnet port 23/tcp telnet</h3>

Step 5 : telnet 10.129.25.177
<img width="1193" height="475" alt="image" src="https://github.com/user-attachments/assets/eb1600b3-79e7-407d-b1bb-185f23d76eec" />


Trying usual usernames with no password:
admin
administrator
root
<img width="1224" height="394" alt="image" src="https://github.com/user-attachments/assets/863e698c-0759-48ca-a227-682e767d8351" />

**Username  "root" does the job!**

<img width="1116" height="389" alt="image" src="https://github.com/user-attachments/assets/2a64a289-172a-43e0-8820-e5484431cda8" />


Step 6 : ls

<img width="341" height="90" alt="image" src="https://github.com/user-attachments/assets/f6af9fce-f88f-462b-8e09-76354b7aeef5" />


Step 7: cat flag.txt



