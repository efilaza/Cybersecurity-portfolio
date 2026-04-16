Step 1: Span the target machinre to acquire its IP.

Step 2: ping the target machine > ping "targetIP"

<img width="981" height="350" alt="image" src="https://github.com/user-attachments/assets/d81b40ac-6951-4ef2-923b-62ac735f9d63" />

Step 3:Scan target for open ports > namp -p- -sV "targetIP"
The -p- switch is used to scan not only the default ports but all the ports up to 65535

<img width="1204" height="412" alt="image" src="https://github.com/user-attachments/assets/0d97722b-be59-4506-98f5-04c3e17a3dc3" />

<h2>There is an open port 6379 which is running a Redis server!!!</h2>

Step 3 : download Redis-cli to interract with the database > sudo apt install redis-tools

Step 4: See the available commands > redis-cli --help

Step 5: Connect to the Redis server  > redir-cli -h "targetIP" 
-h switch is used to connect to the specific hostname

<img width="611" height="99" alt="image" src="https://github.com/user-attachments/assets/2be8af4d-e29c-4440-9535-7ffc32b5f63a" />

We enter the mode to interact with the server

Step 6: Search for informatio and statistics about the Redis server > info

<img width="645" height="190" alt="image" src="https://github.com/user-attachments/assets/ac31be1f-40f3-44c8-941c-d450dc2933ba" />

In the snippet we see there is one database with index 0 with 4 keys .
Step 7: Select the database > select 0

Step 8: List the available keys of the database > keys *

<img width="509" height="255" alt="image" src="https://github.com/user-attachments/assets/30ced6de-e278-493f-ac3a-4f6916b68e20" />

Step 9: View the valuse of each key > get "key" 

<img width="607" height="252" alt="image" src="https://github.com/user-attachments/assets/ef10d173-7ee2-4f1d-9237-64e8c2a53a23" />

<h2>Success: flag value acquired!!!</h2>


