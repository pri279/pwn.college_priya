# Module Name: Pondering PATH

## Challenge 1: The PATH Variable
The challenge requires you to disrupt the operations of a program by getting rid of the rm command.

### Solve
**Flag:** `pwn.college{E39nIG3Bykr_Tg7zit8diPTBUcY.QX2cDM1wSO5IzNzEzW}`

In this challenge, I was required to make sure the /challenge/run didn't delete the flag required. I did this by setting PATH variable to "" and hence obtained the flag on invoking the program.

```bash
hacker@path~the-path-variable:~$ PATH=""
hacker@path~the-path-variable:~$ /challenge/run
Trying to remove /flag...
/challenge/run: line 4: rm: No such file or directory
The flag is still there! I might as well give it to you!
pwn.college{E39nIG3Bykr_Tg7zit8diPTBUcY.QX2cDM1wSO5IzNzEzW}
hacker@path~the-path-variable:~$

```

### New Learnings
I learnt how to get rid of a command by blanking the PATH variable out.

### References 
NIL

## Challenge 2: Setting PATH
The challenge requires you to set the PATH variable to a particular location.

### Solve
**Flag:** `pwn.college{0QPq1hUJn8siqX-jS9VIj9BItbq.QX1cjM1wSO5IzNzEzW}`

Since the /challenge/run program will not run without win command, I used the PATH variable to give the location of the win command script file and on running it once more, I obtained the flag.


```bash
hacker@path~setting-path:/challenge/more_commands$ PATH="/challenge/more_commands/"
hacker@path~setting-path:/challenge/more_commands$ /challenge/run
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
pwn.college{0QPq1hUJn8siqX-jS9VIj9BItbq.QX1cjM1wSO5IzNzEzW}
hacker@path~setting-path:/challenge/more_commands$
```

### New Learnings
Through this challenge I learnt how to detach and reattach a screen.

### References 
NIL

## Challenge 3: Finding Commands
This challenge requires you to find the location of a command to find the flag file location.

### Solve
**Flag:** `pwn.college{0SvXUDPn6thF6YrkQbgyBRfw3TH.01NzEzNxwSO5IzNzEzW}`

Since the description hinted that the win command file and the flag file were in the same location, I used which command to find the location of win command and used cat command to read the flag.

```bash
hacker@path~finding-commands:~$ which win
/challenge/paths/8842/win
hacker@path~finding-commands:~$ cd /challenge/paths/8842/
hacker@path~finding-commands:/challenge/paths/8842$ ls
flag  win
hacker@path~finding-commands:/challenge/paths/8842$ cat flag
pwn.college{0SvXUDPn6thF6YrkQbgyBRfw3TH.01NzEzNxwSO5IzNzEzW}
hacker@path~finding-commands:/challenge/paths/8842$
```

### New Learnings
I learned how to use which command to find location of a command script file.

### References 
NIL

## Challenge 4: Adding Commands
The challenge requires you to create script file to make a command and execute it to obtain the flag.

### Solve
**Flag:** `pwn.college{0Efa-kAXZ56bZ45uUQEYky1owyN.QX2cjM1wSO5IzNzEzW}`

First I created a path to save the win command script file and then wrote into the file using a simple text editor, nano. Then I changed it's permissions to executable and set the PATH variable to my win command's directory. Finally, on running /challenge/run, I was able to obtain the flag.

```bash
hacker@path~adding-commands:~$ mkdir /home/hacker/script
hacker@path~adding-commands:~$ cd script
hacker@path~adding-commands:~/script$ nano win

#!/bin/bash
/run/dojo/bin/cat /flag

hacker@path~adding-commands:~/script$ chmod +x win
hacker@path~adding-commands:~/script$ PATH="/home/hacker/script"
hacker@path~adding-commands:~/script$ /challenge/run
Invoking 'win'....
pwn.college{0Efa-kAXZ56bZ45uUQEYky1owyN.QX2cjM1wSO5IzNzEzW}
hacker@path~adding-commands:~/script$
```

### New Learnings
I learnt how to add commands by writing shell scripts. 

### References 
NIL

## Challenge 5: Hijacking Commands
The challenge requires you to manipulate commands.

### Solve
**Flag:** `pwn.college{ISHooGZY6waftLRwxXUsIkmGLVA.QX3cjM1wSO5IzNzEzW}`

Since the program wouldn't directly print the flag but will delete it using rm command, I created a script file, named it rm and wrote into it such that it would print the flag when executed. Then I set the PATH variable to my desired directory where the decoy rm command is stored and was able to trick /challenge/run into giving up the flag.

```bash
hacker@path~hijacking-commands:~$ cd /home/hacker/script
hacker@path~hijacking-commands:~/script$ nano rm

#!/bin/bash
/run/dojo/bin/cat /flag

hacker@path~hijacking-commands:~/script$ chmod +x rm
hacker@path~hijacking-commands:~/script$ PATH="/home/hacker/script"
hacker@path~hijacking-commands:~/script$ /challenge/run
Trying to remove /flag...
pwn.college{ISHooGZY6waftLRwxXUsIkmGLVA.QX3cjM1wSO5IzNzEzW}
hacker@path~hijacking-commands:~$
```

### New Learnings
I learnt how to use and manipulate the PATH variable as required.

### References 
NIL
