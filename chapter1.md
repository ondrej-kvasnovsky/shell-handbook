# Shell Implementations

There are couple of shell implementations. Here are some of them.

* sh
* bash
* zsh

> See the list of command-line interprets on [wikipage](https://en.wikipedia.org/wiki/List_of_command-line_interpreters).

### Hello World example

Lets create `Hello World` script and try to execute it with all the listed shells.

```
➜ vi hello-world.sh
echo "Hello World!"
```

Then we try to execute the script.

```
➜ ./hello-world.sh
zsh: permission denied: ./hello-world.sh
```

We need to make the file executable first.

```
➜ chmod +x hello-world.sh
```

When we try to execute the script again, we get the hello world message.

```
➜ ./hello-world.sh
Hello World!
```

### sh

`sh` was developed by [Stephen Bourne](https://en.wikipedia.org/wiki/Bourne_shell) released in 1977. It can be found in `/bin/sh`.

```
➜ sh hello-world.sh
Hello World!
```

### bash

`bash` is unix shell and replacement for `sh`. bash was written by [Brian Fox](https://en.wikipedia.org/wiki/Bash_%28Unix_shell%29) and was first released in 1989.

```
➜ bash hello-world.sh
Hello World!
```

### zsh

`zsh` is replacement for `bash`. `zsh` was written by [Paul Falstad](https://en.wikipedia.org/wiki/Z_shell) and was first released in 1990.

```
➜ zsh hello-world.sh
Hello World!
```

### What shell am I using?

Here is how to find what version of shell is currently used on your system.

```
➜ echo $0
-zsh
```



