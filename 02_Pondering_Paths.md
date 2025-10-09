# Module Name: Pondering Paths

## Challenge 1: the root
The challenge requires you to invoke a program in the root directory

### Solve
**Flag:** `pwn.college{Av9bjH48z2i_KI7T_R0fyiK2pwA.QX4cTO0wSO5IzNzEzW}`

I invoked the pwn program on the terminal using its absolute path /pwn which gave me the flag.

```bash
hacker@paths~the-root:~$ /pwn
BOOM!!!
Here is your flag:
pwn.college{Av9bjH48z2i_KI7T_R0fyiK2pwA.QX4cTO0wSO5IzNzEzW}
```

### New Learnings
I learnt that you can invoke a program simply by typing its absolute path in the terminal.

### References 
NIL

## Challenge 2: program and absolute paths
The challenge requires you to execute the run program in the challenge directory.

### Solve
**Flag:** `pwn.college{wdQ8rGBSoN7i0kRWUeYESTZfbbP.QX1QTN0wSO5IzNzEzW}`

By typing the absolute path of the run file, I was able to obtain the flag immediately.


```bash
hacker@paths~program-and-absolute-paths:~$ /challenge/run
Correct!!!
/challenge/run is an absolute path! Here is your flag:
pwn.college{wdQ8rGBSoN7i0kRWUeYESTZfbbP.QX1QTN0wSO5IzNzEzW}
```

### New Learnings
Through this challenge I learned that you can invoke a program in a certain deirectory using it's absolute path.

### References 
NIL

## Challenge 3: position thy self
The challenge requires you to change directories and then execute the required file.

### Solve
**Flag:** `pwn.college{wQ0pqTZ08KFtohIV5gNYfik_BSR.QX2QTN0wSO5IzNzEzW}`

First, I ran the /challenge/run command which gave me the hint to go to a particular directory. Using cd command, I switched to that directory and ran /challenge/run command once again and got the flag.


```bash
hacker@paths~position-thy-self:~$ /challenge/run
Incorrect...
You are not currently in the /usr/share/zoneinfo/posix/Asia directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-thy-self:~$ cd /usr/share/zoneinfo/posix/Asia
hacker@paths~position-thy-self:/usr/share/zoneinfo/posix/Asia$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{wQ0pqTZ08KFtohIV5gNYfik_BSR.QX2QTN0wSO5IzNzEzW}

```

### New Learnings
I learned about switching directories using cd command and executing a file or program.

### References 
NIL

## Challenge 4: position elsewhere
The challenge requires you to execute the /challenge/run program from another directory.

### Solve
**Flag:** `pwn.college{81T1si835ZQpAGy37mYFnapL0Ya.QX3QTN0wSO5IzNzEzW}`

First, I ran the /challenge/run command which gave me the hint to go to a particular directory. Using cd command, I switched to that directory and ran /challenge/run command once again and got the flag.

```bash
hacker@paths~position-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /var/log directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-elsewhere:~$ cd /var/log
hacker@paths~position-elsewhere:/var/log$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{81T1si835ZQpAGy37mYFnapL0Ya.QX3QTN0wSO5IzNzEzW}
```

### New Learnings
I learnt that there are many more such directories and each contains files which can be executed. 

### References 
NIL

## Challenge 5: position yet elsewhere
The challenge requires you to execute the /challenge/run program from another directory.

### Solve
**Flag:** `pwn.college{ceVlMkHeBv1qMhyhVvpJeJUYaIn.QX4QTN0wSO5IzNzEzW}`

First, I ran the /challenge/run command which gave me the hint to go to a particular directory. Using cd command, I switched to that directory and ran /challenge/run command once again and got the flag.

```bash
hacker@paths~position-yet-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /etc directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-yet-elsewhere:~$ cd /etc
hacker@paths~position-yet-elsewhere:/etc$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{ceVlMkHeBv1qMhyhVvpJeJUYaIn.QX4QTN0wSO5IzNzEzW}
```

### New Learnings
I learnt that there are many more such directories and you can iterate through these using the cd command.

### References 
NIL

## Challenge 6: implicit relative paths, from /
The challenge requires you to run a file using a relative path instead of the absolute path.

### Solve
**Flag:** `pwn.college{sKINoPd1cmBL0S9KRXoxhGHe9Pi.QX5QTN0wSO5IzNzEzW}`

First I changed directories from ~ to root using cd / command. Then I gave the relative path of the file required and got the flag.

```bash
hacker@paths~explicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{sKINoPd1cmBL0S9KRXoxhGHe9Pi.QX5QTN0wSO5IzNzEzW}
```

### New Learnings
I learnt that you can invoke a program in a particular directory by moving into that directory and typing its relative path in the terminal.

### References 
NIL

## Challenge 7: explicit relative paths, from / 
The challenge requires you to run a file using a relative path rather than its absolute path.

### Solve
**Flag:** `pwn.college{oGl02CO9jrbjpWC2CgvhZOTbQRZ.QXwUTN0wSO5IzNzEzW}`

First I changed directories from ~ to root using cd / command. Then I gave the relative path of the file required and got the flag.

```bash
hacker@paths~explicit-relative-paths-from-:~$ cd /
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{oGl02CO9jrbjpWC2CgvhZOTbQRZ.QXwUTN0wSO5IzNzEzW}
```

### New Learnings
I learnt that you can use . to signify the current directory in the path to invoke the required file in that directory. 

### References 
NIL

## Challenge 8: implicit relative path
The challenge requires you to invoke a program in the root directory

### Solve
**Flag:** `pwn.college{IsDEtX4TxU1RjJ2LZBob0qGgbXY.QXxUTN0wSO5IzNzEzW}`

First I changed directories from ~ to root using cd / command. Then from / to challenge using the cd command itself. Then by using ./run I was able to run the file directly from that directory.


```bash
hacker@paths~implicit-relative-path:~$ cd /
hacker@paths~implicit-relative-path:/$ cd challenge/
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{IsDEtX4TxU1RjJ2LZBob0qGgbXY.QXxUTN0wSO5IzNzEzW}
```

### New Learnings
I learnt that you can invoke a program in a paritcular directory using ./file_name provided it exists in the current working directory.

### References 
NIL

## Challenge 9: home sweet home
This challenge requires you to specify a path as an argument to the /challenge/run command.

### Solve
**Flag:** `pwn.college{cH5b0-Q9byjxpDRtnZJBVTbfbWP.QXzMDO0wSO5IzNzEzW}`

By specifying the path to a certain file p in the home directory, I was able to obtain the flag since it copied the contents into the file.

```bash
hacker@paths~home-sweet-home:~$ /challenge/run ~/p
Writing the file to /home/hacker/p!
... and reading it back to you:
pwn.college{cH5b0-Q9byjxpDRtnZJBVTbfbWP.QXzMDO0wSO5IzNzEzW}
```

### New Learnings
I learnt that you can pass paths as arguments into commands and how to create a file for the command to copy into.

### References 
NIL
