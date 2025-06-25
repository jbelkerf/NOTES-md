
##CONNECT
- to connect to a host using netcat 
```bash
$	 nc 10.0.0.1 31337
```
-> 10.0.01 is the ip and 31337 is the port

## SEND DATA
- to send data using netcat we should first connect then type the msg then folowed by enter or "\n" because it bffers till it find the newline
```bash
$	 nc 10.0.0.1 31337
$    Hello world

```

## Shutdown 
- if we want to shutdown a connection in netcat we should launch it with a specific flag -N so it stops when we send EOF aka ctrl D:
```bash
$	 nc -N 10.0.0.1 31337
^D
```

## Listen 
- if we want to lesten to a specific port for connection we launch the netcat with -l option and the port we listen on:
```bash
nc -l 31337
```

## Scan with ping
- ping command is used to know if a host is up :
```bash


```