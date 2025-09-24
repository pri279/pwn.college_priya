# Module Name: Comprehending Commands

## Challenge 1: cat: not the pet, but the command!
The challenge requires you to use the cat command and read a file.

### Solve
**Flag:** `pwn.college{kL5zO5hrXDXQcD8Uo66-PHYHRNJ.QXxcTN0wSO5IzNzEzW}`

Using the cat command, I was able to read from a file called flag and obtain the flag.

```bash
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{kL5zO5hrXDXQcD8Uo66-PHYHRNJ.QXxcTN0wSO5IzNzEzW}
```

### New Learnings
I learnt that you can read the contents of a file using cat command.

### References 
NIL

## Challenge 2: catting absolute paths
The challenge requires you to use the cat command with an absolute path as an argument.

### Solve
**Flag:** `pwn.college{wgViRhNAYJIILZEW4uJ3zlbAhEC.QX5ETO0wSO5IzNzEzW}`

By giving the absolute path of the flag file to the cat command, I was able to obtain the flag.


```bash
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{wgViRhNAYJIILZEW4uJ3zlbAhEC.QX5ETO0wSO5IzNzEzW}
```

### New Learnings
Through this challenge, I learned that you can also use absolute paths as arguments for cat command.

### References 
NIL

## Challenge 3: more catting practice
This challenge makes you use the absolute path of the file to retrieve the flag.

### Solve
**Flag:** `pwn.college{k4_Nk2NdRDot-09Pm2uWxXIDTYj.QXwITO0wSO5IzNzEzW}`

When I connected with SSH, I got a hint that the flag is in /usr/lib/p7zip/flag and so by giving that as an argument in cat command, I was able to retrieve the flag.


```bash
Connected!
You cannot use the 'cd' command in this level, and must retrieve the flag by
absolute path. Plus, I hid the flag in a different directory! You can find it
in the file /usr/lib/p7zip/flag. Go cat it out **without** cding into that
directory!
hacker@commands~more-catting-practice:~$ cat /usr/lib/p7zip/flag
pwn.college{k4_Nk2NdRDot-09Pm2uWxXIDTYj.QXwITO0wSO5IzNzEzW}

```

### New Learnings
I learned that cat command can take any absolute path as an argument.

### References 
NIL

## Challenge 4: grepping for a needle in a haystack
The challenge requires you to use the grep command to identify a particular substring from a file having lots of data.

### Solve
**Flag:** `pwn.college{YUUVymee_2k4nnSRBtBYP5iEOf2.QX3EDO0wSO5IzNzEzW}`

In this challenge, I used the grep command to quickly find the key since it always starts with pwn.college { }. This helped me solve the challenge and obtain the flag.

```bash
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{YUUVymee_2k4nnSRBtBYP5iEOf2.QX3EDO0wSO5IzNzEzW}
```

### New Learnings
I learnt about the grep command used to search through content if the data is too large for cat to help. 

### References 
NIL

## Challenge 5: comparing files
The challenge requires you to use the diff command to compare two files.

### Solve
**Flag:** `pwn.college{w_IyYR5lhDhEbI2yBew_GdNHExB.01MwMDOxwSO5IzNzEzW}`

Since there were two files, decoys_only.txt and decoys_and_real.txt, by comparing them I was able to figure out which flag was the odd one out and that would be the correct flag.

```bash
hacker@commands~comparing-files:~$ diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt
98a99
> pwn.college{w_IyYR5lhDhEbI2yBew_GdNHExB.01MwMDOxwSO5IzNzEzW}
```

### New Learnings
I learnt about the importance of diff command to compare the data in two files.

### References 
NIL

## Challenge 6: listing files
The challenge requires you to find the renamed file to obtain the flag.

### Solve
**Flag:** `pwn.college{0UkNUHdYH2RDPzs7OfDTZrwI7EE.QX4IDO0wSO5IzNzEzW}`

