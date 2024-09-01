Bash is without doubt the most famous scripting language out there.

## Creating a BASH Script 
- File Extension:  .sh 
- Mostly Interpreted 
- Support: All Bash versions
### Creating a sample bash script
```bash
# creating an empty file called 'myscript.sh'
touch myscript.sh

# appending sample commands in myscript.sh
echo "pwd" >> myscript.sh

# setting executable permission ( SINGLE TIME ONLY )
chmod +x ./myscript.sh

#running the script
./myscript.sh

# NOTE : We could also use 
# bash ./myscript.sh

# example output
# /home/akshit/

```

## Saying Hello World in BASH
**Ease:** EASY

### 1 : Create a file called hw.sh using nano or vim 

Note : if you dont know how to use nano or vim consider checking out the video

[![Youtube Nano Video](https://img.shields.io/badge/YouTube-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://youtu.be/fIl8jAfqsbg?si=nkRKBJPKJwmoVJEI)

```bash
# filename hw.sh
echo "Hello World"
```

Running the script

```bash
# setting executable permission
chmod +x ./hw.sh

# running the script
./hw.sh

# output
# Hello World
```

## Learning about the variables in bash
- EASE: Easy

Bash follows standard variable naming rules.

By CONVENTION constant variables are capitalized.

**Variables are accessed using *$* operator**

### Simply assign variables using <var_name>=<var_value>

**IMPORTANT**: There should be **<font color="red">no space before or after</font>**  `=`
```bash
# filename: vars.sh
name=Alex
echo "Hello $name"
```

Running the script
```bash # setting executable permission chmod +x ./vars.sh

# running the script
./vars.sh

# output
# Hello Alex
```

### Environment Variables
The linux system by default loads some variables in the memory
These variables are called `ENV` Variables
NOTE: These variables are used in same manner as normal variables.

```bash
# directly in shell
echo $USER

# sample output
# akshit
```


### Numeric Values
The variables by default are treated as string.
We use `$(( <numeric operations> ))` to do artithmetic operations such as addition, substraction, multiplication etc.

```bash
# filename ariths.sh

NUM1=20
NUM2=30

echo $NUM1+$NUM2
#OUTPUT: 20+30

echo $(( $NUM1 + $NUM2 ))
#OUTPUT: 50
```

Running the script
```bash
# setting executable permission
chmod +x ./ariths.sh

# running the script
./ariths.sh

#OUTPUT:
# 20+30
# 50
```

# Reading User Input

The `read` command is used to read user's input from the terminal.

SYNTAX: read [OPTIONS] <variable_name>

The command provides for following flags.
- `-p PROMPT`: Display a prompt before reading input.
- `-t SECONDS`: Timeout after a specified number of seconds.
- `-s`: Silent mode (do not echo input).
- `-n N`: Read only N characters.
- `-r`: Do not allow backslashes to escape characters.

```bash
# filename inp.sh

read -p "Hello There! What's Your Name " NAME

echo "So $NAME you just entered your name"

```

# Practise Question 1 
### Write a Script using Bash to input a directory and cd to that directory then ls in that directory.
```
#!/bin/bash
# Sample Solution
# sc_bash.sh
ls --color=auto

read -p "|Enter the directory name>" dir

cd $dir 

ls -l
```

![Made with VHS](https://vhs.charm.sh/vhs-6jU7poZTg0AYHWS6xb9tE3.gif)

### Write a script in BASH to input a number and add 20% GST to it. 

ISSUE : You cant just simply multiply floating point numbers in bash 
SOLUTION : using `bc` [Basic Calculator]
NOTE:
We have used the pipe `|`. To know more abut pipe follow this link

```
# Sample solution 
# gst.sh

read -p "Enter amount without GST:" amt

bill=$(echo "1.2 * $amt" | bc)

echo "The final amount: $bill"
```

![Made with VHS](https://vhs.charm.sh/vhs-1Bt5oWwijhWxDi5YLnn573.gif)