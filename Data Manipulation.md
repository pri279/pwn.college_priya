# Module Name: Data Manipulation

## Challenge 1: Translating Characters
The challenge requires you to use tr command to swap cases.

### Solve
**Flag:** `pwn.college{UjMsPYrh-AsyXQyUdfTB16YgVmc.01MxEzNxwSO5IzNzEzW}`

Since the /challenge/run program would swap cases of each character, I used the tr command to swap it back and hence obtained the flag.

```bash
hacker@data~translating-characters:~$ /challenge/run | tr ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz
 abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ
yOUR CASE-SWAPPED FLAG:
pwn.college{UjMsPYrh-AsyXQyUdfTB16YgVmc.01MxEzNxwSO5IzNzEzW}

```

### New Learnings
I learnt how to use tr command for modifying data like swapping cases etc.

### References 
NIL

## Challenge 2: Deleting Characters
The challenge requires you to delete certain characters from the file.

### Solve
**Flag:** `pwn.college{gY9D33ZGIcfynygUqct2k2QX7zK.0FNxEzNxwSO5IzNzEzW}`

I was able to obtain the flag by deleting certain characters such as ^ and % using the tr -d command.


```bash
hacker@data~deleting-characters:~$ /challenge/run | tr -d ^%
Your character-stuffed flag:
pwn.college{gY9D33ZGIcfynygUqct2k2QX7zK.0FNxEzNxwSO5IzNzEzW}
```

### New Learnings
Through this challenge I learnt how to delete characters.

### References 
NIL

## Challenge 3: Deleting Newlines
The challenge requires you to use the tr command to delete all newlines.

### Solve
**Flag:** `pwn.college{YHo5dwa5BQngLk3oNvblhPO5zv9.0VNxEzNxwSO5IzNzEzW}`

By running the tr -d command with its argument as "\n" which represents the newline character, I was able to obtain the flag.


```bash
hacker@data~deleting-newlines:~$ /challenge/run | tr -d "\n"
Your line-split flag: pwn.college{YHo5dwa5BQngLk3oNvblhPO5zv9.0VNxEzNxwSO5IzNzEzW}
```

### New Learnings
I learned how to delete newline characters using tr -d.

### References 
NIL

## Challenge 4: Extracting the First Lines with head
The challenge requires you to read only the first few lines of a file.

### Solve
**Flag:** `pwn.college{QKpE2MLZsINXz-kShAYRI14cfol.0lNxEzNxwSO5IzNzEzW}`

First I piped the output of /challenge/pwn (which gives a huge lot of data) into the head command which reads the first 7 lines. And then piped that output into /challenge/college to obtain the flag.

```bash
hacker@data~extracting-the-first-lines-with-head:~$ /challenge/pwn | head -n 7 | /challenge/college
Congratulations, you piped the right codes!
pwn.college{QKpE2MLZsINXz-kShAYRI14cfol.0lNxEzNxwSO5IzNzEzW}
```

### New Learnings
I learnt how to use the head command if a program is very verbose and I only require the first few lines.

### References 
NIL

## Challenge 5: Extracting Specific Sections of Text
The challenge requires you to extract certain sections/columns of the text.

### Solve
**Flag:** `pwn.college{kC5P0Mlaw-uzazYU9petnDE1i5n.01NxEzNxwSO5IzNzEzW}`

First, I ran the /challenge/run program to see how the data looked like. I understood that the flag was on the 2nd column and the newline characters had to be removed. So I used cut and tr -d command to obtain the flag.

