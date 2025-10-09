# Module Name: Practicing Piping

## Challenge 1: Redirecting Output
The challenge requires you to write the PWN to a file named COLLEGE.

### Solve
**Flag:** `pwn.college{oscGPOExF5yYwEC-RJmkhrBngPj.QX0YTN0wSO5IzNzEzW}`

Using the echo command and the left caret symbol, I was able to write into the COLLEGE file and obtain the flag.

```bash
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your
flag:
pwn.college{oscGPOExF5yYwEC-RJmkhrBngPj.QX0YTN0wSO5IzNzEzW}
```

### New Learnings
I learnt that you can use > to write the output of a command into another file.

### References 
NIL

## Challenge 2: Redirecting More Output
The challenge requires you to use > to write output of a program into a file.

### Solve
**Flag:** `pwn.college{QnwYVz_qI2DKLTRpNgbb3-J5CkM.QX1YTN0wSO5IzNzEzW}`

First, I redirected the output of /challenge/run program to myflag file and then used cat command to read it and obtained the flag.


```bash
hacker@piping~redirecting-more-output:~$ /challenge/run > myflag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-more-output:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{QnwYVz_qI2DKLTRpNgbb3-J5CkM.QX1YTN0wSO5IzNzEzW}

```

### New Learnings
Through this challenge, I learned that you can write output of other programs (like /challenge/run) to files.

### References 
NIL

## Challenge 3: Appending Output
This challenge requires you to append the output into the file rather than overwriting.

### Solve
**Flag:** `pwn.college{IJrymkeBJAJ05QFgiUCztxWoVcN.QX3ATO0wSO5IzNzEzW}`

First, I redirected the output of the /challenge/run program into the-flag file which gave it the second half of the required flag. Then I used the append mode(>>) to add to the file without truncating and overwriting so that I wouldn't lose the second half and got the final complete flag.


```bash
hacker@piping~appending-output:~$ /challenge/run > ~/the-flag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] Good luck!

[TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
I will write the flag in two parts to the file /home/hacker/the-flag! I'll do
the first write directly to the file, and the second write, I'll do to stdout
(if it's pointing at the file). If you redirect the output in append mode, the
second write will append to (rather than overwrite) the first write, and you'll
get the whole flag!
hacker@piping~appending-output:~$ /challenge/run >> ~/the-flag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] Good luck!

[TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
I will write the flag in two parts to the file /home/hacker/the-flag! I'll do
the first write directly to the file, and the second write, I'll do to stdout
(if it's pointing at the file). If you redirect the output in append mode, the
second write will append to (rather than overwrite) the first write, and you'll
get the whole flag!
hacker@piping~appending-output:~$ cat  ~/the-flag
 |
\|/ This is the first half:
 v
pwn.college{IJrymkeBJAJ05QFgiUCztxWoVcN.QX3ATO0wSO5IzNzEzW}
                              ^
     that is the second half /|\
                              |

If you only see the second half above, you redirected in *truncate* mode (>)
rather than *append* mode (>>), and so the write of the second half to stdout
overwrote the initial write of the first half directly to the file. Try append
mode!

```

### New Learnings
I learned how to use the append mode so that I don't overwrite information into a file.

### References 
NIL

## Challenge 4: Redirecting Errors
The challenge requires you to redirect the output to one file and the errors to another.

### Solve
**Flag:** `pwn.college{gaQuN5VIGdqi_YtHPc7KvZzS1Av.QX3YTN0wSO5IzNzEzW}`

In this challenge, I used the file descriptors to redirect output of /challenge/run to myflag and it's errors to instructions file. On using cat command with myflag file as its argument, I was able to obtain the flag.

```bash
hacker@piping~redirecting-errors:~$ /challenge/run > myflag 2> instructions
hacker@piping~redirecting-errors:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{gaQuN5VIGdqi_YtHPc7KvZzS1Av.QX3YTN0wSO5IzNzEzW}

```

### New Learnings
I learnt that file descriptors 0,1,2 imply stdin,stdout and stderr and can be used similar to how > is used normally. 

### References 
NIL

## Challenge 5: Redirecting Input
The challenge requires you use redirect input and output to programs.

### Solve
**Flag:** `pwn.college{0Rm-pGH1UC5E_2sdC5JS_-HISo8.QXwcTN0wSO5IzNzEzW}`

First I wrote the contents of COLLEGE to PWN file and then PWN to the /challenge/run program which gave me the flag.

