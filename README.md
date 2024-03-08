## Name:  Piritharaman R
## Ref no: 212223230148
# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
```
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
```
## PROGRAM
## Client
```
import socket
from datetime import datetime
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
print("Client Address : ",addr)
now = datetime.now()
c.send(now.strftime("%d/%m/%Y %H:%M:%S").encode())
ack=c.recv(1024).decode()
if ack:
 print(ack)
c.close()
```
## Server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
print(s.getsockname())
print(s.recv(1024).decode())
s.send("acknowledgement recived from the server".encode())
```
## OUTPUT
## Client
![image](https://github.com/ramanpiritha/2a_Stop_and_Wait_Protocol/assets/147084116/b2599c5f-5b36-4149-a54d-d276029e68a4)
## Server
![image](https://github.com/ramanpiritha/2a_Stop_and_Wait_Protocol/assets/147084116/db48a412-3650-465f-b180-7b40a6135258)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
