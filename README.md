# personal-proxy
personal proxy setup

## azure setting
- need to enable ports: 
  - 443
  - 563
  - 8888

## setup - install 
```
sudo apt update
sudo apt install tinyproxy
```

## update config file location 
```
/etc/tinyproxy/tinyproxy.conf
```


## config file
```
# Listen on all interfaces on port 8888
Port 8888
BindSame yes
Allow 0.0.0.0/0
      
# Forward HTTPS traffic
ConnectPort 443
ConnectPort 563
   
# Log requests to /var/log/tinyproxy/tinyproxy.log
Logfile "/var/log/tinyproxy/tinyproxy.log"
LogLevel Info

```

## then to start: 
```
sudo systemctl start tinyproxy
sudo ufw allow 8888/tcp
```