```bash
hacker@piping~redirecting-input:~$ echo COLLEGE > PWN
hacker@piping~redirecting-input:~$ /challenge/run < PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read
the value 'COLLEGE' out of it!
Here is your flag:
pwn.college{0Rm-pGH1UC5E_2sdC5JS_-HISo8.QXwcTN0wSO5IzNzEzW}
```

### New Learnings
I learnt how to use multiple redirects to acheive the requirement in the challenge.

### References 
NIL

## Challenge 6: Grepping Stored Results
The challenge requires you to redirect output to another file and grep the flag from that file.

### Solve
**Flag:** `pwn.college{QMP9MuFC-ddddbw9Lgz2gXcaZr8.QX4EDO0wSO5IzNzEzW}`

First I redirected the output of /challenge/run to /tmp/data.txt and then used the grep command to search for patterns similar to pwn.college. Thus, I was able to obtain the flag.

```bash
hacker@piping~grepping-stored-results:~$ /challenge/run > /tmp/data.txt
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /tmp/data.txt
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to a file called /tmp/data.txt. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~grepping-stored-results:~$ grep pwn.college /tmp/data.txt
pwn.college{QMP9MuFC-ddddbw9Lgz2gXcaZr8.QX4EDO0wSO5IzNzEzW}
```

### New Learnings
I learnt that you can use grep command after redirecting output to another file.

### References 
NIL

## Challenge 7: Grepping Live Output
The challenge requires you to use the | symbol to redirect output of one program while executing it.

### Solve
**Flag:** `pwn.college{oUwUTr2RmAEEA0MxGAxOoBLfAkV.QX5EDO0wSO5IzNzEzW}`

On running the command /challenge/run | grep pwn.college, I was able to obtain the flag since it had pwn.college as a pattern in it.

```bash
hacker@piping~grepping-live-output:~$ /challenge/run | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stdout : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stdout!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{oUwUTr2RmAEEA0MxGAxOoBLfAkV.QX5EDO0wSO5IzNzEzW}
```

### New Learnings
I learnt that you can use pipe symbol (|) to redirect output of one program as input of another.

### References 
NIL

## Challenge 8: Grepping Errors
The challenge requires you redirect errors and use grep command simultaneously to get the flag.

### Solve
**Flag:** `pwn.college{MzvYi_6rBpSIvt-TOEW6a-VlX7l.QX1ATO0wSO5IzNzEzW}`

I redirected the default stdout file descriptor to the stderr and then used | to use it's output as the input for the grep command.


```bash
hacker@piping~grepping-errors:~$ /challenge/run 2>& 1 | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stderr!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{MzvYi_6rBpSIvt-TOEW6a-VlX7l.QX1ATO0wSO5IzNzEzW}
```

### New Learnings
I learnt that you can use the >& operator when you want to redirect errors to another program while using | operator.

### References 
NIL

## Challenge 9: Filtering with grep-v
This challenge requires you to filter through content using grep -v command.

### Solve
**Flag:** `pwn.college{ss5jRoaLTahATzeUJZh5AjnSDeh.0FOxEzNxwSO5IzNzEzW}`

First, I redirected the output of /challenge/run and used grep -v command to filter out content containing DECOY since that is not the flag and hence was able to obtain the correct flag.

```bash
hacker@piping~filtering-with-grep-v:~$ /challenge/run | grep -v DECOY
pwn.college{ss5jRoaLTahATzeUJZh5AjnSDeh.0FOxEzNxwSO5IzNzEzW}
```

### New Learnings
I learnt that you can use grep -v to invert match (filter out) results containing a certain pattern.

### References 
NIL

## Challenge 10: Duplicating Piped Data with tee
This challenge requires you to pipe into another program but intercept it using tee command.

### Solve
**Flag:** `pwn.college{4ZCoulAijeYC1TY6DNrEsqLRykx.QXxITO0wSO5IzNzEzW}`

First, I piped the output of /challenge/pwn into /challenge/college but using tee command I intercepted the output to another file /challenge/pwnoutput. Using cat command, I was able to display this file which gave me the secret code to running the /challenge/college program which gave me the flag.

```bash
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn | tee /challenge/pwnoutput | /challenge/college
Processing...
The input to 'college' does not contain the correct secret code! This code
should be provided by the 'pwn' command. HINT: use 'tee' to intercept the
output of 'pwn' and figure out what the code needs to be.
hacker@piping~duplicating-piped-data-with-tee:~$ cat /challenge/pwnoutput
Usage: /challenge/pwn --secret [SECRET_ARG]

SECRET_ARG should be "4ZCoulAi"
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --secret 4ZCoulAi | /challenge/college
Processing...
Correct! Passing secret value to /challenge/college...
Great job! Here is your flag:
pwn.college{4ZCoulAijeYC1TY6DNrEsqLRykx.QXxITO0wSO5IzNzEzW}
```

