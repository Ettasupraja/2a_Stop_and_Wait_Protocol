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
client:
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
server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
  print(s.recv(1024).decode())
  s.send("Acknowledgement Recived".encode())
  ```
## OUTPUT
![Screenshot 2024-05-10 131610](https://github.com/Ettasupraja/2a_Stop_and_Wait_Protocol/assets/151641352/ba347ef3-1a30-4333-a01b-b2f2500839b7)
![Screenshot 2024-05-10 131622](https://github.com/Ettasupraja/2a_Stop_and_Wait_Protocol/assets/151641352/c690b4ff-72ab-4a3b-a566-4fbaf287c12d)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
