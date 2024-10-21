# Pondering Paths
### THE ROOT 
In this challenge I learnt how to invoke a program.The root
directory being / and the flag being in '/pwn'.The style of path
which starts with the root directory is called an "absolute"
path.I invoked the program by just providing its path on the
command line.
```
hacker@paths~the-root:~$ /pwn
BOOM!!!
Here is your flag:
pwn.college{8xu_GswaToQpvbHQ4OMzJaaYL-f.dhzN5QDLzczM1czW}
```

### PROGRAM AND IT'S ABSOLUTE PATH
In this challenge the name of the challenge program was run. The
flag was present in the challenge directory which in turn was
present in the ROOT (/) directory.In order to get the flag
in this challenge I needed to invoke the program correctly
with all the directories in the correct order that is I needed to
just type '/challenge/run' on the command line because its the path
leading directly to the flag.
```
hacker@paths~program-and-absolute-paths:~$ /challenge/run
Correct!!!
/challenge/run is an absolute path! Here is your flag:
pwn.college{UY6UpiBdeUGQ0QCSKPzkLB9DjDH.dVDN1QDLzczM1czW}
```


### POSITION THY SELF 
In this challenge basically I had to invoke the'/challenge/run'
program but after changing directory( a directory is basically a
folder which helps us to organize our files).I needed to change my
directory to the /sys directory (/sys directory is a virtual
directory containing information about devices,drivers and kernel
features.Initially I was doing it all wrong as I was trying to
execute the program in the / directory but then I restarted the
challenge and found that it was the incorrect path.
```
hacker@paths~position-thy-self:~$ cd /sys
hacker@paths~position-thy-self:/sys$ ls
block  class  devices   fs          kernel  power
bus    dev    firmware  hypervisor  module
hacker@paths~position-thy-self:/sys$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{EUlDncVLJbfhawCbsd-z2ftANtj.dZDN1QDLzczM1czW}
```


### POSITION ELSEWHERE
This challenge was very similar to the above challenge with the
main difference being that in order to execute the '/challenge/run'
program I needed to be in the /usr/bin directory. So in order to
find out which path to take I ran the program without being in
any directory which told me which path to take.Then I changed my
directory and successfully executed the program.
```
hacker@paths~position-elsewhere:~$ cd /usr/bin
hacker@paths~position-elsewhere:/usr/bin$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{4nvfbl7nc6_KcSFv_cIcKNT0QA_.ddDN1QDLzczM1czW}
```


### POSITION YET ELSEWHERE
This challenge again being very similar to the above 2 challenges
the main difference being the path that I needed to take in order
to execute my program . Again here as well I initailly ran my
program to find out which path to take. It showed that I wasn't
in the / directory so changed my directory and then executed the
program '/challenge/run'.
```
hacker@paths~position-yet-elsewhere:~$ cd /
hacker@paths~position-yet-elsewhere:/$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{oaiS0ox4sbZiOj5sCJA-hkRWIUn.dhDN1QDLzczM1czW}
```


### IMPLICIT RELATIVE PATHS
This challenge taught me about "RELATIVE PATHS". The difference
between an ABSOLUTE path and a RELATIVE path is that a relative
path will not start with the ROOT directory (/). If my cwd is /,
 then a relative path to the file is tmp/a/b/my_file.
If my cwd is /tmp, then a relative path to the file is a/b/my_file.
If my cwd is /tmp/a/b/c, then a relative path to the file is
 ../my_file where the .. refers to the parent directory. So in
this challenge I first needed to go into the / directory then
execute the program challenge/run because we needed a relative
path in order to get the flag.
```
hacker@paths~implicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{8EG3TP7aUbDBM3-EefPiTe770rx.dlDN1QDLzczM1czW}
```


### EXPLICIT RELATIVE PATHS
In our previous challenge the relative path was "NAKED" means
it directly specified the directory to descend into from the
current directory. In most operating systems, including Linux,
 every directory has two implicit entries that you can reference
 in paths: . and .., the first, ., refers right to the same
 directory. In this challenge I first changed the directory to /
then executed the program './challenge/run' which gave me the
flag.
```
hacker@paths~explicit-relative-paths-from-:~$ cd /
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{gEYW3kH0GWFESVVUrEns_WkJbK8.dBTN1QDLzczM1czW}
```

### HOME SWEET HOME 
The home directory is usually of the form /home/username. The '~'
is used as a shortform for the home directory. If we just use the
command 'cd' without passing any arguement we'll reach the
home directory. In this challenge firstly I went tho the home
directory then I executed the program along with passing the
arguement and I knew which arguement to give as I used the
'ls' command wich I knew (thanks to my computer science lab in my
college) which is used to list the files in the current directory
that we are in. Prior to this successful attempt I was doing it all
wrong as I wasn't using '~' before passing the arguement beacause
without this the system won't understand where exactly to copy the
flag.
```
hacker@paths~home-sweet-home:~$ cd
hacker@paths~home-sweet-home:~$ /challenge/run ~/a
Writing the file to /home/hacker/a!
... and reading it back to you:
pwn.college{IHs8dWajpAE8MYM33snKV__xfZA.dNzM4QDLzczM1czW}
```



