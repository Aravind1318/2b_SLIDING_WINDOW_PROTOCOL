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
```python
CLIENT
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
SERVER
 
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True:    
    print(s.recv(1024).decode()) 
    s.send("acknowledgement recived from the server".encode())
```
## OUPUT
<img width="817" height="433" alt="2ba" src="https://github.com/user-attachments/assets/db74a306-781b-404b-a065-b1fa4c197b9a" />
<img width="822" height="282" alt="2bb" src="https://github.com/user-attachments/assets/6435a6de-98b0-4d61-9a86-7919dc3efab2" />
<img width="857" height="303" alt="2b 1" src="https://github.com/user-attachments/assets/da693f45-4fa3-4c62-b626-c9dbd64aeaee" />
<img width="852" height="248" alt="2b 2" src="https://github.com/user-attachments/assets/90007754-f182-4fcb-a5dd-efe455dc916a" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
