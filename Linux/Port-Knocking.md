### Port Knocking

**Metaphor**: We must do the exactly sequence of secret knocking to open a door. 
If someone knocks the wrong way the door doesn't show. Only people who know the exact sequence get let in.

**Computer terms**: Server's ports are all hidden by a firewall, to unlock the real door you have knock on a secret sequence of closed ports in the right order.
If correct, the firewall siently opens the real port just for one specific IP address. 

Sadservers Challenge: https://sadservers.com/newserver/taipei

## Reasons for getting Connection Refused

1) Problem in the web server:
  - If we get the netstat -ln | grep {PORT} and it is LISTEN, means that the nginx is running and bound to the port. So not this problem.
2) Service running, firewall blocking.
3) Service running, wrong port.
4) Port knocking active.

- Officially are 1-65535 ports in Linux. (https://serverfault.com/questions/103626/what-is-the-maximum-port-number-in-linux)

Brutal-force approach: 

admin@ip-10-1-12-47:~$ for i in $(seq 1 65535); do knock localhost $i; curl -s localhost && echo "Port was $i" && break; done
