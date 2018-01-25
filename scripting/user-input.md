# User Input

There are two types of input into the script.

### Parameters

User can pass a parameter to a shell script. We can reference each param by its index, starting from `$1`.

```
➜ cat params.sh
#!/bin/bash
echo "Username: $1"
```

Here is what we get when we pass one parameter to the script. 

```
➜ ./params.sh John
Username: John
```

We can also pass output of other script as a parameter. 

```
➜ ./params.sh "$(./hello-world.sh)"
```

### Interactive Inputs

We can get user input when the script is running.

```
➜ cat params.sh
#!/bin/bash
read username
echo "Username: $username"
```

Then we are asked to insert username. 

```
➜ ./params.sh
Username:
John
Username: John
```

### Login Form

Here is how to read secret password without echoing it to the console. Lets say we want to build login form. 

```
➜ cat login.sh
#!/bin/bash
echo -n "Username:"
read username
echo -n "Password:"
read -s password

echo "You are trying to login with: $username and $password"
```

Lets try to run the script and type in the username and password. For validation purposes, we print out both inputs.

```
➜ ./login.sh
Username:john
Password:
You are trying to login with: john and my-secret
```

> `-n` flag will move cursor back so we continue typing just after `Username:` string.



