# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## NAME : SRIMATHI S
## REF NO : 212225230275
## DATE : 20/05/2026
## AIM
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
## PROGRAM
SERVER
```
import socket 
# Create socket 
server = socket.socket() 
# Bind IP and port 
server.bind(("127.0.0.1", 5555)) 
# Listen for client 
server.listen(1) 
print("Server waiting for connection...") 
# Accept client 
client, addr = server.accept() 
print("Connected to:", addr) 
# Ask filename 
filename = input("Enter file name to send: ") 
# Open and send file 
with open(filename, "rb") as file: 
    data = file.read() 
client.send(data) 
print("File sent successfully") 
# Close connections 
client.close() 
server.close()
```
CLIENT
```
import socket 
# Create socket 
client = socket.socket() 
# Connect to server 
client.connect(("127.0.0.1", 5555)) 
# Save file name 
save_name = input("Enter name to save file: ") 
# Receive data 
data = client.recv(1000000) 
# Save file 
with open(save_name, "wb") as file: 
    file.write(data) 
print("File received successfully") 
# Close connection 
client.close()
```
## OUPUT

<img width="1920" height="1080" alt="Screenshot 2026-05-20 114736" src="https://github.com/user-attachments/assets/558fe364-649d-42e1-beb6-2859ecdca927" />

<img width="1920" height="1080" alt="Screenshot 2026-05-20 114723" src="https://github.com/user-attachments/assets/9ddd36b0-25c5-40bc-a598-91913b1070dd" />


<img width="1920" height="1080" alt="Screenshot 2026-05-20 114819" src="https://github.com/user-attachments/assets/5827070e-6d8f-46b4-a688-f429712b62d6" />


<img width="1920" height="1080" alt="Screenshot 2026-05-20 114809" src="https://github.com/user-attachments/assets/0a37a391-fc1f-4345-b3ca-0e006d97acb5" />

## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
