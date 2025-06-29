

```c
#include <stdio.h>

#include <stdlib.h>

#include <string.h>

#include <unistd.h> // for close()

#include <arpa/inet.h> // for inet_pton()

#include <sys/socket.h> // for socket functions

#include <netinet/in.h> // for sockaddr_in

  

int main()

{

int sock;

struct sockaddr_in server_addr;

const char *server_ip = "10.0.0.2";

int port = 31337;

int count = 10000;

while (count > 0)

{

int pid = fork();

if (pid == 0)

{

sock = socket(AF_INET, SOCK_STREAM, 0);

if (sock == -1)

{

perror("socket");

exit(1);

}

}

server_addr.sin_family = AF_INET;

server_addr.sin_port = htons(port);

  

//Convert IP address from text to binary form

if (inet_pton(AF_INET, server_ip, &server_addr.sin_addr) <= 0) {

perror("inet_pton");

close(sock);

exit(EXIT_FAILURE);

}

  

// 3. Connect to the server

if (connect(sock, (struct sockaddr*)&server_addr, sizeof(server_addr)) < 0) {

perror("connect");

close(sock);

exit(EXIT_FAILURE);

}

  

printf("Connected to the server!\n");

  

// 4. Optionally s

count--;

}

  

}
```
