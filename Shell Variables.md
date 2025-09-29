# Module Name: Shell Variables

## Challenge 1: Printing Variables
The challenge requires you print the value of a variable.

### Solve
**Flag:** `pwn.college{owG9bSybwOlRuF0aIii9orL1uDl.QX3UTN0wSO5IzNzEzW}`

Since the description says that the flag is given in the FLAG variable, I printed it out using echo and prepended the variable name with $.

```bash
hacker@variables~printing-variables:~$ echo $FLAG
pwn.college{owG9bSybwOlRuF0aIii9orL1uDl.QX3UTN0wSO5IzNzEzW}
```

### New Learnings
I learnt how to print out the value of a variable.

### References 
NIL

## Challenge 2: Setting Variables
The challenge requires you to set the value of a variable.

### Solve
**Flag:** `pwn.college{A2ytlwA12bl1qcdPiJSA6VkCyvN.QX5UTN0wSO5IzNzEzW}`

I set the value of PWN variable to COLLEGE and was able to obtain the flag.


```bash
hacker@variables~setting-variables:~$ PWN=COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{A2ytlwA12bl1qcdPiJSA6VkCyvN.QX5UTN0wSO5IzNzEzW}
```

### New Learnings
Through this challenge I learnt how to set values for variables.

### References 
NIL

## Challenge 3: Multi-word Variables
The challenge requires you to set a variable to a multi-word value.

### Solve
**Flag:** `pwn.college{kq2alYn7XPWAF8liShMRjaL_9vr.QXwYTN0wSO5IzNzEzW}`

Using quotes, I was able to set the value of PWN as COLLEGE YEAH and obtained the flag.


```bash
hacker@variables~multi-word-variables:~$ PWN="COLLEGE YEAH"
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{kq2alYn7XPWAF8liShMRjaL_9vr.QXwYTN0wSO5IzNzEzW}

```

### New Learnings
I learned how to set multi word values for a variable using quotes ("").

### References 
NIL

## Challenge 4: Exporting Variables
The challenge requires you to export a variable and invoke the program.

### Solve
**Flag:** `pwn.college{AzKwSmPhtnb7tsy4eFFZ02etd33.QXyYTN0wSO5IzNzEzW}`

First, I exported the PWN variable and set its value to COLLEGE. Then I set the value of COLLEGE to PWN without exporting it. After this, when I invoked the /challenge/run program, I was able to obtain the key.

```bash
hacker@variables~exporting-variables:~$ export PWN=COLLEGE
You've set the PWN variable to the proper value!
hacker@variables~exporting-variables:~$ COLLEGE=PWN
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ /challenge/run
CORRECT!
You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. Great
job! Here is your flag:
pwn.college{AzKwSmPhtnb7tsy4eFFZ02etd33.QXyYTN0wSO5IzNzEzW}
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
```

### New Learnings
I learnt how to export variables and set values for them.

### References 
NIL

## Challenge 5: Printing Exported Variables
The challenge requires you to print exported variables using env command.

### Solve
**Flag:** `pwn.college{QlufIiytx56uyT8_odLGmOlRjkC.QX4UTN0wSO5IzNzEzW}`

I ran the env command which gave me a list of every exported variable. I was able to obtain the flag from the FLAG variable.

```bash
hacker@variables~printing-exported-variables:~$ env
SHELL=/run/dojo/bin/bash
HOSTNAME=variables~printing-exported-variables
PWD=/home/hacker
MANPATH=/run/dojo/share/man:
DOJO_AUTH_TOKEN=0b50c58017bce8f536b28b17d7c97c7a53dc34c8137de1de35d5635e486bd293
HOME=/home/hacker
LANG=C.UTF-8
FLAG=pwn.college{QlufIiytx56uyT8_odLGmOlRjkC.QX4UTN0wSO5IzNzEzW}
TERMINFO=/run/dojo/share/terminfo
TERM=xterm-256color
SHLVL=2
LC_CTYPE=C.UTF-8
SSL_CERT_FILE=/run/dojo/etc/ssl/certs/ca-bundle.crt
PATH=/run/challenge/bin:/run/dojo/bin:/root/.cargo/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
DEBIAN_FRONTEND=noninteractive
_=/run/dojo/bin/env
```

### New Learnings
I learnt how to use the env command to list out all the exported variables.

### References 
NIL

## Challenge 6: Storing Command Output
The challenge requires you to store the output of a command/program into a variable.

### Solve
**Flag:** `pwn.college{szkdiD6izbAIa9LNRMVwzlF3c_P.QX1cDN1wSO5IzNzEzW}`

First I stored the output of /challenge/run into PWN variable. Then, using echo command, I printed out the flag.

```bash
hacker@variables~storing-command-output:~$ PWN=$(/challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out
and submit it!
hacker@variables~storing-command-output:~$ echo $PWN
pwn.college{szkdiD6izbAIa9LNRMVwzlF3c_P.QX1cDN1wSO5IzNzEzW}
```

### New Learnings
I learnt how to store command output into variables for later use.

### References 
NIL

## Challenge 7: Reading Input
The challenge requires you to read input and store it into a variable.

### Solve
**Flag:** `pwn.college{cH-Q-Id2zeUwWUNU_as3CqXU3_o.QX4cTN0wSO5IzNzEzW}`

Using read command, I stored the input given by the user into variable PWN and obtained the flag.

```bash
hacker@variables~reading-input:~$ read -p "Enter COLLEGE " PWN
Enter COLLEGE COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{cH-Q-Id2zeUwWUNU_as3CqXU3_o.QX4cTN0wSO5IzNzEzW}
```

### New Learnings
I learnt how to obtain input from the user and store it into a variable.

### References 
NIL

## Challenge 8: Reading Files
The challenge requires you to you read the /challenge/read_me into the PWN variable in one command.

### Solve
**Flag:** `pwn.college{4fOZ2TdjnclYmBjmJ6NUywtf-Mj.QXwIDO0wSO5IzNzEzW}`

I used the read command to read the /challenge/read_me into the PWN variable and so I was able to obtain the flag.


```bash
hacker@variables~reading-files:~$ read PWN < /challenge/read_me
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{4fOZ2TdjnclYmBjmJ6NUywtf-Mj.QXwIDO0wSO5IzNzEzW}
```

### New Learnings
I learnt how to read a file into a variable using read command and the redirect operators.

### References 
NIL