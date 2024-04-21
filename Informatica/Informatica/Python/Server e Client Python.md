# Step da fare Server
1) importa libreria
```python:
import socket
```
2) creare oggetto socket
```python:
server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
```
3) fare binding
```python:
server_socket.bind((HOST, PORT))
```
4) metterci in ascolto
```python:
server_socket.listen()  
print(f"Server start on port: {PORT}")
```
5) aspettare il messaggio
```python:
while goAgain:  
    connessione, indirizzo_del_client = server_socket.accept()
```
6) prelevare il messaggio
```python:
connessione, indirizzo_del_client = server_socket.accept() #il mess si trova in connessione
messaggio = connessione.recv(1024).decode()  
print(messaggio)
```
7) se serve dare risposta
8) chiudere connessione client
```python:
connessione.close()
```
9) chiudere conn server

# Step da fare Client

1) importa libreria
```python:
import socket
```
2) creare oggetto socket
```python:
socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
```
3) connetto al server
```python:
socket.connect((HOST, PORT))
```
1) invia messaggio
```python:
messaggio = input("Scirvi qualoca -> ")  
socket.send(messaggio.encode())
```
3) attendere eventuale risposta
4) chiudere connessione
```python:
socket.close()
```


