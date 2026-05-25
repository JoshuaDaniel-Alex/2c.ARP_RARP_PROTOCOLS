# 2c.SIMULATING ARP /RARP PROTOCOLS
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
## Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
## Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
P
## PROGRAM - ARP
Client:
```
# Developed by:Joshua Daniel A
# Register number:212225040161            
import socket 
s=socket.socket() 
s.bind(('localhost',8000)) 
s.listen(5) 
c,addr=s.accept() 
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"}; 
while True: 
    ip=c.recv(1024).decode() 
    try: 
        c.send(address[ip].encode()) 
    except KeyError: 
        c.send("Not Found".encode())             
```
Server:
```
# Developed by:Joshua Daniel A
# Register number:212225040161            
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter logical Address : ") 
    s.send(ip.encode()) 
    print("MAC Address",s.recv(1024).decode())              
```
## OUPUT - ARP
Client:
<img width="1146" height="284" alt="Screenshot 2026-05-19 133723" src="https://github.com/user-attachments/assets/ad9d7162-5bbe-4ed7-a3b4-fcf0c1271a1e" />

Server:
<img width="1312" height="381" alt="Screenshot 2026-05-19 133736" src="https://github.com/user-attachments/assets/d85c22fd-21a5-4f9e-a02e-d0064a21ea84" />

## PROGRAM - RARP
Client:
```
# Developed by:Joshua Daniel A
# Register number:212225040161            
import socket            
s=socket.socket()            
s.bind(('localhost',8000))                 
s.listen(5)            
c,addr=s.accept()                       
address={"F8:3D:C6:CE:5B:6E":"10.248.110.146"};             
while True:              
    ip=c.recv(1024).decode()            
    try:                
       c.send(address[ip].encode())             
    except KeyError:            
       c.send("Not Found".encode())               
```
Server:
```
# Developed by:Joshua Daniel A
# Register number:212225040161            
import socket           
s=socket.socket()                
s.connect(('localhost',8000))                
while True:               
    ip=input("Enter MAC Address : ")                
    s.send(ip.encode())                   
    print("IP Address",s.recv(1024).decode())                
```
## OUTPUT - RARP:
Client:
<img width="1919" height="339" alt="image" src="https://github.com/user-attachments/assets/6c1b261c-d59e-4d2d-abc3-5f0a1259103c" />

Server:
<img width="1919" height="327" alt="Screenshot 2026-05-25 211533" src="https://github.com/user-attachments/assets/c543aa62-07e5-41d6-9851-fd6a18ed4a7e" />


## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
