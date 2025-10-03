# Module Name: Processes and Jobs

## Challenge 1: Listing Processes
The challenge requires you to use the ps command to list out all the current processes.

### Solve
**Flag:** `pwn.college{kwCsJ6yykYu2J8wUrJ7giP3cl0t.QX4MDO0wSO5IzNzEzW}`

I used the ps aux command to list out the current processes since the description hinted that the correct program was already running. By invoking the program, I was able to obtain the flag.

```bash
hacker@processes~listing-processes:~$ ps aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.0  0.0   1056   640 ?        Ss   14:04   0:00 /sbin/docker-init -- /nix/var/nix/profiles/
root           7  0.0  0.0 231708  2560 ?        S    14:04   0:00 /run/dojo/bin/sleep 6h
root         132  0.0  0.0   4132  2560 ?        S    14:04   0:00 /challenge/10040-run-26512
root         135  0.0  0.0   2744  1280 ?        S    14:04   0:00 sleep 6h
hacker       137  0.0  0.0 231576  3520 pts/0    Ss   14:04   0:00 /nix/store/0nxvi9r5ymdlr2p24rjj9qzyms72zld1
hacker       143  0.0  0.0 231940  4160 pts/0    S    14:04   0:00 /run/dojo/bin/bash --login
root         153  0.0  0.0 231576  3520 pts/0    S+   14:05   0:00 /challenge/10040-run-26512
root         155  0.0  0.0 231708  2560 pts/0    S+   14:05   0:00 sleep 6h
hacker       156  0.8  0.0 231576  3520 pts/1    Ss   14:05   0:00 /nix/store/0nxvi9r5ymdlr2p24rjj9qzyms72zld1
hacker       162  0.0  0.0 231940  4160 pts/1    S    14:05   0:00 /run/dojo/bin/bash --login
hacker       171  0.0  0.0 233600  3840 pts/1    R+   14:05   0:00 ps aux
hacker@processes~listing-processes:~$ /challenge/10040-run-26512
Yahaha, you found me! Here is your flag:
pwn.college{kwCsJ6yykYu2J8wUrJ7giP3cl0t.QX4MDO0wSO5IzNzEzW}
Now I will sleep for a while (so that you could find me with 'ps').
```

### New Learnings
I learnt how to use ps command to view current running processes.

### References 
NIL

## Challenge 2: Killing Processes
The challenge requires you to terminate a process to obtain the flag.

### Solve
**Flag:** `pwn.college{o0itL_W6wQUp1DItLPpfCqErw3O.QXyQDO0wSO5IzNzEzW}`

First, I found the /challenge/dont_run command to get it's PID and then I passed it as an argument to the kill command and sucessfully terminated it. Now, when I invoked the /challenge/run command, I was able to obtain the flag.


```bash
hacker@processes~killing-processes:~$ ps -ef | grep /challenge/dont_run
hacker       136     135  0 14:10 ?        00:00:00 /challenge/dont_run
hacker       188     178  0 14:13 pts/2    00:00:00 grep --color=auto /challenge/dont_run
hacker@processes~killing-processes:~$ kill 136
hacker@processes~killing-processes:~$ /challenge/run
Great job! Here is your payment:
pwn.college{o0itL_W6wQUp1DItLPpfCqErw3O.QXyQDO0wSO5IzNzEzW}
```

### New Learnings
I learnt how to use the kill command to terminate processes with their PID as the argument.

### References 
NIL

## Challenge 3: Interrupting Processes
The challenge requires you to force-quit a process using the control code: Ctrl+C.

### Solve
**Flag:** `pwn.college{MrnelnM6uozGaeIZL1SDHmjp0xn.QXzQDO0wSO5IzNzEzW}`

First, I invoked the /challenge/run command and then to force quit it, I used Ctrl+C and was able to obtain the flag.


```bash
hacker@processes~interrupting-processes:~$ /challenge/run
I could give you the flag... but I won't, until this process exits. Remember,
you can force me to exit with Ctrl-C. Try it now!
^C
Good job! You have used Ctrl-C to interrupt this process! Here is your flag:
pwn.college{MrnelnM6uozGaeIZL1SDHmjp0xn.QXzQDO0wSO5IzNzEzW}
```

