Step 1: Spawn The Target Machine to acquire the target's IP

<img width="644" height="201" alt="image" src="https://github.com/user-attachments/assets/4f28b1a3-e704-4355-a606-b41597ce5c8e" />

Step2 :Ping the target machine > ping 10.129.27.11

<img width="1167" height="364" alt="image" src="https://github.com/user-attachments/assets/c16a55be-437e-47f9-8f5e-de4418066606" />

Step 3: Enumerate for open ports > nmap -sV 10.129.27.11

<img width="1227" height="499" alt="image" src="https://github.com/user-attachments/assets/14244b12-7382-45f8-b8d8-f5c43366d9df" />

Port 21 is OPEN!!!

Step 4: Connect with the ftp port > ftp 10.129.27.11
Use anonymous credentials:
username: anonymous
password: 1234
<img width="830" height="410" alt="image" src="https://github.com/user-attachments/assets/1c0e64fa-40f2-4c6d-a33d-ddce9f7519ef" />

Step 5: use help to search for the available commands > help
<img width="1175" height="925" alt="image" src="https://github.com/user-attachments/assets/28f60171-ec8f-47e0-afa9-08726822dfb0" />

Step 6: Use ls command to find the directories contents > ls
<img width="988" height="234" alt="image" src="https://github.com/user-attachments/assets/403c6399-306a-4a50-b95a-05dbc6d6205b" />

<h3>There is a flag.txt file!!!!</h3>

Step 7 : Get the flag.txt file from the server > get flag.txt
<img width="2542" height="316" alt="image" src="https://github.com/user-attachments/assets/51408657-0dc5-40a7-81b1-82e5b9ca9f89" />

Step 8: Exit from ftp console > bye

Step 8: See the contents of flag.txt file to acquire the Flag!!! > cat flag.txt





