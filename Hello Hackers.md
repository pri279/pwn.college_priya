# Module Name: Hello Hackers

## Challenge 1: Intro to Commands
The challenege asks you to invoke multiple commands such as whoami and hello

### Solve
**Flag:** `pwn.college{wSk1EB2t8V1oG9RuSDAv2iSZiNL.QX3YjM1wSO5IzNzEzW}`

First i invoked the whoami command that displays the username to the terminal and then  ran the command hello which gave me the flag immediately.

```bash
hacker@hello~command-history:~$ ssh hacker@dojo.pwn.college
hacker@hello~command-history:~$ hello
Success! Here is your flag:
pwn.college{wSk1EB2t8V1oG9RuSDAv2iSZiNL.QX3YjM1wSO5IzNzEzW}
```

### New Learnings
I learnt about Linux commands and understood commands such as hello and whoami

### References 
NIL

## Challenge 2: Intro to Arguments
The challenge requires you to give an argument for commands like echo which just returns whatever you have inputted as an argument and hello

### Solve
**Flag:** `pwn.college{wSk1EB2t8V1oG9RuSDAv2iSZiNL.QX3YjM1wSO5IzNzEzW}`

First I ran echo Hello which printed Hello and then I ran hello hackers in the kernel and got the flag immediately.


```bash
hacker@hello~command-history:~$ echo hello
hello
hacker@hello~command-history:~$ ssh hacker@dojo.pwn.college
hacker@hello~command-history:~$ hello hackers
Success! Here is your flag:
pwn.college{wSk1EB2t8V1oG9RuSDAv2iSZiNL.QX3YjM1wSO5IzNzEzW}
```

### New Learnings
Through this challenge I learned that commands can take arguments like "hello hackers" where hello was the command and hackers was the arguemnt passed. And a new command "echo" which returns whatever argument you give it.

### References 
NIL

## Challenge 3: Command History
The challenge requires you to access the history of commands and obtain the flag from there 

### Solve
**Flag:** `pwn.college{siOsxZvi9vOBqG2Yu3ebgOBVavv.0lNzEzNxwSO5IzNzEzW}`

I was able to iterate through the history of commands using the up and down arrows and when i clicked the up arrow, i was able to get the flag immediately.


```bash
hacker@hello~command-history:~$ ssh hacker@dojo.pwn.college
hacker@hello~command-history:~$ the flag is pwn.college{siOsxZvi9vOBqG2Yu3ebgOBVavv.0lNzEzNxwSO5IzNzEzW}
```

### New Learnings
I learned a very useful tool (command history) which can be iterated through using the up and down arrow keys. This helps save time rather than re-typing previous commands. 

### References 
NIL

