# Echoserver
Echo server and client using python socket

# AIM:

To develop an echo server and client using python socket

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client
## PROGRAM:
```
Client :

import socket

HOST = "127.0.0.1"
PORT = 65432

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()

    print("Server is waiting for connection...")

    conn, addr = s.accept()

    with conn:
        print(f"Connected by {addr}")

        while True:
            data = conn.recv(1024)

            if not data:
                break

            print("Received:", data.decode())

            conn.sendall(data)

Server :

import socket

HOST = "127.0.0.1"
PORT = 65432

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))

    message = input("Enter message: ")

    s.sendall(message.encode())

    data = s.recv(1024)

print("Server replied:", data.decode())
```

## OUTPUT:
<img width="1920" height="1103" alt="ethical hacking" src="https://github.com/user-attachments/assets/2a13c3ca-ebef-447a-b674-71ed82d67357" />

## RESULT:
The program is executed succesfully