First I listed out the files in /challenge directory which gave me a hint since one of them had a random name. On invoking that file, I was able to obtain the flag.

```bash
hacker@commands~listing-files:~$ ls /challenge
5261-renamed-run-21031  DESCRIPTION.md
hacker@commands~listing-files:~$ /challenge/5261-renamed-run-21031
Yahaha, you found me! Here is your flag:
pwn.college{0UkNUHdYH2RDPzs7OfDTZrwI7EE.QX4IDO0wSO5IzNzEzW}
```

### New Learnings
I learnt that you can list out files in a particular directory using ls command.

### References 
NIL

## Challenge 7: touching files
The challenge requires you to create two new files and run the /challenge/run to obtain the flag.

### Solve
**Flag:** `pwn.college{cyb87dyumIJuqsNUpjKGkhd2cjI.QXwMDO0wSO5IzNzEzW}`

First I created the two files /tmp/pwn and /tmp/college using the touch command and passing its path as arguments. Then by running the /challenge/run command, I was able to obtain the flag.

```bash
hacker@commands~touching-files:~$ touch /tmp/pwn
hacker@commands~touching-files:~$ touch /tmp/college
hacker@commands~touching-files:~$ /challenge/run
Success! Here is your flag:
pwn.college{cyb87dyumIJuqsNUpjKGkhd2cjI.QXwMDO0wSO5IzNzEzW}
```

### New Learnings
I learnt that you can create new files in a particular directory/location using the touch command.

### References 
NIL

## Challenge 8: removing files
The challenge requires you to delete a file and then run a program that checks if its been deleted.

### Solve
**Flag:** `pwn.college{4euDnrWokPE6CPQ4jcREbuOOQhG.QX2kDM1wSO5IzNzEzW}`

First I deleted the delete_me file using the rm command. Then by invoking the /challenge/check program, I was able to get the flag.


```bash
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{4euDnrWokPE6CPQ4jcREbuOOQhG.QX2kDM1wSO5IzNzEzW}
```

### New Learnings
I learnt that you can remove/delete files using the rm command.

### References 
NIL

## Challenge 9: moving files
This challenge requires you to move a file to a specified location and obtain flag.

### Solve
**Flag:** `pwn.college{E_R4FuAmTFU33nxvQXLhEaWdwHz.0VOxEzNxwSO5IzNzEzW}`

Using the mv command, I moved the /flag file to /tmp/hack-my-planet and when I invoked the /challenge/run program, I was able to obtain the flag.

```bash
hacker@commands~moving-files:~$ mv /flag /tmp/hack-the-planet
Correct! Performing 'mv /flag /tmp/hack-the-planet'.
hacker@commands~moving-files:~$ /challenge/check
Congrats! You successfully moved the flag to /tmp/hack-the-planet! Here it is:
pwn.college{E_R4FuAmTFU33nxvQXLhEaWdwHz.0VOxEzNxwSO5IzNzEzW}
```

### New Learnings
I learnt that you can use mv command to move files from one placec to another.

### References 
NIL

## Challenge 10: hidden files
This challenge requires you to specify a path as an argument to the /challenge/run command.

### Solve
**Flag:** `pwn.college{AL8YWhnLYBdD47ca24ZQHPsMTb8.QXwUDO0wSO5IzNzEzW}`

First I moved into the root directory using cd command and then listed all the files, including the ones starting with . ,that are usually excluded, using ls -a command. Then I used the cat command to read the file contents and thus obtained the flag.

```bash
hacker@commands~hidden-files:/$ cd /
hacker@commands~hidden-files:/$ ls -a
.   .dockerenv          bin   challenge  etc   lib    lib64   media  nix  proc  run   srv  tmp  var
..  .flag-887222132173  boot  dev        home  lib32  libx32  mnt    opt  root  sbin  sys  usr
hacker@commands~hidden-files:/$ cat /.flag-887222132173
pwn.college{AL8YWhnLYBdD47ca24ZQHPsMTb8.QXwUDO0wSO5IzNzEzW}
```

