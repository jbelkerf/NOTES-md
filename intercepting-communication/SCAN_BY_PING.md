## Scan with ping
- ping command is used to know if a host is up :
```bash
$	 ping 10.0.0.1
$	 PING 10.0.0.1 (10.0.0.1) 56(84) bytes of data.
$	 64 bytes from 10.0.0.1: icmp_seq=1 ttl=64 time=0.028 ms
$	 64 bytes from 10.0.0.1: icmp_seq=2 ttl=64 time=0.034 ms
$	 64 bytes from 10.0.0.1: icmp_seq=3 ttl=64 time=0.044 ms
$	 64 bytes from 10.0.0.1: icmp_seq=4 ttl=64 time=0.033 ms
$	 64 bytes from 10.0.0.1: icmp_seq=5 ttl=64 time=0.034 ms
$^C
```
- if we want to set a time limit for our ping we can use the timeout command
```sql
$	 timeout 4 ping 10.0.0.1
```
