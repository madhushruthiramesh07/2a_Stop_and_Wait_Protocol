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

```
1.Client
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

```
2.server
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT
<img width="1403" height="292" alt="image" src="https://github.com/user-attachments/assets/c9622bd3-b585-48fb-892a-6ee7d7d115b5" />
<img width="1403" height="292" alt="image" src="https://github.com/user-attachments/assets/f00adbbc-fd68-47e9-9e98-8f34e4cc382c" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
