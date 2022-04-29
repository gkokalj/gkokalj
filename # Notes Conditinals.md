# Notes Conditinals 

### Expression syntax:
```bash
if [expression]; then
code if 'expression' is correct 
fi
```
#### Basic conditional example if .. then ... else
```bash
#!/bin/bash 
if [ "foo" = "foo" ]; then
    echo expression evaluated as true
else
    echo expression evaluated as false
fi
```
#### Conditionals with variables         
```bash
TR=1
OT=2
if [ "$TR" = "$OT" ]; then
    echo "Expression is true."
else    
    echo "Expression is false." 
fi
```
#### For sample
```bash
#!/bin/bash
for i in $( ls ); do
    echo item: $i        
done
```
 On the second line, we declare i to be the variable that will take the different values contained in $( ls ).

The third line could be longer if needed, or there could be more lines before the done (4).

'done' (4) indicates that the code that used the value of $i has finished and $i can take a new value.

This script has very little sense, but  a more useful way to use the for loop would be to use it to match only certain files on the previous example 

OR
```bash
#!/bin/bash
for i in `seq 1 10`;
do
    echo $i
done              
```
#### While sample
```bash
#!/bin/bash 
COUNTER=0
while [  $COUNTER -lt 10 ]; do
    echo The counter is $COUNTER
    let COUNTER=COUNTER+1 
done
```             

This script 'emulates' the well known (C, Pascal, perl, etc) 'for' structure

#### Until sample
```bash
#!/bin/bash 
COUNTER=20
until [  $COUNTER -lt 10 ]; do
    echo COUNTER $COUNTER
    let COUNTER-=1
    done
```             
### Functions
#### Functions sample
```bash
#!/bin/bash 
function quit {
    exit
}
function hello {
    echo Hello!
}
hello
quit
echo foo
```
#### Functions with parameters sample
```bash
#!/bin/bash 
function quit {
    exit
}  
function e {
    echo $1 
}  
e Hello
e World
quit
echo foo 
```
This script is almost identically to the previous one. The main difference is the funcion 'e'. This function, prints the first argument it receives. Arguments, within funtions, are treated in the same manner as arguments given to the script.
