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
CLient.py
```
import socket
s=socket.socket()
s.bind(('localhost', 9000))
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
Server.py
```
import socket
s=socket.socket()
s.connect(('localhost', 9000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived frome the server".encode())

```


## OUTPUT

<img width="1486" height="348" alt="{672D8CEC-D7E3-40E1-AE4E-0A7521CC2E76}" src="https://github.com/user-attachments/assets/71c274e5-8b7d-45b6-affc-10ee8172ad46" />



## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
