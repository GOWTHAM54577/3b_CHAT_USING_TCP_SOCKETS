# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM
### SERVER
```
import socket

HOST = '127.0.0.1'  
PORT = 65432       

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print('Connected by', addr)
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
```
### CLIENT
```
import socket

HOST = '127.0.0.1'  
PORT = 65432        

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    while True:
        message = input("Enter message to send to server: ")
        s.sendall(message.encode())
        data = s.recv(1024)
        print('Received', repr(data.decode()))

```
## OUPUT
### SERVER
![WhatsApp Image 2024-04-03 at 11 02 49_56184284](https://github.com/GOWTHAM54577/3b_CHAT_USING_TCP_SOCKETS/assets/144589420/65b3bc74-ba95-4d02-b6c8-dce54586b1d1)

### CLIENT

![WhatsApp Image 2024-04-03 at 11 02 50_ae024e3b](https://github.com/GOWTHAM54577/3b_CHAT_USING_TCP_SOCKETS/assets/144589420/e7bb9320-b9cf-4838-89aa-63380d02d7c7)


## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
