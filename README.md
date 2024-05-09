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
## CLIENT:
```
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
## SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())

```
## OUTPUT
![image](https://github.com/NaliniG007/2a_Stop_and_Wait_Protocol/assets/146498969/e9690040-ccd9-46e1-955b-aba1f561398c)
![image](https://github.com/NaliniG007/2a_Stop_and_Wait_Protocol/assets/146498969/35a1cfbe-a593-4082-822c-d71b773d0f92)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
