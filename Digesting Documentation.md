# Module Name: Pondering Paths

## Challenge 1: Learning from Documentation
The challenge requires you run a program with an argument.

### Solve
**Flag:** `pwn.college{wj1nMVLk_Gltvq0mpiqCwv5mcNq.QX0ITO0wSO5IzNzEzW}`

I invoked the /challenge/challenge program and gave it an argument --giveflag to make it return the flag.

```bash
hacker@man~learning-from-documentation:~$ /challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{wj1nMVLk_Gltvq0mpiqCwv5mcNq.QX0ITO0wSO5IzNzEzW}
```

### New Learnings
I learnt how to use documentation to understand arugments of a particular program.

### References 
NIL

## Challenge 2: Learning Complex Usage
The challenge requires you to give an argument for an argument of a program.

### Solve
**Flag:** `pwn.college{sx-PvI4vIRqg4yo-YTAahjQPIwd.QX1ITO0wSO5IzNzEzW}`

I was able to obtain the flag by running the program with an argument --printfile that takes a path as an argument and put the path to the /flag file. 


```bash
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{sx-PvI4vIRqg4yo-YTAahjQPIwd.QX1ITO0wSO5IzNzEzW}
```

### New Learnings
Through this challenge I learnt that an argument of a program can have its own argument.

### References 
NIL

## Challenge 3: Reading Manuals
The challenge requires you to use the man command and find the right argument to obtain flag.

### Solve
**Flag:** `pwn.college{8gI-Ulm6wzws47s6P_GknqCvCSq.QX0EDO0wSO5IzNzEzW}`

First, I ran the man challenge command to give me the documentation of the challenge program. On reading it, I understood that I need to pass an argument --glmwzw which has an argument 864. Executing this command gave me the flag.


```bash
hacker@paths~position-thy-self:~$ man challenge
CHALLENGE(1)                                 Challenge Commands                                CHALLENGE(1)

NAME
       /challenge/challenge - print the flag!

SYNOPSIS
       challenge OPTION

DESCRIPTION
       Output the flag when called with the right arguments.

       --fortune
              read a fortune

       --version
              output version information and exit

       --glmwzw NUM
              print the flag if NUM is 864

AUTHOR
       Written by Zardus.

REPORTING BUGS
       The repository for this dojo: <https://github.com/pwncollege/linux-luminarium/>
 Manual page challenge(1) line 1 (press h for help or q to quit)
hacker@man~reading-manuals:~$ /challenge/challenge --glmwzw 864
Correct usage! Your flag: pwn.college{8gI-Ulm6wzws47s6P_GknqCvCSq.QX0EDO0wSO5IzNzEzW}
```

### New Learnings
I learned how to access and utilise the man command to understand the working of each command/program.

### References 
NIL

## Challenge 4: Searching Manuals
The challenge requires you to search the manual and find which argument gives you the flag.

### Solve
**Flag:** `pwn.college{cAOMVYFC8mqEdKgi70NjLJv6MG_.QX1EDO0wSO5IzNzEzW}`

First I ran the man command which gave me a long list of commands that weren't the correct usage. But using the / I was able to search for /flag and found the correct argument to use. On running that command, I was able to get the flag.

```bash
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$
hacker@man~searching-manuals:~$ /challenge/challenge --jfvnl
Initializing...
Correct usage! Your flag: pwn.college{cAOMVYFC8mqEdKgi70NjLJv6MG_.QX1EDO0wSO5IzNzEzW}
```

### New Learnings
I learnt that you can move through man pages using up/down arrow keys and search through them using / and ? and n and N to move to next and previous searches. 

### References 
NIL

## Challenge 5: Searching For Manuals
The challenge requires you to figure out the right argument which can be found only through the man page.

### Solve
**Flag:** `pwn.college{oRSvxCrEp16b3-QmV5Vr0o4Y6vF.QX2EDO0wSO5IzNzEzW}`

First, I ran the man man command which showed the manual page for the man command. By reading through it, I found a command that searches the decriptions for keywords. Using this clue, I executed the man -k /challenge/challenge command which gave me a randomized name. Then, I searched for the manual page of this randomized name and got the correct usage to obtain the key.

```bash
hacker@paths~position-yet-elsewhere:~$ man man
hacker@man~searching-for-manuals:~$ man -k /challenge/challenge
ovxrpbmrov (1)       - print the flag!
hacker@man~searching-for-manuals:~$ man ovxrpbmrov
hacker@man~searching-for-manuals:~$ /challenge/challenge --ovxrpb 163
Correct usage! Your flag: pwn.college{oRSvxCrEp16b3-QmV5Vr0o4Y6vF.QX2EDO0wSO5IzNzEzW}
```

### New Learnings
I learnt that there is a manual page for the man command in which it is specified all the possible arugments and options usable with man command.

### References 
NIL

## Challenge 6: Helpful Programs
The challenge requires you to find the correct argument using the --help command.

### Solve
**Flag:** `pwn.college{4vAmKV119w7Or92A7AuGNrw9pHN.QX3IDO0wSO5IzNzEzW}`

First I ran the /challenge/challenge --help command which showed me the argument to print the secret number. Then I used the /challenge/challenge command with the -g argument and the secret number.

```bash
hacker@man~helpful-programs:~$ /challenge/challenge --help
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give you the flag
hacker@man~helpful-programs:~$ /challenge/challenge -p
The secret value is: 411
hacker@man~helpful-programs:~$ /challenge/challenge -g 411
Correct usage! Your flag: pwn.college{4vAmKV119w7Or92A7AuGNrw9pHN.QX3IDO0wSO5IzNzEzW}
```

### New Learnings
I learnt that some programs don't have a man page and might give you clues using the help command.

### References 
NIL

## Challenge 7: Help for Builtins
In this challenge, the challenge command is a shell builtin and requires a particular argument to give the flag. 

### Solve
**Flag:** `pwn.college{U014zYdmrEaLKIkkk7-3xDtXXNM.QX0ETO0wSO5IzNzEzW}`

First I used the help command with the command name as its argument. Then I was able to get details on how to use the challenge command which easily led me to the flag.

```bash
hacker@man~help-for-builtins:~$ help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!

    Options:
      --fortune         display a fortune
      --version         display the version
      --secret VALUE    prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "U014zYdm".
hacker@man~help-for-builtins:~$ challenge --secret U014zYdm
Correct! Here is your flag!
pwn.college{U014zYdmrEaLKIkkk7-3xDtXXNM.QX0ETO0wSO5IzNzEzW}

```

### New Learnings
I learnt that you can search specific commands using the help command which will give you important info on that particular command.

### References 
NIL
