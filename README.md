# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
## AIM:
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM:
### Server Program:
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
    if data.lower() == 'exit':
        break 
    client_socket.send(data.encode()) 

client_socket.close() 
server_socket.close()
```

### Client Program:
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
## OUTPUT:
### Server Output:
<img width="1920" height="1080" alt="Screenshot (215)" src="https://github.com/user-attachments/assets/947c9ce4-965a-4e23-a321-336bf9c6a96f" />
### Client Output:
<img width="1920" height="1080" alt="Screenshot (216)" src="https://github.com/user-attachments/assets/6ee5bab1-6a6c-45f6-aab4-670c3bacc56f" />

## RESULT:
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links was successfully created and executed.
