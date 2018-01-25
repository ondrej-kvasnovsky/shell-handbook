# Flow Control

### if else

For `if-else` statements, we place checks into `[]` brackets.

```
➜  shell cat ./if-else.sh
#!/bin/bash
read something
if [ -n $something ];
then # is not empty
  if [ "$something" == "hi" ];
  then # equals "hi"
    echo "Hi there!"
  fi
fi

if [ -n $something ] && [ "$something" == "hi" ]; then
  echo "Hi there, second time!"
fi
```

> We always want to wrap a variable in `""` to make sure if statement is valid.

Here is the list of all available options we can use to easier code inside `if` statement. 

| Expression | **Description** |
| :--- | :--- |
| -d file | True if file is a directory. |
| -e file | True if file exists. |
| -f file | True if file exists and is a regular file. |
| -L file | True if file is a symbolic link. |
| -r file | True if file is a file readable by you. |
| -w file | True if file is a file writable by you. |
| -x file | True if file is a file executable by you. |
| file1 -nt file2 | True if file1 is newer than \(according to modification time\) file2 |
| file1 -ot file2 | True iffile1is older thanfile2 |
| -z string | True ifstringis empty. |
| -n string | True if string is not empty. |
| string1 = string2 | True if string1 equals string2. |
| string1 != string2 | True if string1 does not equal string2. |
| -gt number | True if greater than a number |
| -lt number | True if less than a number |

More if else branches. 

```
#!/bin/bash
echo -n "Enter a number between 1 and 3 inclusive > "
read character
if [ "$character" = "1" ]; then
    echo "You entered one."
elif [ "$character" = "2" ]; then
    echo "You entered two."
elif [ "$character" = "3" ]; then
    echo "You entered three."
else
    echo "You did not enter a number between 1 and 3."
fi
```

### switch

An alternative to if-else with many branches is switch. 

```
➜ cat ./switch.sh
#!/bin/bash
echo -n "Enter a number between 1 and 3 inclusive > "
read character
case $character in
    1 ) echo "You entered one."
        ;;
    2 ) echo "You entered two."
        ;;
    3 ) echo "You entered three."
        ;;
    * ) echo "You did not enter a number between 1 and 3."
esac
```

Here is an output. 

```
➜ ./switch.sh
Enter a number between 1 and 3 inclusive > 2
You entered two.
```



