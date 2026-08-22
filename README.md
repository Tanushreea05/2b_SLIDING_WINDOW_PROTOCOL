# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM

## Client

```import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
while(i<len(l)):
st+=s
c.send(str(l[i:st]).encode())
ack=c.recv(1024).decode()
if ack:
print(ack)
i+=s
```

## Server

```import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
print(s.recv(1024).decode())
s.send("acknowledgement received from the server".encode())
```
## OUPUT
## Client
<img width="895" height="958" alt="image" src="https://github.com/user-attachments/assets/e400913a-c722-44fc-811a-8a13301f2cd2" />


## Server
<img width="890" height="947" alt="image" src="https://github.com/user-attachments/assets/e7e6ce11-fd8f-41e6-a123-bd530e36f33c" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
