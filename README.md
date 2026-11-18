# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM
SERVER:
```
import socket
server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM) 

host = '127.0.0.1' 
port = 5000 
server_socket.bind((host, port)) 
server_socket.listen(1) 
print("Echo Server is waiting for connection...") 
client_socket, addr = server_socket.accept() 
print("Connected to:", addr) 
while True: 
    data = client_socket.recv(1024).decode() 
    if not data: 
        break 
print("Client:", data)
client_socket.send(data.encode())
client_socket.close() 
server_socket.close()
```
CLIENT:
```
import socket
client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
host = '127.0.0.1' 
port = 5000 
client_socket.connect((host, port)) 
while True:
    message = input("Enter message: ")
    client_socket.send(message.encode()) 
    if message.lower() == 'exit': 
        break
data = client_socket.recv(1024).decode() 
print("Server echoed:", data)
client_socket.close()
```
## OUPUT
<img width="1673" height="135" alt="Screenshot 2026-11-18 100708" src="https://github.com/user-attachments/assets/157af99b-c0f4-4357-822b-fef46fced626" />
<img width="1685" height="238" alt="Screenshot 2026-11-18 100734" src="https://github.com/user-attachments/assets/8a3f37a3-7e2e-485a-b7a9-5e5c77dd5adb" />

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