```bash
hacker@data~extracting-specific-sections-of-text:~$ /challenge/run
2544 p
6704 w
25083 n
9828 .
6818 c
12367 o
17390 l
21882 l
23816 e
18065 g
29384 e
18063 {
28018 k
4414 C
9761 5
23575 P
1446 0
22599 M
16377 l
5033 a
16606 w
13059 -
4825 u
3874 z
10539 a
20954 z
22443 Y
19763 U
1448 9
32438 p
6157 e
13822 t
20961 n
11382 D
867 E
3630 1
29677 i
30944 5
18437 n
20915 .
28844 0
18761 1
32714 N
17625 x
976 E
3474 z
102 N
25788 x
2458 w
2101 S
32148 O
7134 5
19644 I
24240 z
30981 N
19163 z
4135 E
7837 z
26492 W
16048 }
hacker@data~extracting-specific-sections-of-text:~$ /challenge/run | cut -d " " -f 2 | tr -d "\n"
pwn.college{kC5P0Mlaw-uzazYU9petnDE1i5n.01NxEzNxwSO5IzNzEzW}
```

### New Learnings
I learnt how to use cut command to access specific columns in the text and manipulate that to my requirement.

### References 
NIL

## Challenge 6: Sorting Data
The challenge requires you to sort contents of a file in alphabetical order.

### Solve
**Flag:** `pwn.college{srODrh8tp_LYDU8iSSXs3G2gVpK.0FM0MDOxwSO5IzNzEzW}`

Using sort command, I sorted the contents of /challenge/flags.txt and from the description, I was able to obtain the correct flag to be at the last position.

