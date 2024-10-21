# Comprehending Commands

### CAT : NOT THE PET , BUT THE COMMAND

The 'cat' command is used to read out the files. In this challenge
the flag was present in the flag file only and I just used
'cat flag' in my home directory only to get the flag.
```
hacker@commands~cat-not-the-pet-but-the-command:~$ ls
COLLEGE  PWN  a.out  hellohackers  myflag        pwn       vi
Desktop  a    flag   instructions  not-the-flag  the-flag
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{A8MqhwyWW2fWMwGLyFLrRi3Evbh.dFzN1QDLzczM1czW}
```

### CATTING ABSOLUTES

This challenge is also very similar to the first one as here also
I'm using the 'cat' command to read out the flag but here I'm
using the absolute path of '/flag' which makes it different from
the previous challenge.
```
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{4fJyOWD0tbqbxYweNgxZotxHawg.dlTM5QDLzczM1czW}
```

### MORE CATTING PRACTICE

In this challenge I couldn't change my directory so I just had to
use the 'cat' command to read out the flag which was present in
some random directory and just it's path was mentioned. So I just
used 'cat' and copied the path where the flag was present.
```
hacker@commands~more-catting-practice:~$ cat  /opt/splitmind/splitmind/flag
pwn.college{sSOAx1vMmGfXc7NizEmAicpfTkV.dBjM5QDLzczM1czW}
```

### GREPPING FOR A NEEDLE IN A HAYSTACK

Sometimes, the files that you might cat out are too big. Luckily,
 we have the grep command to search for the contents we need. The
'grep' command is used as grep SEARCH_STRING /path/file. In this
challenge the file '/challenge/data.txt' was filled with
millions of lines of text so I just used the 'grep' command
to fish out the flag.
```
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{0BapCT3ktuQ3A9Ordys-9aM59p1.ddTM4QDLzczM1czW}
```
### LISTING FILES

The 'ls' command is used to list out all the files present in the
current working directory. In this challenge I just had to go to
the directory '/challenge' then I had to use the 'ls' command
to find out which files were present in the '/challenge'
directory and then I just had to execute the program.
```
hacker@commands~listing-files:~$ cd /challenge
hacker@commands~listing-files:/challenge$ ls
18176-renamed-run-25793  DESCRIPTION.md
hacker@commands~listing-files:/challenge$ /challenge/18176-renamed-run-25793
Yahaha, you found me! Here is your flag:
pwn.college{g8rjKvWyDAqf4k4gf4iDl9javiz.dhjM4QDLzczM1czW}
```

### TOUCHING FILES

The 'touch' command is used to create new files in the current
working directory. In this challenge I just had to create two
new and blank files in the tmp directory.
```
hacker@commands~touching-files:~$ cd /tmp
hacker@commands~touching-files:/tmp$ touch pwn
hacker@commands~touching-files:/tmp$ touch college
hacker@commands~touching-files:/tmp$ ls
bin  college  hsperfdata_root  pwn  tmp.MiOQGWw5Zc
hacker@commands~touching-files:/tmp$ /challenge/run
Success! Here is your flag:
pwn.college{oVniX3r6f43PrD68xzqyMUKWK7l.dBzM4QDLzczM1czW}
```

### REMOVING FILES

The 'rm' command is used to remove files in the directory and in
this I just had to remove a certain mentioned file and then run
a program to capture the flag.
```
hacker@commands~removing-files:~$ ls
COLLEGE  PWN  a.out      hellohackers  myflag        pwn       vi
Desktop  a    delete_me  instructions  not-the-flag  the-flag
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ ls
COLLEGE  PWN  a.out         instructions  not-the-flag  the-flag
Desktop  a    hellohackers  myflag        pwn           vi
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{892bEoBVyUyYi0Ve-aERwfYYQsf.dZTOwUDLzczM1czW}
```

### HIDDEN FILES

Interestingly, ls doesn't list all the files by default. Linux has a
 convention where files that start with a '.' don't show up by default in ls and in a few other contexts. To view them with ls
, you need to invoke ls with the -a. In this challenge I just had
to use the command 'ls -a' in the '/' directory to get the file
where the flag was present and then I used the 'cat' command to
read out the flag.
```
hacker@commands~hidden-files:~$ cd /
hacker@commands~hidden-files:/$ ls
bin        dev   lib    libx32  nix   root  srv  usr
boot       etc   lib32  media   opt   run   sys  var
challenge  home  lib64  mnt     proc  sbin  tmp
hacker@commands~hidden-files:/$ ls -a
.                      bin        etc    lib64   nix   run   tmp
..                     boot       home   libx32  opt   sbin  usr
.dockerenv             challenge  lib    media   proc  srv   var
.flag-323563044528614  dev        lib32  mnt     root  sys
hacker@commands~hidden-files:/$ cat .flag-323563044528614
pwn.college{g45DgEZJnLl50Qeaxh8CZhhtNsY.dBTN4QDLzczM1czW}
```

### MAKING DIRECTORIES

By using the 'mkdir' command we can makke new directories on our
system and store files in it. In this challenge I just had to
create a new directory on my system and then make a new file in
it.
```
hacker@commands~making-directories:~$ mkdir /tmp/pwn
hacker@commands~making-directories:~$ cd /tmp/
hacker@commands~making-directories:/tmp$ cd /tmp/pwn
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ ls
college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Success! Here is your flag:
pwn.college{4j9kea72bgBsbTz-jbkyxuHvIUt.dFzM4QDLzczM1czW}
```







