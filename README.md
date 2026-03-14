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
#Server program:
import socket

server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

host = "localhost"

port = 12345

server_socket.bind((host, port))

server_socket.listen(1)

print("Server is waiting for connection...")

conn, addr = server_socket.accept()

print("Connected to:", addr)

message = conn.recv(1024).decode()

print("Message from client:", message)

conn.send(message.encode())

conn.close()

#Server output:

PS C:\Users\acer\OneDrive\Attachments>  & 'c:\Users\acer\AppData\Local\Microsoft\WindowsApps\python3.13.exe' 'c:\Users\acer\.vscode\extensions\ms-python.debugpy-2025.18.0-win32-x64\bundled\libs\debugpy\launcher' '59039' '--' 'C:\Users\acer\OneDrive\Attachments\echo server.py' 

Server is waiting for connection...

Connected to: ('127.0.0.1', 59084)

Message from client: Good morning

PS C:\Users\acer\OneDrive\Attachments> 

#Client program:

import socket

client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

host = "localhost"

port = 12345

client_socket.connect((host, port))

message = input("Enter message: ")

client_socket.send(message.encode())

echo = client_socket.recv(1024).decode()

print("Echo from server:", echo)

client_socket.close()

#Client output:

PS C:\Users\acer\OneDrive\Attachments>  & 'c:\Users\acer\AppData\Local\Microsoft\WindowsApps\python3.13.exe' 'c:\Users\acer\.vscode\extensions\ms-python.debugpy-2025.18.0-win32-x64\bundled\libs\debugpy\launcher' '59073' '--' 'C:\Users\acer\OneDrive\Attachments\echo client.py' 

Enter message: Good morning

Echo from server: Good morning

PS C:\Users\acer\OneDrive\Attachments> 
## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
