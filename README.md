# EX-3 IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
# DATE : 23.03.2023
## AIM :
To write a python program to perform sliding window protocol
## ALGORITHM :
### STEP1 : Start the program.
### STEP2 : Get the frame size from the user
### STEP3 : To create the frame based on the user request.
### STEP4 : To send frames to server from the client side.
### STEP5 : If your frames reach the server it will send ACK signal to client otherwise it will send NACKsignal to client.
### STEP6 : Stop the program.
## CLIENT PROGRAM :

## Developed : Malarvizhi G
## Reg no : 212222040096
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
## SERVER PROGRAM :
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("acknowledgement recived from the server".encode())
```
## OUTPUT :
## SERVER OUTPUT :
![ex03 server output](https://github.com/22008650/EX-3/assets/122548204/cd5984ec-740b-4b91-8cf1-2d004461f259)
## CLIENT OUTPUT :
![ex03 client output](https://github.com/22008650/EX-3/assets/122548204/a92eaaad-77f4-47f7-8e7b-fd3196b02683)
## RESULT :
Thus, python program to perform stop and wait protocol And Sliding Window Protocol was successfully executed.