```bash
hacker@data~sorting-data:~$ sort /challenge/flags.txt
ovm.bollefe{sqODrg7tp_LYCU7hRRXs2G2gVpJ.0EM0MCNwwSO5IyNzEzV}
ovm.collefe{srODrh8so_LYCU8hSRXr2F2gVpK.0FM0LDOxwRO5HyNzEyW}
ovn.bnkkdgd{srODrg8so_LXCT7hSSXs3G2gUoK.0FM0LDNxwSO5IzNzEzW}
ovn.bnklegd{sqOCqh7sp_KXCT8hRRXs3F2fVpK.0FM0MDNxvSO5HzNzEzV}
ovn.bolkdge{sqNDrh8tp_LYDU8iSSWs3G2fVpJ.0FM0MDOxwRN5HyMzDzW}
ovn.colkefd{srODrh8sp_LYCT8hRSXs3F1fVpK.0FL0MDOxvSO4HzMzEzV}
ovn.colldge{srOCrh8to_LYCU8iSSXs3G2gVpK.0EM0MDOxwSO5HzNzEyV}
ovn.college{rrNDqh8tp_KYDU8iRSXr3G2gUoK.0EM0MDNwvSN5IzMyEzW}
ovn.college{rrODrh8tp_LYDU8iSSXr3G2fVpK.0FL0LDOxwSO4IzMzEzW}
owm.bolldge{srODrh8tp_LYDU8iSSXs3G1gVpK.0FL0MCOxwSO5IyNzEzV}
owm.cnlldge{srODrh8to_KYDU8iSSWs3G2gVpK.0FM0MDOxwSN5HzNzEzW}
owm.collegd{sqODrh7tp_LXDU8iSSXs3G2gVpK.0FM0MCOxvSO5IzNzEzW}
own.bnlkdgd{srNCrh7tp_LYDT8hSRXs2G2fVoK.0FM0MCOxvSN4IzNyEyW}
own.bnlkege{srOCrh8tp_KYDU8iSSXs3G2gUpK.0EM0LDOxwRO5IzNzEyW}
own.boklege{srOCqg7so_LYDT8iRRXr3G2fVpJ.0FM0MCOxwSO5IzNyEzV}
own.bolkege{rrNDqh7tp_LXDT8iSRWs3G2gVoJ.0FM0MDOxwSO5IzNzEzW}
own.cnklefe{srNCrh8tp_LYDT8iSRXs3G2gVpK.0FM0MDOwwSN5IzNzEzW}
own.cnklege{srNDrh7to_LXDU7iSSXr2G1fVpK.0EM0MDOxwSO5IzNyEzW}
own.coklege{srODrg8so_LYDT7iSSXs3G2gVoJ.0FL0MCOxwSO4IyNzDyW}
own.colkefd{srODrh7tp_LYCT7iSSXs3G2fVpJ.0FM0LDNxwSO5HzNzDzW}
own.colkege{rrODrh7tp_LYCT8iSSWs3G2fVpK.0FM0MDOxwSN5IzMyEzW}
own.collefe{srNDqh8tp_KYDT8hSRXs3G2gVpK.0FL0MDOxvSO5IyNzDzV}
own.college{srODrh8sp_KYDU8iRRXr3G2gVpJ.0FM0LDNxwSO5IzNzEzW}
own.college{srODrh8tp_LYDU8iSSXs3G2gVpK.0FM0MDOwwRO5IzMzEzW}
pvm.cnllege{rrNDrh8sp_LXCT8hSRXs3F2fVpK.0FL0LDNwwSO5IyNzDzW}
pvm.collefd{rrNCrh8sp_LXDU8iSRXs3F2fVpK.0FM0MDNwvSO5IzNzEzW}
pvm.college{rrNCqh8sp_LYCT7iSRWs2G2gVpK.0FM0MDOxvRO5HzNyDzW}
pvm.college{rrODrh8sp_KYDU8iSSXs3G1gVpK.0EM0MDOwwSN4HzMzEzW}
pvn.bnklege{srODrg8to_LXCU8iSSXs2G1fVoK.0EM0MDOxvRO4HzNyDzV}
pvn.bollege{srODrh8tp_LYDT8iSSXs3G1gVpK.0EM0MCOwvSN4IzNzEzW}
pvn.cnkkege{sqODrh8tp_LYDU7iRSXs2G2gVpK.0EL0LDOxvSO4HyMyEyV}
pvn.cnlkege{rqNCqh8tp_KYDU8iRSWs2G2gVoK.0FM0MCNwvRO5HzMzDzW}
pvn.cnlkege{sqODrh8tp_LYDT8hSSWr2F2gUpK.0FM0MCOxwSO4IyNzEzW}
pvn.coklege{rrOCrg8tp_LYCU7iRSXs2F2gVoK.0FM0MCNxwSN4IzNzEzW}
pvn.colkegd{rqNCrh8sp_LXCT8hSRXs3F2fVpK.0EM0MDOxwRO5HyMzEzV}
pvn.colldge{sqODrh8to_LXCT8iSSWs2G2gVpK.0FM0MDOxwRO5IzNzEzW}
pvn.colldge{srODrg8tp_LYDU8iRSWs3G1gVpJ.0FM0MCOxwSO5IzNzEzW}
pvn.colldge{srODrh7sp_LYCU7iRRWs3G1fUpK.0FM0MCNxvSO5IzNyDyW}
pvn.collefe{sqODqh8sp_LYDU8iSSXs3G2gVoK.0FL0LDOxvRO5IzNzEzW}
pvn.collegd{rqNDrh8tp_LXDT8iSRXs3F2gVpJ.0FL0LCOxwSO4IzNzEyV}
pvn.collegd{rqOCrg7tp_KYCU8iSRWr3F2fVpK.0FL0LDOwwSO5IyMyDyW}
pvn.collegd{rrOCrh8tp_LYDU7iSRXs3F2fVpK.0FM0LDOxwSN5IzNzEzW}
pvn.college{rrODrg8tp_LYDU8iSSXs3G2gVpK.0FM0LCOxwSO5IzNzDzW}
pvn.college{srODrh8tp_LYDT8iRSWr3G2gVoJ.0FM0MDNwvSO5IyMzEyW}
pwm.bnlkegd{srOCrh8to_LYCU7iSSWs2G2fUoK.0EL0LDNxwSN4IyMyEyV}
pwm.bolkdge{srODrh8tp_KYDT8iSRXr3G2fVpK.0EM0MDOxwSN4IzMzEyW}
pwm.bollege{sqODrh8to_LXDU8hSSXs3G2gVpK.0FM0MCOxwSO5IzNzEzW}
pwm.bollege{srODrh8tp_LYCU8iSSXs2G1gVpK.0FM0MCOxwSO5IzNzEzW}
pwm.cnlldgd{rrOCrh8tp_LXCU8hSSXs3F1gVpJ.0FL0LDOxvSO5IzNyDzW}
pwm.cnllege{sqNCrh8to_LYCU8iSSXs3G2gUpK.0FM0MDOxwSN5IzNyEyW}
pwm.cokkdgd{srODrg8tp_LYDT8hSRXr3G2gVpK.0FM0MDOwwRO5IzMzDzW}
pwm.cokldfe{srOCrh8to_LYCU8hSSWr3F2gUpK.0FL0LDOxvSO5IzNzDyW}
pwm.coklege{srODrh8sp_LYDU8hSSXr3G2gVpK.0FM0MDOxwSO5IzNzEzW}
pwm.collefd{srNDrh8tp_LYDU8iSSXs3F1gVpK.0EM0MCOwwSO5HzNzEzW}
pwm.college{rrODrh7to_KYDU7hSSXs3F2fVpK.0FL0MDOxwSO4IzNzEzW}
pwm.college{srODrh8tp_LYDU8iRSXs3G2gVpK.0FM0MDOxwSO5IyNyEzW}
pwn.bnlkegd{sqNDqg8to_LXCT7hSSWs2F2gVoK.0EL0MCOxwSO5IzNyEzW}
pwn.bokkdge{srODrg8tp_KYCU7iSRXs3F1fVpJ.0FL0MDOxwSO4IzMzEzV}
pwn.boklege{srOCrh8so_LYDT8iSSWr2G1gVpK.0FL0MDOwwSN4HyMzDzW}
pwn.boklege{srODrg7tp_LXDU8iSSXs3G2gVpK.0FM0MDOxwRO5IzNzDzW}
pwn.bolkege{srODrg7sp_KYCU8iRSXs3G2gVpK.0FM0LDOwwSO5IzMzDzW}
pwn.bollefe{srODrh8sp_LYDU7iSSWr2G2gUoK.0FM0MCOwwSN5IzMyEzW}
pwn.bollege{srODrh8tp_LYCU8iSSXs3G2gVpK.0FM0MDOxwSO5IzNzEzW}
pwn.bollege{srODrh8tp_LYDT8iSSXs3G2gVpK.0FM0MDOxwSO5IzNzEzW}
pwn.bollege{srODrh8tp_LYDU8iSSXr3G2gVpK.0FM0MCOxwSO5IzNzEzW}
pwn.bollege{srODrh8tp_LYDU8iSSXr3G2gVpK.0FM0MDNxwRO5IzNzEzW}
pwn.cnkkegd{rrNCrg8tp_KYDT7iSRXs2G2fVpK.0EM0MDNxvRO5IyNzEzV}
pwn.cnkkegd{srODqh8tp_KYDT8iSSXr3F2gVoJ.0FM0LDNxwSN5IzNzEzW}
pwn.cnllegd{srODrh8to_LYDT8hRSXr2G2gVoK.0FM0MCOxwSO5IyNzDzW}
pwn.cnllege{srODrg8tp_LYDU8iSSXs3G2gVpK.0FM0MDOxwSN5HzMzEzW}
pwn.cokkefe{rqNDrh8sp_LYDU7iRSXs2G2fVpJ.0FL0MDNwwRO5IzNzEyW}
pwn.cokkege{sqODqh8tp_KYCU8iSSWr3G2gUoK.0EM0MDNwwRO5IzNzDyW}
pwn.cokldfe{sqNDrg7so_KYDU8iRSWs3G2gVpK.0FM0MCOwwRN5IyNyEzW}
pwn.coklege{sqODrh7tp_LYDU8hSSXs2G2gVpK.0FM0LDOxvRO4IzNzEzW}
pwn.coklege{srOCrh8tp_LYDU8iSSXs3G2gVpK.0FM0MDOwvSN4IzNzEzW}
pwn.coklege{srODrh7tp_LYDT8iSSXs3G2fVpK.0FM0MDOxwSO5IzNzEzW}
pwn.coklege{srODrh7tp_LYDU8iSRXs3G2gVpK.0FM0MCOxwSO4IzNyEzV}
pwn.coklege{srODrh8tp_LXDU8iSSXr3G2gVpK.0FM0MDNxwSO5IyNzEzV}
pwn.colkefd{rrOCrh8sp_LYDT8iSSXs3G2gVpK.0EM0MDOwwSN5IzNzEzW}
pwn.colkege{srOCrh8tp_LYDU8iSRXs3G1gVpK.0FM0MDOxwSO5IzNzEzW}
pwn.colkege{srODqg8to_KYDU7iSRXs3G2fVpK.0FM0LDOxwSO5IyMzEzW}
pwn.colldfd{srOCrh8tp_LYDU8hSSXs3G1gVpK.0FM0MCOxwRN4IzNzDzW}
pwn.collefe{sqODrh8to_LXDU7hSSXs3G2gUpK.0EL0MDOxvRO4HzNzDzW}
pwn.college{rrODrh8tp_LYDU8iSSXs3G2gVpK.0FM0MDOxwSO5IzNzEzW}
pwn.college{sqODrh8tp_KYDU8iRSXs3G2gUpK.0FM0MDOxwSO5IzNzEzW}
pwn.college{sqODrh8tp_LYDT8iSSXs3G2gVpK.0FM0MDOxwSO5IzNzEzW}
pwn.college{srNCqh7sp_LYDU7iRRXs2G1fUoK.0EL0MDOxwSO5HzNzEzW}
pwn.college{srNCrh8tp_LYDU7hRSXs3F1fVpK.0FM0MDOwwRO5HyNzEzW}
pwn.college{srNDqh8sp_LYDU8iSSXs3G2gVpK.0FM0MDOxwRO5IzNzEzW}
pwn.college{srNDrh7tp_LYDU8iSSXs3G2gVpK.0FM0MDOxwSO5IzNzEzW}
pwn.college{srOCrh7tp_LYDU8iSSXs3G2gVpK.0FM0MDOxwSO5IzNzEzW}
pwn.college{srOCrh8tp_LYDU8iSSXs3G2gVpK.0FM0MDOxwSO5IzNzDzW}
pwn.college{srODqh8tp_LYDU8iSSXs3G2gVpK.0FM0LDOxwSO5IyNzEzW}
pwn.college{srODrg7tp_LYCT8hSSXs3G2gVpJ.0FL0LDNxvSN5IzNzDzW}
pwn.college{srODrh8tp_LYDT8iSSXs3G2gVpK.0FM0LDOwvSO4IzNzEzW}
pwn.college{srODrh8tp_LYDU8iSSWs3G2gVpK.0FM0MDOxwSO5IzNzEzW}
pwn.college{srODrh8tp_LYDU8iSSXs3G1gVpK.0FM0MDOxwSO5IzNzEzW}
pwn.college{srODrh8tp_LYDU8iSSXs3G2gVpK.0FM0MDOwwSO5IzNzEzW}
pwn.college{srODrh8tp_LYDU8iSSXs3G2gVpK.0FM0MDOxwSN5IzNzEzW}
pwn.college{srODrh8tp_LYDU8iSSXs3G2gVpK.0FM0MDOxwSO5IzNzEyW}
pwn.college{srODrh8tp_LYDU8iSSXs3G2gVpK.0FM0MDOxwSO5IzNzEzW}
```

### New Learnings
I learnt how to sort text alphabetically, reversed, uniquely etc.

### References 
NIL