# Module Name: Terminal Multiplexing

## Challenge 1: Launching Screen
The challenge requires you to use screen command to open a screen in your terminal.

### Solve
**Flag:** `pwn.college{oFdmgNanG0X0lYzmb_lqkWboIFI.0VN4IDOxwSO5IzNzEzW}`

On using screen command and launching a screen, I was able to obtain the flag.

```bash
hacker@terminal-multiplexing~launching-screen:~$ screen

Congratulations! You're inside a screen session!
Here's your flag:
pwn.college{oFdmgNanG0X0lYzmb_lqkWboIFI.0VN4IDOxwSO5IzNzEzW}
hacker@terminal-multiplexing~launching-screen:~$

```

### New Learnings
I learnt how to use screen command.

### References 
NIL

## Challenge 2: Detaching and Attaching
The challenge requires you to launch a screen and then detach it.

### Solve
**Flag:** `pwn.college{oyGokmEbj2KjLEsmHcLBALe9gk1.0lN4IDOxwSO5IzNzEzW}`

First I used the screen command to launch a screen and then detached from it using Ctrl+A followed by d. Then I invoked the /challenge/run program and then reattached it which gave me the flag.


```bash
hacker@terminal-multiplexing~detaching-and-attaching:~$ screen
[detached from 139.pts-0.terminal-multiplexing~detaching-and-attaching]
hacker@terminal-multiplexing~detaching-and-attaching:~$ /challenge/run
Found detached screen session: 139.pts-0.terminal-multiplexing~detaching-and-attaching
Sending flag to your screen session...

Flag sent! Now reattach to your screen session with:

  screen -r

You'll find the flag waiting for you there!
hacker@terminal-multiplexing~detaching-and-attaching:~$ screen -r
hacker@terminal-multiplexing~detaching-and-attaching:~$ echo Yes! Flag is: pwn.college{oyGokmEbj2KjLEsmHcLBALe9gk1.0lN4IDOxwSO5IzNzEzW}
Yes! Flag is: pwn.college{oyGokmEbj2KjLEsmHcLBALe9gk1.0lN4IDOxwSO5IzNzEzW}
hacker@terminal-multiplexing~detaching-and-attaching:~$
[screen is terminating]
hacker@terminal-multiplexing~detaching-and-attaching:~$
```

### New Learnings
Through this challenge I learnt how to detach and reattach a screen.

### References 
NIL

## Challenge 3: Finding Sessions
This challenge requires you to check various screens to find the one containing the flag.

### Solve
**Flag:** `pwn.college{YjEfrQpoSy4tarnIWOrRsvTm1Ak.01N4IDOxwSO5IzNzEzW}`

First I checked the first screen using screen -r and it's name but did not find the flag there. But when I went to the next one, I was able to obtain the flag.


```bash
hacker@terminal-multiplexing~finding-sessions:~$ screen -ls
There are screens on:
        145.session_84eb094c0e1b1ea3    (Detached)
        148.session_a57055b5ea13428a    (Detached)
        151.session_722a177474e279e5    (Detached)
3 Sockets in /home/hacker/.screen.
hacker@terminal-multiplexing~finding-sessions:~$ screen -r session_84eb094c0e1b1ea3

hacker@terminal-multiplexing~finding-sessions:~$  echo 'Nothing here! Try another session.'
Nothing here! Try another session.
hacker@terminal-multiplexing~finding-sessions:~$

[detached from 145.session_84eb094c0e1b1ea3]
hacker@terminal-multiplexing~finding-sessions:~$ screen -r session_a57055b5ea13428a

hacker@terminal-multiplexing~finding-sessions:~$  echo 'Congratulations! You found the right session!'
Congratulations! You found the right session!
hacker@terminal-multiplexing~finding-sessions:~$  echo pwn.college{YjEfrQpoSy4tarnIWOrRsvTm1Ak.01N4IDOxwSO5IzNzEzW}
pwn.college{YjEfrQpoSy4tarnIWOrRsvTm1Ak.01N4IDOxwSO5IzNzEzW}
hacker@terminal-multiplexing~finding-sessions:~$
[detached from 148.session_a57055b5ea13428a]
hacker@terminal-multiplexing~finding-sessions:~$
```

### New Learnings
I learned how to view the various deattached screens and how to reattach to them.

### References 
NIL

## Challenge 4: Switching Windows
The challenge requires you to switch between screens to find the flag.

