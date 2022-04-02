# ssh-jumper-proxy-config


with socks5 proxy
```
Host 192.168.23.2:8080
  HostName 192.168.23.2:8080
  Port 22
  ForwardX11 no
  ProxyCommand nc -X 5 -x 192.168.23.2:8080 %h %p
  User username
  
```

with jumper server
```
Host jumpserver
  HostName 192.168.213.4
  Port 22
  User 123
  RemoteForward [192.168.23.2]:22

Host server
  HostName server
  HostName 192.168.23.2
  User username
  Port 22
  ForwardX11 no
  ProxyJump jumpserver

```
