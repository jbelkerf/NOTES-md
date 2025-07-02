- simple udp connection

```python
import socket

  

sock = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
  
add = ("10.0.0.2", 31337)

msg = b"Hello, World!\n"

sock.sendto(msg, add) 

print(sock.recvfrom(1024))
```

- udp connection with sport set 

```python
import socket

sock = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)

add = ("10.0.0.2", 31337)

msg = b"Hello, World!\n"

sock.bind(("10.0.0.1", 31338))

sock.sendto(msg, add)


print(sock.recvfrom(1024))
```