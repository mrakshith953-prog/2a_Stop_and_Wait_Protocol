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
Developed by : **RAKSHITH M**<br>
Reg No : **212225220080**

### Client
```python
  import socket
s=socket.socket()
s.bind(('localhost',8080))
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
### Server
```python
import socket
s=socket.socket()
s.connect(('localhost',8080))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Received ".encode())
```

## OUTPUT
<img width="1699" height="213" alt="{93777B19-E9B9-4BC8-8194-59C258BE338C}" src="https://github.com/user-attachments/assets/033ba744-ada0-4d28-bb97-7e42b6087222" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
