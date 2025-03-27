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
### server:
~~~
import socket
  s=socket.socket()
  s.bind(('localhost',8000))
  s.listen(5)
  c,addr=s.accept()
  while True:
      i=input("Enter a data:")
      c.send(i.encode())
      ack=c.recv(1024).decode()
      if ack:
          print(ack)
          continue
      else:
          c.close()
          break
~~~
  
### client:
~~~
import socket
  s=socket.socket()
  s.connect(('localhost',8000))
  while True:
      print(s.recv(1024).decode())
      s.send("Acknowledgement Received".encode())
~~~
## OUTPUT

### server

![Screenshot 2025-03-22 110201](https://github.com/user-attachments/assets/1315788e-f016-432c-961c-3847db4f9b19)

### client

![Screenshot 2025-03-22 110207](https://github.com/user-attachments/assets/e9b41077-fe32-4b7d-9b65-081718543449)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