### New Learnings
I learned how to use the Ctrl+C to force-exit a program or process.

### References 
NIL

## Challenge 4: Killing Misbehaving Processes
The challenge requires you to kill the decoy process using kill command.

### Solve
**Flag:** `pwn.college{kYHvKcYb6YI99BL7nIkFYyh3zMR.0FNzMDOxwSO5IzNzEzW}`

First, I used the ps command to find the PID of the /challenge/decoy and then using kill command, terminated that process. Then on running the /challenge/run and cat command, I was able to obtain the flag.

```bash
hacker@processes~killing-misbehaving-processes:~$ ps -ef | grep /challenge/decoy
root         139       1  0 14:21 ?        00:00:00 su -c exec /challenge/decoy > /tmp/flag_fifo hacker
hacker       142     139  0 14:21 ?        00:00:00 /usr/bin/python /challenge/decoy
hacker       164     150  0 14:22 pts/0    00:00:00 grep --color=auto /challenge/decoy
hacker@processes~killing-misbehaving-processes:~$ kill 142
hacker@processes~killing-misbehaving-processes:~$ /challenge/run | cat /tmp/flag_fifo
pwn.college{kYHvKcYb6YI99BL7nIkFYyh3zMR.0FNzMDOxwSO5IzNzEzW}
```

### New Learnings
I learned how to kill processes that are obstructing the goal to obtain the flag.

### References 
NIL

## Challenge 5: Suspending Processes
The challenge requires you suspend a program and relaunch it.

### Solve
**Flag:** `pwn.college{cRb719n82fM7I61ogSuBt_kHMUY.QX1QDO0wSO5IzNzEzW}`

First, I invoked the /challenge/run program and then suspended it using Ctrl+Z and re-launched it, which gave me the flag.

```bash
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         138     129  0 14:28 pts/0    00:00:00 bash /challenge/run
root         140     138  0 14:28 pts/0    00:00:00 ps -f

I don't see a second me!

To pass this level, you need to suspend me and launch me again! You can
background me with Ctrl-Z or, if you're not ready to do that for whatever
reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         138     129  0 14:28 pts/0    00:00:00 bash /challenge/run
root         145     129  0 14:28 pts/0    00:00:00 bash /challenge/run
root         147     145  0 14:28 pts/0    00:00:00 ps -f

Yay, I found another version of me! Here is the flag:
pwn.college{cRb719n82fM7I61ogSuBt_kHMUY.QX1QDO0wSO5IzNzEzW}
```

### New Learnings
I learnt that you can suspend processes if you don't want to completely terminate them.

### References 
NIL

## Challenge 6: Resuming Processes
The challenge requires you to resume a process using fg command.

### Solve
**Flag:** `pwn.college{8Prpw6anBhgDGi-pbkEJtsOleg9.QX2QDO0wSO5IzNzEzW}`

First I ran the /challenge/run command and then suspended it using Ctrl+Z. Then to resume it, I used the fg command which gave me the flag.

```bash
hacker@processes~resuming-processes:~$ /challenge/run
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with
the 'fg' command! Or just press Enter to quit me!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~resuming-processes:~$ fg
/challenge/run
I'm back! Here's your flag:
pwn.college{8Prpw6anBhgDGi-pbkEJtsOleg9.QX2QDO0wSO5IzNzEzW}
Don't forget to press Enter to quit me!

Goodbye!
```

### New Learnings
I learnt how to resume a suspended process.

### References 
NIL

## Challenge 7: Backgrounding Processes
This challenge requires you to use the bg command to run a process in the background.

### Solve
**Flag:** `pwn.college{s53LmMayWsAJezPHE7Q130NFgnr.QX3QDO0wSO5IzNzEzW}`

First I ran the /challenge/run command and then suspended it using Ctrl+Z. Then to run it in the background, I used the bg command and invoked it once again to obtain the flag.