### New Learnings
I learnt that Linux has a convention where files starting with . are not shown when ls command is used, but using ls -a we can view all those files in the directory.

### References 
NIL

## Challenge 11: an epic filesystem quest
This challenge requires you to use the hints given and find which directory to go or which file to look into.

### Solve
**Flag:** `pwn.college{Y0Dp8-yBghn-iCtsEI1vUUy4cX1.QX5IDO0wSO5IzNzEzW}`

First I went to the root directory and looked through the list of files and folders in it. I then read a file named INSIGHT using the cat command which gave me my next clue to another directory. But since it would self destruct if I changed to that directory, I used ls command and gave the absolute path of the required directory. Then I read a file which gave me the next hint to look into another directory. Following many such clues in a similar pattern, I was able to finally arrive at the flag.

```bash
hacker@commands~an-epic-filesystem-quest:~$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls
INSIGHT  boot       dev  flag  lib    lib64   media  nix  proc  run   srv  tmp  var
bin      challenge  etc  home  lib32  libx32  mnt    opt  root  sbin  sys  usr
hacker@commands~an-epic-filesystem-quest:/$ cat INSIGHT
Tubular find!
The next clue is in: /usr/local/lib/python3.8/dist-packages/mako/ext

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/$ ls /usr/local/lib/python3.8/dist-packages/mako/ext
ALERT-TRAPPED  __pycache__     babelplugin.py   extract.py       preprocessors.py  turbogears.py
__init__.py    autohandler.py  beaker_cache.py  linguaplugin.py  pygmentplugin.py
hacker@commands~an-epic-filesystem-quest:/$ cat /usr/local/lib/python3.8/dist-packages/mako/ext/ALERT-TRAPPED
Yahaha, you found me!
The next clue is in: /usr/share/icons/hicolor/64x64/intl

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/$ ls -a /usr/share/icons/hicolor/64x64/intl
.  ..  .MESSAGE
hacker@commands~an-epic-filesystem-quest:/$ cat /usr/share/icons/hicolor/64x64/intl/.MESSAGE
Tubular find!
The next clue is in: /var/lib/sudo/lectured

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/$ cd /var/lib/sudo/lectured
hacker@commands~an-epic-filesystem-quest:/var/lib/sudo/lectured$ ls
MEMO
hacker@commands~an-epic-filesystem-quest:/var/lib/sudo/lectured$ cat MEMO
Yahaha, you found me!
The next clue is in: /usr/lib/python3/dist-packages/hamcrest/library/number/__pycache__

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/var/lib/sudo/lectured$ cd  /usr/lib/python3/dist-packages/hamcrest/library/number/__pycache__
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/hamcrest/library/number/__pycache__$ ls
SECRET  __init__.cpython-38.pyc  iscloseto.cpython-38.pyc  ordering_comparison.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/hamcrest/library/number/__pycache__$ cat SECRET
Lucky listing!
The next clue is in: /opt/linux/linux-5.4/drivers/staging/qlge

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/hamcrest/library/number/__pycache__$ ls  /opt/linux/linux-5.4/drivers/staging/qlge
Kconfig  Makefile  TEASER-TRAPPED  TODO  qlge.h  qlge_dbg.c  qlge_ethtool.c  qlge_main.c  qlge_mpi.c
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/hamcrest/library/number/__pycache__$ cat  /opt/linux/linux-5.4/drivers/staging/qlge/TEASER-TRAPPED
Tubular find!
The next clue is in: /usr/share/racket/pkgs/typed-racket-more/typed/mred/compiled

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/hamcrest/library/number/__pycache__$ ls -a /usr/share/racket/pkgs/typed-racket-more/typed/mred/compiled
.  ..  .POINTER  mred_rkt.dep  mred_rkt.zo
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/hamcrest/library/number/__pycache__$ cat /usr/share/racket/pkgs/typed-racket-more/typed/mred/compiled/.POINTER
Yahaha, you found me!
The next clue is in: /opt/linux/linux-5.4/drivers/net/ethernet/aquantia/atlantic
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/hamcrest/library/number/__pycache__$ cd /opt/linux/linux-5.4/drivers/net/ethernet/aquantia/atlantic
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/net/ethernet/aquantia/atlantic$ ls
Makefile     aq_drvinfo.c  aq_filters.c   aq_hw_utils.h  aq_nic.h       aq_ring.h   aq_vec.h
README       aq_drvinfo.h  aq_filters.h   aq_main.c      aq_pci_func.c  aq_rss.h    hw_atl
aq_cfg.h     aq_ethtool.c  aq_hw.h        aq_main.h      aq_pci_func.h  aq_utils.h  ver.h
aq_common.h  aq_ethtool.h  aq_hw_utils.c  aq_nic.c       aq_ring.c      aq_vec.c
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/net/ethernet/aquantia/atlantic$ cat README
Yahaha, you found me!
The next clue is in: /usr/local/lib/python3.8/dist-packages/networkx/algorithms/tree

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/net/ethernet/aquantia/atlantic$ ls -a  /usr/local/lib/python3.8/dist-packages/networkx/algorithms/tree
.   .SNIPPET     __pycache__    coding.py         mst.py         recognition.py
..  __init__.py  branchings.py  decomposition.py  operations.py  tests
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/net/ethernet/aquantia/atlantic$ cat  /usr/local/lib/python3.8/dist-packages/networkx/algorithms/tree/.SNIPPET
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{Y0Dp8-yBghn-iCtsEI1vUUy4cX1.QX5IDO0wSO5IzNzEzW}
```

