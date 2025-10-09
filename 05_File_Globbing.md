# Module Name: File Globbing

## Challenge 1: Matching with *
The challenge requires you change to another directory using file globbing with * character.

### Solve
**Flag:** `pwn.college{ANSjOlxsJSLNoDGmYkIH2FlDwcU.QXxIDO0wSO5IzNzEzW}`

I used the file globbing techniques since the terminal would only allow 4 characters with the cd command. I was able to obtain the flag by running /challenge/run after changing directories.

```bash
hacker@globbing~matching-with-:~$ cd /c*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{ANSjOlxsJSLNoDGmYkIH2FlDwcU.QXxIDO0wSO5IzNzEzW}
```

### New Learnings
I learnt how to use * character in file paths to match a pattern that we input. 

### References 
NIL

## Challenge 2: Matching with ?
The challenge requires you change to another directory using file globbing with * character.

### Solve
**Flag:** `pwn.college{MaJuccxnfP1v94nRuQdhNxFbxZm.QXyIDO0wSO5IzNzEzW}`

I was able to obtain the flag by using the file globbing technique with the ? character and switched to the right directory to invoke the program.


```bash
This challenge resets your working directory to /home/hacker unless you change
directory properly...
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{MaJuccxnfP1v94nRuQdhNxFbxZm.QXyIDO0wSO5IzNzEzW}
```

### New Learnings
I learnt how to use ? character in a file path to match a single character in the original filename.

### References 
NIL

## Challenge 3: Matching with []
The challenge requires you change to another directory using file globbing using [].

### Solve
**Flag:** `pwn.college{stc3TnFhu3-WAfuiMdjj9UAEatG.QXzIDO0wSO5IzNzEzW}`

First, I changed directories and then using the [] operator I gave a subset of potential characters as an argument. On doing so, I was able to retrieve the flag.


```bash
hacker@globbing~matching-with-:~$ cd /challenge/files
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[bash]
You got it! Here is your flag!
pwn.college{stc3TnFhu3-WAfuiMdjj9UAEatG.QXzIDO0wSO5IzNzEzW}
```

### New Learnings
I learned how to use the [] operator as part of file globbing techniques.

### References 
NIL

## Challenge 4: Matching paths with [] 
The challenge requires you change to another directory using file globbing using [] but with its absolute path.

### Solve
**Flag:** `pwn.college{g2ODSEjoYUtN9ICFnr5sgPSqXwe.QX0IDO0wSO5IzNzEzW}`

In one step, I invoked the /challenge/run program with the argument being the absolute path of the required files. Doing so instantly gave me the flag.

```bash
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[bash]
You got it! Here is your flag!
pwn.college{g2ODSEjoYUtN9ICFnr5sgPSqXwe.QX0IDO0wSO5IzNzEzW}
```

### New Learnings
I learned how to use the [] operator with absolute paths of various files.

### References 
NIL

## Challenge 5: Multiple Globs
The challenge requires you to use multiple * characters to obtain the flag.

### Solve
**Flag:** `pwn.college{kn1n35rAHyFBZwEApYrjILmI9jG.0lM3kjNxwSO5IzNzEzW}`

First, I changed directories to /challenge/files and since the hint was that the correct argument contained the letter p and had to be not more than 3 characters, I was able to use * p * to signify that it could start/end with anything but must include p.

```bash
hacker@globbing~multiple-globs:~$ cd /challenge/files
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run *p*
You got it! Here is your flag!
pwn.college{kn1n35rAHyFBZwEApYrjILmI9jG.0lM3kjNxwSO5IzNzEzW}
```

### New Learnings
I learnt that you can use multiple globs in a single command and how * is used in such a way.

### References 
NIL

## Challenge 6: Mixing Globs
The challenge requires you to mix and use various glob methods to find the correct argument.

### Solve
**Flag:** `pwn.college{4wEyjP0BhizbWPIoqEOx1w4Hbq2.QX1IDO0wSO5IzNzEzW}`

First I changed to the /challenge/files directory and since the words educational,challenging and pwning begin with ecp and end with various letters, I used [ecp]* as an argument to obtain the flag.