```bash
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         138 S+   bash /challenge/run
root         140 R+   ps -o user=UID,pid,stat,cmd

I don't see a second me!

To pass this level, you need to suspend me, resume the suspended process in the
background, and then launch a new version of me! You can background me with
Ctrl-Z (and resume me in the background with 'bg') or, if you're not ready to
do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~backgrounding-processes:~$ bg
[1]+ /challenge/run &
hacker@processes~backgrounding-processes:~$


Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out.

hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         138 S    bash /challenge/run
root         148 S    sleep 6h
root         149 S+   bash /challenge/run
root         151 R+   ps -o user=UID,pid,stat,cmd

Yay, I found another version of me running in the background! Here is the flag:
pwn.college{s53LmMayWsAJezPHE7Q130NFgnr.QX3QDO0wSO5IzNzEzW}
```

### New Learnings
I learnt how to run processes in the background.

### References 
NIL

## Challenge 8: Foregrounding Processes
The challenge requires you to bring back a backgrounded process.

### Solve
**Flag:** `pwn.college{4cygF9lpX0Spp2DVMs0OoqAWfgQ.QX4QDO0wSO5IzNzEzW}`

First, I invoked the program /challenge/run and backgrounded it. Then to bring it back, I simply used the fg command to obtain the flag.

```bash
hacker@processes~foregrounding-processes:~$ /challenge/run
To pass this level, you need to suspend me, resume the suspended process in the
background, and *then* foreground it without re-suspending it! You can
background me with Ctrl-Z (and resume me in the background with 'bg') or, if
you're not ready to do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~foregrounding-processes:~$ bg
[1]+ /challenge/run &
hacker@processes~foregrounding-processes:~$


Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out. After that, resume me into the foreground with 'fg';
I'll wait.

hacker@processes~foregrounding-processes:~$ fg
/challenge/run
YES! Great job! I'm now running in the foreground. Hit Enter for your flag!

pwn.college{4cygF9lpX0Spp2DVMs0OoqAWfgQ.QX4QDO0wSO5IzNzEzW}
```

### New Learnings
I learnt how to bring a process from background to foreground.

### References 
NIL

## Challenge 9: Starting Backgrounded Processes
The challenge requires you to background a process without suspending it first.

### Solve
**Flag:** `pwn.college{gdLWG3-aAFnVP9m2HiCYOkggMqZ.QX5QDO0wSO5IzNzEzW}`

I appended the & operator to /challenge/run to indicate that it should be run in the background and was able to obtain the flag.

```bash
hacker@processes~starting-backgrounded-processes:~$ /challenge/run &
[1] 138
hacker@processes~starting-backgrounded-processes:~$


Yay, you started me in the background! Because of that, this text will probably
overlap weirdly with the shell prompt, but you're used to that by now...

Anyways! Here is your flag!
pwn.college{gdLWG3-aAFnVP9m2HiCYOkggMqZ.QX5QDO0wSO5IzNzEzW}
^C
[1]+  Done                    /challenge/run
```

### New Learnings
I learnt how to background a process without suspending it first.

### References 
NIL

## Challenge 10: Process Exit Codes
This challenge requires you to retreive the exit code of a program and use it as an argument for another program.

### Solve
**Flag:** `pwn.college{YLn-AIRXLN914pNRokvl9P8ZT-B.QX5YDO1wSO5IzNzEzW}`

First, to obtain the exit code of the program /challenge/get code, I used the $? which would return 0 if it was sucessful and a non-zero number if it failed. On passing that number into /challenge/submit-code as an argument, I was able to obtain the flag.

```bash
hacker@processes~process-exit-codes:~$ /challenge/get-code
Exiting with an error code!
hacker@processes~process-exit-codes:~$ echo $?
104
hacker@processes~process-exit-codes:~$ /challenge/submit-code 104
CORRECT! Here is your flag:
pwn.college{YLn-AIRXLN914pNRokvl9P8ZT-B.QX5YDO1wSO5IzNzEzW}
```

### New Learnings
I learnt how to access the exit code of a program using the special ? variable.

### References 
NIL
