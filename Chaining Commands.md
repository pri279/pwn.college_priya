# Module Name: Chaining Commands

## Challenge 1: Chaining With Semicolons
The challenge requires you to use semicolon to chain two commands

### Solve
**Flag:** `pwn.college{QO2c9IIBiIoTUQ8aNfEQQL8uTnJ.QX1UDO0wSO5IzNzEzW}`

By invoking the /challenge/pwn chained with /challenge/college, I was able to obtain the flag.

```bash
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn ; /challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{QO2c9IIBiIoTUQ8aNfEQQL8uTnJ.QX1UDO0wSO5IzNzEzW}
```

### New Learnings
I learnt that you can use ; to chain two commands together.

### References 
NIL

## Challenge 2: Building On Success
The challenge requires you to use && operator to chain two commands.

### Solve
**Flag:** `pwn.college{4NC568GIkXouDpK1XYTxNwPVD01.0lM0MDOxwSO5IzNzEzW}`

I chained the two programs using && operator which gave me the flag.


```bash
hacker@chaining~building-on-success:~$ /challenge/first-success && /challenge/second
Nice chaining! Flag: pwn.college{4NC568GIkXouDpK1XYTxNwPVD01.0lM0MDOxwSO5IzNzEzW}
```

### New Learnings
Through this challenge, I learned that you can use AND operator if you want one command to work based on the exit code of the previous.

### References 
NIL

## Challenge 3: Handling Failure
This challenge requires you to use || operator to chain commands.

### Solve
**Flag:** `pwn.college{Awy-9vB-ML_Us7SZQvzRCUWjuX3.01M0MDOxwSO5IzNzEzW}`

I chained the two programs using || operator which gave me the flag.

```bash
hacker@chaining~handling-failure:~$ /challenge/first-failure || /challenge/second
Nice chaining! Flag: pwn.college{Awy-9vB-ML_Us7SZQvzRCUWjuX3.01M0MDOxwSO5IzNzEzW}
```

### New Learnings
I learned that you can use OR operator if you want one command to work based on the exit code of the previous.

### References 
NIL

## Challenge 4: Your First Shell Script
The challenge requires you to write a basic shell script.

### Solve
**Flag:** `pwn.college{U84ksE2-ljT8jNe-o003_36Ezuf.QXxcDO0wSO5IzNzEzW}`

In this challenge, I used the normal text editor to create a shell script file called x.sh and on executing it, I was able to obtain the flag.

```bash
hacker@chaining~your-first-shell-script:~/Desktop$ bash x.sh
Great job, you've written your first shell script! Here is the flag:
pwn.college{U84ksE2-ljT8jNe-o003_36Ezuf.QXxcDO0wSO5IzNzEzW}

```

### New Learnings
I learnt how to write a very basic shell script.

### References 
NIL

## Challenge 5: Redirecting Script Output
The challenge requires you write a shell script and redirect its output to a program.

### Solve
**Flag:** `pwn.college{MFLcLG08RTKI5OMjpwiwoJx5hfD.QX4ETO0wSO5IzNzEzW}`

In this challenge, I used the normal text editor to create a shell script file called y.sh and on redirecting it's output to /challenge/solve, I was able to obtain the flag.

```bash
hacker@chaining~redirecting-script-output:~/Desktop$ bash y.sh | /challenge/solve
Correct! Here is your flag:
pwn.college{MFLcLG08RTKI5OMjpwiwoJx5hfD.QX4ETO0wSO5IzNzEzW}
```

### New Learnings
I learnt how to use output redirection with shell script files. 

### References 
NIL

## Challenge 6: Executable Shell Scripts
The challenge requires you to make a shell script executable.

### Solve
**Flag:** `pwn.college{c3Cp09Xx5Isp176IqNtQVtAMk3l.QX0cjM1wSO5IzNzEzW}`

First I made a shell script file called x.sh and gave it pemissions to be executable. On invoking the command, I was able to obtain the flag.

```bash
hacker@chaining~executable-shell-scripts:~$ chmod u+x ~/x.sh
hacker@chaining~executable-shell-scripts:~$ /home/hacker/x.sh 
Congratulations on your shell script execution! Your flag:
pwn.college{c3Cp09Xx5Isp176IqNtQVtAMk3l.QX0cjM1wSO5IzNzEzW}

```

### New Learnings
I learnt how to make a shell script file executable.

### References 
NIL

## Challenge 7: Understanding Shebangs
The challenge requires you to use the shebangs to run a file.

### Solve
**Flag:** `pwn.college{I1oO2WFE7D5hMHvcT4mcFQBIUI9.0VOzMDOxwSO5IzNzEzW}`

I created a script file solve.sh containing :
```bash
#!/bin/bash
echo hack the planet
```
and after saving it as /home/hacker/solve.sh and changing it's permissions to executable. I ran /challenge/run and was able to obtain the output.

```bash
hacker@chaining~understanding-shebangs:~$ chmod +x ~/solve.sh
hacker@chaining~understanding-shebangs:~$ /challenge/run
Testing your script...
Perfect! Your flag:
Flag: pwn.college{I1oO2WFE7D5hMHvcT4mcFQBIUI9.0VOzMDOxwSO5IzNzEzW}

```

### New Learnings
I learnt how to use shebangs in the start of a file to run it.

### References 
NIL

