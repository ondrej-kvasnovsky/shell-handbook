# Loops

Loops make passible to iterate through values. 

### For Loop

`for` loop iterates through values provided.

```
➜ cat for.sh
#!/bin/bash
for i in 1 2 3 4 5 hi
do
  echo "Printing: $i"
done
```

Then `for` loop iterates through values from 1 to 5 and does what is defined in `do-done` section.

```
➜ ./for.sh
Printing: 1
Printing: 2
Printing: 3
Printing: 4
Printing: 5
Printing: hi
```

### While Loop

`while` loops is repeated until certain condition is positive.

```
#!/bin/sh
INPUT_STRING=hello
while [ "$INPUT_STRING" != "quit" ]
do
  echo "Please type something in (quit)"
  read INPUT_STRING
  echo "You typed: $INPUT_STRING"
done
```

When we run the script, we will need to write quit to exit the while loop.

```
➜ ./while.sh
Please type something in (quit)
hi
You typed: hi
Please type something in (quit)
quit
You typed: quit
➜
```



