# EX-2 IMPLEMENTATION OF STOP AND WAIT PROTOCOL

### DATE:15-03-2023

### AIM :

## To write a python program to perform stop and wait protocol

### ALGORITHM :

## 1. . Start the program.
## 2. Get the frame size from the user
## 3. To create the frame based on the user request.
## 4. To send frames to server from the client side.
## 5. If your frames reach the server it will send ACK signal to client
otherwise it will sendNACK signal to client.

## 6. Stop the program

### CLIENT PROGRAM :
```

import socket
s = socket.socket()
s.bind(("localhost", 8000))
s.listen(5)
c, addr = s.accept()
while True:
    i = input("Enter a data:")
    c.send(i.encode())
    ack = c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
```
### SERVER PROGRAM :
```
import socket
s=socket.socket()
s.connect(("localhost", 8000))
while True:
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Received".encode())
```
### SERVER OUTPUT :
![image](https://github.com/tsanjaithirumal/EX-2/assets/119393916/395fa2e2-9e89-49ac-ada5-da45a69bd4f7)
### CLIENT OUTPUT :
![image](https://github.com/tsanjaithirumal/EX-2/assets/119393916/9dbc48c9-2207-4bc9-9d2f-879541bf648d)


### RESULT :
Thus, python program to perform stop and wait protocol was successfully executed.




