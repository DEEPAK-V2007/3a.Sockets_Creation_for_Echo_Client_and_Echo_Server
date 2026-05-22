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
CLIENT.PY
```
import socket

s = socket.socket()

s.connect(('localhost', 8000))

print("Connected to server")

while True:
    msg = input("Client > ")

    s.send(msg.encode())

    if msg.lower() == "exit":
        break

    reply = s.recv(1024).decode()

    print("Server >", reply)

s.close()
```

SERVER.PY
```
import socket

s = socket.socket()

s.bind(('localhost', 8000))

s.listen(1)

print("Waiting for client connection...")

c, addr = s.accept()

print("Connected to:", addr)

while True:
    msg = c.recv(1024).decode()

    if msg.lower() == "exit":
        print("Client disconnected")
        break

    print("Client >", msg)

    reply = input("Server > ")

    c.send(reply.encode())

c.close()
s.close()
```
## OUPUT

<img width="1000" height="951" alt="{FFBAD61D-4983-4E74-97B6-3424A0FA26E5}" src="https://github.com/user-attachments/assets/21777561-9b56-41fe-bdaa-1e3cfb326a71" />

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
