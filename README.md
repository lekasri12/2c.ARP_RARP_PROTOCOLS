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
```
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
## OUPUT - ARP
![325083871-3b7ee08c-a686-4832-8690-3e938c14b7f4](https://github.com/lekasri12/2c.ARP_RARP_PROTOCOLS/assets/149037427/9e7309b4-394b-4946-9199-b1b1a60a3036)

## PROGRAM - RARP
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter logical Address : ")
    s.send(ip.encode())
    print("MAC Address",s.recv(1024).decode())
```
## OUPUT -RARP
![325083920-2784c864-d334-4b60-b3ab-1f0b8441f8e6](https://github.com/lekasri12/2c.ARP_RARP_PROTOCOLS/assets/149037427/810506e9-8601-4554-ac61-f4067636ca0a)

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
