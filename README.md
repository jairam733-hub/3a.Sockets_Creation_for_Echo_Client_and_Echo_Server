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
```
import socket
import threading
import time

# -------- Server Function --------
def server():
    server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

    # Reuse address
    server_socket.setsockopt(socket.SOL_SOCKET, socket.SO_REUSEADDR, 1)

    host = "127.0.0.1"
    port = 5000

    server_socket.bind((host, port))
    server_socket.listen(1)

    print("Server is waiting for connection...")

    conn, addr = server_socket.accept()

    print("Connected to:", addr)

    message = conn.recv(1024).decode()

    print("Message from client:", message)

    # Echo message back
    conn.send(message.encode())

    conn.close()
    server_socket.close()


# -------- Client Function --------
def client():
    client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

    host = "127.0.0.1"
    port = 5000

    # Small delay so server starts first
    time.sleep(1)

    client_socket.connect((host, port))

    message = input("Enter message: ")

    client_socket.send(message.encode())

    echo = client_socket.recv(1024).decode()

    print("Echo from server:", echo)

    client_socket.close()


# -------- Main Program --------
server_thread = threading.Thread(target=server)

server_thread.start()

client()

server_thread.join()
```
## OUPUT
<img width="1008" height="128" alt="image" src="https://github.com/user-attachments/assets/66988ee7-16c2-4efb-8a0b-1c8e801a73a4" />

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