### Solve
**Flag:** `pwn.college{Q4iNAPgoYxovwjx6-zzQ3MQGq0k.0FO4IDOxwSO5IzNzEzW}`

First I listed out the current screens using screen -ls and reattached the challenge_session screen. On doing so, I got to window 1 and was instructed to switch to window 0 to obtain the flag.

```bash
hacker@terminal-multiplexing~switching-windows:~$ screen -ls
There are screens on:
        148.session_a57055b5ea13428a    (Remote or dead)
        151.session_722a177474e279e5    (Remote or dead)
        135.challenge_session   (Detached)
3 Sockets in /home/hacker/.screen.
hacker@terminal-multiplexing~switching-windows:~$ screen -r challenge_session
 cat <<MSG
Welcome to the window switching challenge!
You are currently in window 1.
The flag is hidden in window 0.
Use Ctrl-A 0 to switch to window 0!
MSG
hacker@terminal-multiplexing~switching-windows:~$  cat <<MSG
> Welcome to the window switching challenge!
> You are currently in window 1.
> The flag is hidden in window 0.
> Use Ctrl-A 0 to switch to window 0!
> MSG
Welcome to the window switching challenge!
You are currently in window 1.
The flag is hidden in window 0.
Use Ctrl-A 0 to switch to window 0!
hacker@terminal-multiplexing~switching-windows:~$

hacker@terminal-multiplexing~switching-windows:~$  cat <<MSG
> Excellent work! You found window 0!
> Here is your flag: pwn.college{Q4iNAPgoYxovwjx6-zzQ3MQGq0k.0FO4IDOxwSO5IzNzEzW}
> MSG
Excellent work! You found window 0!
Here is your flag: pwn.college{Q4iNAPgoYxovwjx6-zzQ3MQGq0k.0FO4IDOxwSO5IzNzEzW}
hacker@terminal-multiplexing~switching-windows:~$
```

### New Learnings
I learnt how to switch windows within a screen.

### References 
NIL

## Challenge 5: Detaching and Attaching (tmux)
The challenge requires you to detach and reattach using tmux instead of screen.

### Solve
**Flag:** `pwn.college{YCbXYSlKeujtqeJUT6Gcbi5Y9sN.0VO4IDOxwSO5IzNzEzW}`

First, I used tmux command and then detached from it. Then, I invoked /challenge/run to send the flag to the tmux session. On reattaching, I was able to obtain the flag. 

```bash
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ tmux
[detached (from session 0)]
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ /challenge/run
Found detached tmux session: 0
Sending flag to your tmux session...

Flag sent! Now reattach to your tmux session with:
  tmux attach

You'll find the flag waiting for you there!
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ tmux a
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$  echo Congratulations, here is your flag: pwn.college{YCbXYSlKeujtqeJUT6Gcbi5Y9sN.0VO4IDOxwSO5IzNzEzW}
Congratulations, here is your flag: pwn.college{YCbXYSlKeujtqeJUT6Gcbi5Y9sN.0VO4IDOxwSO5IzNzEzW}
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$
[detached (from session 0)]
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$
```

### New Learnings
I learnt how to use tmux instead of screen commands.

### References 
NIL

## Challenge 6: Switching Windows (tmux)
The challenge requires you to sort contents of a file in alphabetical order.

### Solve
**Flag:** `pwn.college{UP5ppTPDxDeadsht64toVk9n6tO.0FM5IDOxwSO5IzNzEzW}`

I opened tmux and switched to window 0 which was said to contain the flag. On doing so, I was able to obtain the flag.

```bash
hacker@terminal-multiplexing~switching-windows-tmux:~$ tmux
hacker@terminal-multiplexing~switching-windows-tmux:~$  cat <<MSG
> Excellent work! You found window 0!
> Here is your flag: pwn.college{UP5ppTPDxDeadsht64toVk9n6tO.0FM5IDOxwSO5IzNzEzW}
> MSG
Excellent work! You found window 0!
Here is your flag: pwn.college{UP5ppTPDxDeadsht64toVk9n6tO.0FM5IDOxwSO5IzNzEzW}
hacker@terminal-multiplexing~switching-windows-tmux:~$
[exited]
hacker@terminal-multiplexing~switching-windows-tmux:~$
```

### New Learnings
I learnt how to switch between windows on tmux.

### References 
NIL
