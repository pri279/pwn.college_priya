# Module Name: Hello Hackers

## Challenge 1: Intro to Commands
learned about commands like whoami,hello

### Solve
**Flag:** `pwn.college{wSk1EB2t8V1oG9RuSDAv2iSZiNL.QX3YjM1wSO5IzNzEzW}`

i ran the command "hello" after linking the ssh key and got the flag immediately.

```bash
ssh hacker@dojo.pwn.college
hello
Success! Here is your flag:
pwn.college{wSk1EB2t8V1oG9RuSDAv2iSZiNL.QX3YjM1wSO5IzNzEzW}
```

### New Learnings
Understood commands like hello (which gave me the flag) and whoami(which prints the username)

### References 
NIL

## Challenge 2: Intro to Arguments
intro to arguments for a command like echo hello or hello hackers

### Solve
**Flag:** `pwn.college{wSk1EB2t8V1oG9RuSDAv2iSZiNL.QX3YjM1wSO5IzNzEzW}`

ran "hello hackers" in the kernel and got the flag immediately.


```bash
ssh hacker@dojo.pwn.college
hello hackers
Success! Here is your flag:
pwn.college{wSk1EB2t8V1oG9RuSDAv2iSZiNL.QX3YjM1wSO5IzNzEzW}
```

### New Learnings
Learned that commands can take arguments like "hello hackers" where hello was the command and hackers was the arguemnt passed. Also a new command echo which basically returns whatever argument you give.

### References 
NIL

## Challenge 3: Command History
learned how to access history of commands 

### Solve
**Flag:** `pwn.college{siOsxZvi9vOBqG2Yu3ebgOBVavv.0lNzEzNxwSO5IzNzEzW}`

by pressing the up arrow, i was able to go thru the history of commands and got the flag immediately.


```bash
ssh hacker@dojo.pwn.college
hacker@hello~command-history:~$ the flag is pwn.college{siOsxZvi9vOBqG2Yu3ebgOBVavv.0lNzEzNxwSO5IzNzEzW}
```

### New Learnings
Learned a very useful tool (command history) which can be iterated thru using the up and down arrow keys. this helps us save time rather than re typing previous commands 

### References 
NIL

