# Linux Commands

[history](https://ss64.com/bash/history.html) - returns all executed commands

* `Ctrl+R` to search in history
* `!!` go to previous command
* `Ctrl+P` provides previous command
* `!1` to execute first command in history

```
$ history
1 cat index.js
2 vi index.js
```

[ls](http://man7.org/linux/man-pages/man1/ls.1.html) - list files and directories

Print content of current directory as long list `-l`, not ignoring entries starting with dot `-a`,  in columns, with file index `-i`, sorted by modification date `-t`.

```
$ ls -laist
total 40
8599111455  0 drwxr-xr-x   6 ok  staff    192 Mar 13 09:11:09 2018 .
8599112561  8 -rw-r--r--   1 ok  staff    353 Mar 13 09:11:09 2018 package.json
8599112253  8 -rw-r--r--   1 ok  staff    284 Mar 13 09:07:43 2018 index.js
8599112008 24 -rw-r--r--   1 ok  staff  10467 Mar 13 09:05:17 2018 package-lock.json
8599111546  0 drwxr-xr-x  43 ok  staff   1376 Mar 13 09:05:17 2018 node_modules
8595834271  0 drwxr-xr-x   5 ok  staff    160 Mar 13 09:04:17 2018 ..
```

[find](http://man7.org/linux/man-pages/man1/find.1.html) - searches for files in directories

Find all files larger than 100MB.

```
find /Users/ -type f -size +100M -print
```

[ps](http://man7.org/linux/man-pages/man1/ps.1p.html) - reports processes status

The following will print all processes in full format

```
$ ps -ef
```

[tail](http://man7.org/linux/man-pages/man1/tail.1.html) - prints out last lines from a file

```
$ tail -f logs/app.log
```

[du](https://linux.die.net/man/1/du) - free space in a folder

```
$ du -h
 16K    ./node_modules/destroy
 24K    ./node_modules/content-type
```

[htop](https://linux.die.net/man/1/htop) - interactive process viewer

```
$ sudo yum install htop
$ htop
  1  [|||||||||||                                           17.9%]   5  [||||||||                                              11.9%]
  2  [||                                                     1.3%]   6  [                                                       0.0%]
  3  [||||||||                                              11.8%]   7  [||||||||                                              10.5%]
  4  [||                                                     1.3%]   8  [||                                                     1.3%]
  Mem[||||||||||||||||||||||||||||||||||||||||||||||||8.50G/16.0G]   Tasks: 451, 1485 thr; 1 running
  Swp[||||||||||||||||||||||||||||||                  1.51G/3.00G]   Load average: 3.25 3.12 2.96
                                                                     Uptime: 18 days, 16:01:31

  PID USER      PRI  NI  VIRT   RES S CPU% MEM%   TIME+  Command
43378 ok  24   0 8523M  112M ?  6.3  0.7  1h26:53 /Applications/iTerm.app/Contents/MacOS/iTerm2
....
```

[tmux](https://linux.die.net/man/1/tmux) - enables to run multiple session from one screen

```
$ tmux
$ tmux list-sessions
0: 1 windows (created Tue Mar 13 09:43:33 2018) [138x70] (attached)
```

[rsync](https://linux.die.net/man/1/rsync) - remote file copying / sync tool

Sync local changes with two server that can be found under 1.1.1.1 and 2.2.2.2 IP addresses.

```
#! env sh

ipAddresses='1.1.1.1 2.2.2.2'

for ipAddress in $ipAddresses; do
  echo "Sync: $ipAddress"
  rsync -rave "ssh -i ~/.ssh/somekey.pem" \
    --exclude 'node_modules' \
    --exclude 'logs' \
    --exclude '.git' \
    . \
    myusernamer@$ipAddress:/home/myusername/

  ssh -i ~/.ssh/somekey.pem myusernamer@$ipAddress pm2 restart all
done
```



