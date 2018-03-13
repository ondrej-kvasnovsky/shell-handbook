# Running Apps



### Running Java Server

Lets say we want to start a java server on a linux instance \(without docker and other help\).

```
nohup  java -Xmx4g -jar \
  -Ddb.url=$DB_URL -Ddb.username=$DB_USERNAME -Ddb.password=$DB_PASSWORD \
  app.jar &
```