## Challenge 8: Scripting with Arguments
The challenge requires you create a script file that takes arguments.

### Solve
**Flag:** `pwn.college{kqurDGViHFyR2DljC9IUDsfHU2g.0VNzMDOxwSO5IzNzEzW}`

First I wrote into the x.sh file, a script program to take arguments and return them in reverse order:
```bash
#!/bin/bash
echo $2 $1
```
Then I changed it's permission and on running /challenge/run, I was able to obtain the flag.

```bash
hacker@chaining~scripting-with-arguments:~$ chmod +x ~/solve.sh
hacker@chaining~scripting-with-arguments:~$ /challenge/run
Correct! Your script properly reversed the arguments.
Here's your flag:
pwn.college{kqurDGViHFyR2DljC9IUDsfHU2g.0VNzMDOxwSO5IzNzEzW}
```

### New Learnings
I learnt that you can use $1 $2 $3 etc... to take arguments in script files.

### References 
NIL

## Challenge 9: Scripting with Conditionals
This challenge requires you to create script files having conditional statements.

### Solve
**Flag:** `pwn.college{kBMtCM2_IOa6Qg7Qt4JfWmu12GW.0lNzMDOxwSO5IzNzEzW}`

First, I wrote the code into the solve.sh file so that if input is "pwn", it's output would be "college": 

```bash
#!/bin/bash
if [ "$1"  == "pwn" ]
then
	echo college
fi
```
Then, on changing the file's permissions, I was able to obtain the flag by invoking the program /challenge/run.

```bash
hacker@chaining~scripting-with-conditionals:~$ chmod +x ~/solve.sh
hacker@chaining~scripting-with-conditionals:~$ /challenge/run
Correct! Your script properly handles all the conditions.
Here's your flag:
pwn.college{kBMtCM2_IOa6Qg7Qt4JfWmu12GW.0lNzMDOxwSO5IzNzEzW}

```

### New Learnings
I learnt how to write conditional statements using if.

### References 
NIL

## Challenge 10: Scripting with Default Cases
This challenge requires you to create script files with more conditionals.

### Solve
**Flag:** `pwn.college{QI_Ir8s1bjI7JuBbBydvfhgALvZ.01NzMDOxwSO5IzNzEzW}`

First, I wrote the code into the solve.sh file so that if input is "pwn", it's output would be "college" otherwise it would return "nope" : 

```bash
#!/bin/bash
if [ "$1"  == "pwn" ]
then
	echo college
else
    echo nope
fi
```
Then, on changing the file's permissions, I was able to obtain the flag by invoking the program /challenge/run.

```bash
hacker@chaining~scripting-with-default-cases:~$ chmod +x ~/solve.sh
hacker@chaining~scripting-with-default-cases:~$ /challenge/run
Correct! Your script properly handles the if/else conditions.
Here's your flag:
pwn.college{QI_Ir8s1bjI7JuBbBydvfhgALvZ.01NzMDOxwSO5IzNzEzW}

```

### New Learnings
I learnt how to write conditional statements using if and else.

### References 
NIL

## Challenge 11: Scripting with Multiple Conditions
This challenge requires you to create script files with more conditionals.

### Solve
**Flag:** `pwn.college{UkGZEEkWiiXlE9C6Ux0WxTX_vc3.0FOzMDOxwSO5IzNzEzW}`

First, I wrote the code into the solve.sh file for a few more conditionals for input and output: 

```bash
#!/bin/bash
if [ "$1"  == "hack" ]
then
	echo "the planet"
elif [ "$1" == "pwn" ]
then
	echo "college"
elif [ $1 == "learn" ]
then
	echo  "linux"
else
	echo "unknown"
fi
```
Then, on changing the file's permissions, I was able to obtain the flag by invoking the program /challenge/run.

```bash
hacker@chaining~scripting-with-multiple-conditions:~$ chmod +x ~/solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ /challenge/run
Correct! Your script properly handles all the conditions with elif.
Here's your flag:
pwn.college{UkGZEEkWiiXlE9C6Ux0WxTX_vc3.0FOzMDOxwSO5IzNzEzW}

```

### New Learnings
I learnt how to write conditional statements using if and else.

### References 
NIL

## Challenge 12: Reading Shell Scripts
This challenge requires you to read shell script to find the correct argument.

### Solve
**Flag:** `pwn.college{k_kL0vOuqrLYjWl-OXOsbnPcHfk.0lMwgDOxwSO5IzNzEzW}`

First, I used cat command to read the shell script of /challenge/run program through which I figured out the argument required. On inputting that string, I was able to obtain the flag.

```bash
hacker@chaining~reading-shell-scripts:~$ /challenge/run

Read the /challenge/run file to figure out the correct password!
hacker@chaining~reading-shell-scripts:~$ cat /challenge/run
#!/opt/pwn.college/bash

read GUESS
if [ "$GUESS" == "hack the PLANET" ]
then
        echo "CORRECT! Your flag:"
        cat /flag
else
        echo "Read the /challenge/run file to figure out the correct password!"
fi
hacker@chaining~reading-shell-scripts:~$ /challenge/run
hack the PLANET
CORRECT! Your flag:
pwn.college{k_kL0vOuqrLYjWl-OXOsbnPcHfk.0lMwgDOxwSO5IzNzEzW}

```

### New Learnings
I learnt how to read shell script of various programs to understand their working.

### References 
NIL