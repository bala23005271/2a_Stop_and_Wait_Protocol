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
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT
![image](https://github.com/bala23005271/2a_Stop_and_Wait_Protocol/assets/155039753/e6e71d14-752f-4065-855c-563fa07c9606)
![image](https://github.com/bala23005271/2a_Stop_and_Wait_Protocol/assets/155039753/45e12fd2-5179-4e8b-a42e-6bb2e98bb3c3)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