### New Learnings
I learnt that you can see the folders in a directory without actually going into it and that you can also read a file without entering that directory. All using absolute paths.

### References 
NIL

## Challenge 12: making directories
This challenge requires you to create a directory and run a program that checks if you did.

### Solve
**Flag:** `pwn.college{UAEv8BY14ANGYvlnxzJqD8LWD65.QXxMDO0wSO5IzNzEzW}`

I created a directory in /tmp called pwn and then created a file in it called college. After that, I invoked the /challenge/run program which checked if I had done those two things and then gave me the key.

```bash
hacker@commands~making-directories:~$ mkdir /tmp/pwn
hacker@commands~making-directories:~$ touch /tmp/pwn/college
hacker@commands~making-directories:~$ /challenge/run
Success! Here is your flag:
pwn.college{UAEv8BY14ANGYvlnxzJqD8LWD65.QXxMDO0wSO5IzNzEzW}
```

### New Learnings
I learnt how to create directories and add files inside them.

### References 
NIL

## Challenge 13: finding files
This challenge requires you to use the find command to search the entire filesystem for the flag file.

### Solve
**Flag:** `pwn.college{I2C2peX4w-znDQ76VtfkrpRrNlm.QXyMDO0wSO5IzNzEzW}`

I used the find command on the whole filesystem and specifying the name of the file and got a bunch of results. Through trial and error method, I was able to obtain the flag at the correct location.

