# HTTP

Couple of useful commands with examples. 

### wget

`wget` with authentication

```
wget --user=reader --password=mypassword  https://company.jfrog.io/quadanalytix/path/tojar/myapp.jar
```

### curl 

`curl` with proxy that is secured and we need to provide username and password together with proxy IP and port.

```
curl -U username:password -x 1.1.1.1:80 https://www.google.com
```