```bash
hacker@globbing~multiple-globs:~$ cd /challenge/files
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [ecp]*
You got it! Here is your flag!
pwn.college{4wEyjP0BhizbWPIoqEOx1w4Hbq2.QX1IDO0wSO5IzNzEzW}
```

### New Learnings
I learnt the different ways you can mix and use the file globbing characters when you have particular constraints.

### References 
NIL

## Challenge 7: Exclusionary Globbing
This challenge requires you to use the exclusionary globbing method to get all files except ones starting with p, w or n.

### Solve
**Flag:** `pwn.college{IXphel208LE6QoB0PGc_nt3LIAi.QX2IDO0wSO5IzNzEzW}`

First I used the cd command to change directories to /challenge/files. Then using the ^ globbing technique, I was able to get arguments as files that do not start with p,w or n and hence obtained the flag.

```bash
hacker@globbing~multiple-globs:~$ cd /challenge/files
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [^pwn]*
You got it! Here is your flag!
pwn.college{IXphel208LE6QoB0PGc_nt3LIAi.QX2IDO0wSO5IzNzEzW}
```

### New Learnings
I learnt a new method where you can exclude a subset of characters from the argument you require.

### References 
NIL

## Challenge 8: Tab Completion
The challenge requires you to compelete the command using the TAB completion to obtain the flag.

### Solve
**Flag:** `pwn.college{cEuEVwtOkUR-7tibdfympLASfTR.0FN0EzNxwSO5IzNzEzW}`

First, I listed out the programs and folders in /challenge and tried to cat /challenge/pwncollege which was said to be containing the file. But only when I used tab completion was I able to obtain the flag.

```bash
hacker@globbing~tab-completion:~$ ls /challenge
DESCRIPTION.md  pwncollege​
hacker@globbing~tab-completion:~$ cat /challenge/pwncollege
cat: /challenge/pwncollege: No such file or directory
hacker@globbing~tab-completion:~$ cat /challenge/pwncollege​
pwn.college{cEuEVwtOkUR-7tibdfympLASfTR.0FN0EzNxwSO5IzNzEzW}
```

### New Learnings
I learnt that you can auto-complete commands using tab completion.

### References 
NIL

## Challenge 9: Multiple Options for Tab Completion
The challenge requires you to use tab completion to identify the flag file without using ls commands.

### Solve
**Flag:** `pwn.college{MgOoqx3rtQlglMhMHnZjtc4NwEb.0lN0EzNxwSO5IzNzEzW}`

I used the cat command to read the contents of /challenge/run/p and used TAB key from then on. This gave me a list of options and since it begins with pwncollege, I was able to obtain the flag in that manner.

```bash
hacker@globbing~multiple-options-for-tab-completion:~$ cat /challenge/files/pwn
pwn                    pwn-the-planet         pwncollege-flag        pwncollege-flyswatter
pwn-college            pwncollege-family      pwncollege-flamingo    pwncollege-hacking
hacker@globbing~multiple-options-for-tab-completion:~$ cat /challenge/files/pwncollege-flag
pwn.college{MgOoqx3rtQlglMhMHnZjtc4NwEb.0lN0EzNxwSO5IzNzEzW}
```

### New Learnings
I learnt how to use tab completion with various commands like cat command.

### References 
NIL

## Challenge 10: Tab Completions on Commands
In this challenge, you must use the TAB completetion feature to complete the command and obtain the flag.

### Solve
**Flag:** `pwn.college{Y8wsLfdX0zoFaOhIIPnYjZ8R1G8.0VN0EzNxwSO5IzNzEzW}`

I typed pwncollege since the decription hinted that the command beings with pwncollege and by hitting TAB key, I was able to get the flag instantly as it auto-completed the rest of the command.

```bash
hacker@globbing~tab-completion-on-commands:~$ pwncollege-13674
Correct! Here is your flag:
pwn.college{Y8wsLfdX0zoFaOhIIPnYjZ8R1G8.0VN0EzNxwSO5IzNzEzW}
```

### New Learnings
I learnt that you can also auto-complete commands using TAB completion but this must be used with caution and should be double-checked before executing.

### References 
NIL
