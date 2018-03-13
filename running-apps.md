# Running Apps

### Running Java Server

Lets say we want to start a java server on a linux instance \(without docker and other help\).

```
$ nohup  java -Xmx4g -jar \
    -Ddb.url=$DB_URL -Ddb.username=$DB_USERNAME -Ddb.password=$DB_PASSWORD \
    app.jar &
```

### Install NodeJS with yum

```
$ ulimit -n 100000
$ curl --silent --location https://rpm.nodesource.com/setup_9.x | sudo bash -
$ yum install -y nodejs
```



