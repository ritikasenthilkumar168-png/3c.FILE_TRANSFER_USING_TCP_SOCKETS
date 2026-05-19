# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## NAME: Ritika S
## REGNO: 212225220086
## AIM:
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
## PROGRAM:
server.py
```
import socket
# Create socket
server = socket.socket()
# Bind host and port
server.bind(("localhost", 5000))
# Listen for client
server.listen(1)
print("Waiting for connection...")
# Accept connection
client, addr = server.accept()
print("Connected to", addr)
# Open file and read data
file = open("sample.txt", "rb")
data = file.read()
# Send file data
client.send(data)
print("File sent successfully")
file.close()
client.close()
server.close()
```
client.py
```
import socket
# Create socket
client = socket.socket()
# Connect to server
client.connect(("localhost", 5000))
# Receive file data
data = client.recv(1024)
# Save received data into new file
file = open("received.txt", "wb")
file.write(data)
print("File received successfully")
file.close()
client.close()
```

## OUPUT:
# server.py
<img width="457" height="206" alt="Screenshot 2026-05-19 092936" src="https://github.com/user-attachments/assets/4485e443-070b-40ca-bb68-ad1003fc822c" />

# client.py
<img width="471" height="192" alt="Screenshot 2026-05-19 093026" src="https://github.com/user-attachments/assets/2aa580db-bac8-419f-ac2a-0e4454cdd364" />

## RESULT:
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
