# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## NAME: ZAFREEN J
## REGISTER NO:212223040252
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
client
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
server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
     print(s.recv(1024).decode())
     s.send("acknowledgement recived from the server".encode())
```
## OUPUT
client

![Screenshot 2024-04-15 190254](https://github.com/ZafreenJagir/2b_SLIDING_WINDOW_PROTOCOL/assets/144870573/22b4bb2b-cabf-4a1b-be22-83daa8fa53ab)

server

![Screenshot 2024-04-15 190331](https://github.com/ZafreenJagir/2b_SLIDING_WINDOW_PROTOCOL/assets/144870573/df4761d5-f5ba-4bdb-be54-d00117e67e68)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