```bash
hacker@commands~finding-files:~$ find / -name flag
find: ‘/tmp/tmp.TpSOPGOVKK’: Permission denied
find: ‘/etc/ssl/private’: Permission denied
/usr/local/lib/python3.8/dist-packages/pwnlib/flag
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/cache/private’: Permission denied
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/mysql-files’: Permission denied
find: ‘/var/lib/private’: Permission denied
find: ‘/var/lib/mysql’: Permission denied
find: ‘/var/lib/mysql-keyring’: Permission denied
find: ‘/var/lib/php/sessions’: Permission denied
find: ‘/var/log/private’: Permission denied
find: ‘/var/log/apache2’: Permission denied
find: ‘/var/log/mysql’: Permission denied
find: ‘/run/mysqld’: Permission denied
find: ‘/run/sudo’: Permission denied
find: ‘/root’: Permission denied
/opt/busybox/busybox-1.33.2/include/config/feature/top/smp/flag
/opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
find: ‘/proc/tty/driver’: Permission denied
find: ‘/proc/1/task/1/fd’: Permission denied
find: ‘/proc/1/task/1/fdinfo’: Permission denied
find: ‘/proc/1/task/1/ns’: Permission denied
find: ‘/proc/1/fd’: Permission denied
find: ‘/proc/1/map_files’: Permission denied
find: ‘/proc/1/fdinfo’: Permission denied
find: ‘/proc/1/ns’: Permission denied
find: ‘/proc/7/task/7/fd’: Permission denied
find: ‘/proc/7/task/7/fdinfo’: Permission denied
find: ‘/proc/7/task/7/ns’: Permission denied
find: ‘/proc/7/fd’: Permission denied
find: ‘/proc/7/map_files’: Permission denied
find: ‘/proc/7/fdinfo’: Permission denied
find: ‘/proc/7/ns’: Permission denied
/nix/store/ka6xbd6z6wj5d6frl7ym4nzfc6p2wkdx-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/f31j0igg7ms3yrj5gm3cm76bjcmdl8w5-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/7ns27apnvn4qj4q5c82x0z1lzixrz47p-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/5z3sjp9r463i3siif58hq5wj5jmy5m98-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/n6vb30rd7kkwjj595pgm0dmsmfaqi6i5-rizin-0.7.3/share/rizin/flag
/nix/store/5n5lp1m8gilgrsriv1f2z0jdjk50ypcn-rizin-0.7.3/share/rizin/flag
/nix/store/bnlabj2vsbljhp597ir29l51nrqhm89w-rizin-0.7.4/share/rizin/flag
/nix/store/s8b49lb0pqwvw0c6kgjbxdwxcv2bp0x4-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/8qvj9mzdq2qxgjigw4ysqgbkcx1zi80y-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag
/nix/store/1hyxipvwpdpcxw90l5pq1nvd6s6jdi5m-python3.12-pwntools-4.14.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/dz2qxywk6d8hc1gkarpwbhyxb50sh2ak-pwntools-4.14.0/lib/python3.13/site-packages/pwnlib/flag
hacker@commands~finding-files:~$ cat /usr/local/lib/python3.8/dist-packages/pwnlib/flag
cat: /usr/local/lib/python3.8/dist-packages/pwnlib/flag: Is a directory
hacker@commands~finding-files:/usr/local/lib/python3.8/dist-packages/pwnlib/flag$ cat /opt/busybox/busybox-1.33.2/include/config/feature/top/smp/flag
pwn.college{I2C2peX4w-znDQ76VtfkrpRrNlm.QXyMDO0wSO5IzNzEzW}
```

### New Learnings
I learnt the usage of the find command and how I can specify a location, criteria etc.

### References 
NIL

## Challenge 14: linking files
This challenge requires you to symlink a the flag file to fool the program into giving you the flag.

### Solve
**Flag:** `pwn.college{4JHCNtIHFZiMQeCKSPnpakQT_LH.QX5ETN1wSO5IzNzEzW}`

First, I tried running the /challenge/catflag program and it said it was supposed to read from the not-the-flag file (which didnt exist). Using that clue, I created a symlink between the correct /flag file and the /home/hacker/not-the/flag so that when I re-run the /challenge/catflag program, I would get the correct flag instead.

```bash
hacker@commands~linking-files:~$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
cat: /home/hacker/not-the-flag: No such file or directory
hacker@commands~linking-files:~$ ln -s /flag /home/hacker/not-the-flag
hacker@commands~linking-files:~$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{4JHCNtIHFZiMQeCKSPnpakQT_LH.QX5ETN1wSO5IzNzEzW}
```

### New Learnings
I learnt how to use symlinks to manipulate data and content in a particular file and also about hard links and soft/sym links.

### References 
NIL