### New Learnings
I learnt how to use tee command to debug or to intercept data that is being piped from one program to another.

### References 
NIL

## Challenge 11: Process Substitution with Input
This challenge requires you to use process substitution to compare two files.

### Solve
**Flag:** `pwn.college{cMWt9I7O0Bgj3VE-yrFumPGJLlY.0lNwMDOxwSO5IzNzEzW}`

Since the two programs contained decoys and only one contained the right flag, I used diff command to compare the two files using process substitution as arguments for the diff command.

```bash
hacker@piping~process-substitution-for-input:~$ diff <(/challenge/print_decoys) <(/challenge/print_decoys_and_
flag)
22a23
> pwn.college{cMWt9I7O0Bgj3VE-yrFumPGJLlY.0lNwMDOxwSO5IzNzEzW}
```

### New Learnings
I learnt that you can compare two commands without having to actually save them as files using process substitution with input.

### References 
NIL

## Challenge 12: Writing to Multiple Programs
This challenge requires you to write a program's output as input into two files at the same time.

### Solve
**Flag:** `pwn.college{Ea8mmVE4BSPMIcvXZG_NJw0BAnP.QXwgDN1wSO5IzNzEzW}`

I used the process substitution method and the tee command to obtain the flag by writing the output of /challenge/hack as input to both /challenge/the and /challenge/planet programs and used tee command to intercept the data being passed. 

```bash
hacker@piping~writing-to-multiple-programs:~$ /challenge/hack | tee  >(/challenge/the) >(/challenge/planet)
This secret data must directly and simultaneously make it to /challenge/the and
/challenge/planet. Don't try to copy-paste it; it changes too fast.
180472461882821843
Congratulations, you have duplicated data into the input of two programs! Here
is your flag:
pwn.college{Ea8mmVE4BSPMIcvXZG_NJw0BAnP.QXwgDN1wSO5IzNzEzW}
```

### New Learnings
I learnt how to write to multiple programs using process substitution method.

### References 
NIL

## Challenge 13: Split-piping stderr and stdout
This challenge requires you to combine all the operators learnt to redirect stdout and stderr into two different programs.

### Solve
**Flag:** `pwn.college{4nqrT4lmauRtxwFKQZbqj-JtA_9.QXxQDM2wSO5IzNzEzW}`

Since we need the stderr to be redirected into /challenge/the, we use the 2> operator and then the output is piped into /challenge/planet. Hence the flag is obtained.

```bash
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack 2> >(/challenge/the) | /challenge/planet
Congratulations, you have learned a redirection technique that even experts
struggle with! Here is your flag:
pwn.college{4nqrT4lmauRtxwFKQZbqj-JtA_9.QXxQDM2wSO5IzNzEzW}
```

### New Learnings
I learned how to combine and use 2> >() and | to redirect stderr and stdout wherever required.

### References 
NIL

## Challenge 14: Named Pipes
This challenge requires you to create a FIFO and redirect stdout to it and read from it.

### Solve
**Flag:** `pwn.college{UX_kG8u1kVsrQ1K6SW1BI_Q-sMp.01MzMDOxwSO5IzNzEzW}`

First I created the FIFO using mkfifo command and then redirected the stdout of /challenge/run to the FIFO. Then, in a new terminal, I used the cat command to read what was written to the FIFO and thud obtained the flag.

```bash
hacker@piping~named-pipes:~$ mkfifo /tmp/flag_fifo
hacker@piping~named-pipes:~$ /challenge/run > /tmp/flag_fifo
You're successfully redirecting /challenge/run to a FIFO at /tmp/flag_fifo!
Bash will now try to open the FIFO for writing, to pass it as the stdout of
/challenge/run. Recall that operations on FIFOs will *block* until both the
read side and the write side is open, so /challenge/run will not actually be
launched until you start reading from the FIFO!
hacker@piping~named-pipes:~$ cat /tmp/flag_fifo
You've correctly redirected /challenge/run's stdout to a FIFO at
/tmp/flag_fifo! Here is your flag:
pwn.college{UX_kG8u1kVsrQ1K6SW1BI_Q-sMp.01MzMDOxwSO5IzNzEzW}
```

### New Learnings
I learnt how to create a named pipe (FIFO) using mkfifo command and how to redirect and read from it. I also learnt the various benefits of using this method rather than the convnetional way using normal files.

### References 
NIL
