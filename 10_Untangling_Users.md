# Module Name: Untangling Users

## Challenge 1: Becoming Root with su
The challenge requires you become root using su command.

### Solve
**Flag:** `pwn.college{4-VVhn86Hd3Ezd8uyH6fo-pdFX3.QX1UDN1wSO5IzNzEzW}`

I used the su command to get root access and read the /flag file to obtain the flag.

```bash
hacker@users~becoming-root-with-su:~$ su
Password:
root@users~becoming-root-with-su:/home/hacker# cat /flag
pwn.college{4-VVhn86Hd3Ezd8uyH6fo-pdFX3.QX1UDN1wSO5IzNzEzW}
```

### New Learnings
I learnt how to gain root access using su command

### References 
NIL

## Challenge 2: Other Users with su
The challenge requires you to use su command to switch users to zardus.

### Solve
**Flag:** `pwn.college{YBVxcw2ARviGzHgp6wYMVCiB8OV.QX2UDN1wSO5IzNzEzW}`

First, I used the su command to change user to zardus and entered the password. On running /challenge/run, I was able to obtain the flag.


```bash
hacker@users~other-users-with-su:~$ su zardus
Password:
zardus@users~other-users-with-su:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{YBVxcw2ARviGzHgp6wYMVCiB8OV.QX2UDN1wSO5IzNzEzW}
```

### New Learnings
I learnt how to switch users using su user command.

### References 
NIL

## Challenge 3: Cracking Passwords
The challenge requires you to crack a password to switch users and run a program.

### Solve
**Flag:** `pwn.college{8i_hALhezBZRsxLol5eOtybXUdm.QX3UDN1wSO5IzNzEzW}`

First, I used the john command to decrypt the passwords in /challenge/shadow-leak and obtained the password. Then I switched to zardus user using su command and entered the password I decrypted. On running /challenge/run in zardus user, I was able to obtain the flag.


```bash
hacker@users~cracking-passwords:~$ john /challenge/shadow-leak
Loaded 1 password hash (crypt, generic crypt(3) [?/64])
aardvark         (zardus)
1g 0:00:00:21 100% 2/3 0.04679g/s 272.4p/s 272.4c/s 272.4C/s Johnson..buzz
Use the "--show" option to display all of the cracked passwords reliably
Session completed
hacker@users~cracking-passwords:~$ su zardus
Password:
zardus@users~cracking-passwords:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{8i_hALhezBZRsxLol5eOtybXUdm.QX3UDN1wSO5IzNzEzW}
```

### New Learnings
I learned how to use john the ripper as a tool to crack passwords.

### References 
NIL

## Challenge 4: Using sudo
The challenge requires you to read from a file using root permissions.

### Solve
**Flag:** `pwn.college{wb-PZwSwvw2iHwoOkY0tj9FTljw.QX4UDN1wSO5IzNzEzW}`

Using the sudo command, I gained root access to read the /flag file and obtain the flag.

```bash
hacker@users~using-sudo:~$ sudo cat /flag
pwn.college{wb-PZwSwvw2iHwoOkY0tj9FTljw.QX4UDN1wSO5IzNzEzW}
```

### New Learnings
I learnt how to use sudo command to gain root access without switching users.

### References 
NIL
