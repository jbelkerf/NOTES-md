

## LIST RULES

- if we want to list rules for OUTPUT OR INPUT OR FORWORD
```bash
$	 iptables -L OUTPUT --line-numbers
Chain OUTPUT (policy ACCEPT)
num  target     prot opt source               destination         
1    ACCEPT     tcp  --  anywhere             anywhere             tcp dpt:31337
```
## DELETE RULES

- if we want to delete rules we can 
```bash
$	 iptables -D OUTPUT 1
```
-> the '1' is the line number of the rule you want to delete
## ADD RULES
- this command is used to configure firewall
```bash
$	 iptables -A INPUT -p tcp --dport 31337 -j DROP
```
-> -A append (there is also the -I option insert) it to all input devices (there is OUTPUT AND FORWORD)
-> -p tcp choose tcp packets
-> --dport   choose the port
-> -j choose the action either DROP or ACCEPT

- if we want to block it jus from one ip we can do 
```bash
$	 iptables -A INPUT -p tcp --dport 31337 -s 10.0.0.4 -j DROP 
```
-> -s choose the exact ip to block

## DELETE RULES