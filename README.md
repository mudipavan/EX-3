# EX-3 IMPLEMENTATION OF SLIDING WINDOW PROTOCOL

## DATE :22-03-2023

## AIM :
To write a python program to perform sliding window protocol.
## ALGORITHM :

```
1.Start the program.
2.Get the frame size from the user
3.To create the frame based on the user request.
4.To send frames to server from the client side.
5.If your frames reach the server it will send ACK signal to client otherwise it will 
  send NACKsignal to client.
6.Stop the program
```
## PROGRAM :
```
Developed By:mudi.pavan kumar
Reg No: 212221230067
```
### client:
```
import socket
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
### server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("acknowledgement recived from the server".encode())
```
## OUTPUT:
![cn 3-1](https://github.com/yashaswimitta/EX-3/assets/94619247/ad183fe3-5159-46e2-a678-f8ab38c21d5d)

![cn 3-2](https://github.com/yashaswimitta/EX-3/assets/94619247/afd2b91f-ed23-4a44-92a9-4ca19523fed6)




## RESULT:
Thus, python program to perform  SLIDING WINDOW PROTOCOL was successfully executed.
