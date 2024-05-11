# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
CLIENT:
```
VIJAY R
212223240178

import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
 i=input("Enter a data: ")
 c.send(i.encode())
 ack=c.recv(1024).decode()
 if ack:
   print(ack)
   continue
 else:
   c.close()
   break
```
SERVER
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
## OUTPUT
CLIENT![Screenshot 2024-05-11 161946](https://github.com/vijayr21/2a_Stop_and_Wait_Protocol/assets/149347607/8f9c04a7-1bf4-4424-af6c-852e7d0ebbaf)
SERVER![Screenshot 2024-05-11 162004](https://github.com/vijayr21/2a_Stop_and_Wait_Protocol/assets/149347607/aa3b1eb7-8e37-4f46-ab37-35e42aea818a)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
