# File Globbing

### MATCHING WITH *

In Linux the pattern used for matching or finding filenames is termed as "GLOBS". When it
encounters a GLOBBING CHARECTER it gets treated as a wildcard and the system tries to 
replace it with any file that matches with it. When zero files are matched by default
the shell leaves the glob unchanged. The glob can result in multiple arguements or
just one as well. In this challenge I needed to enter the '/challenge' directory 
by using atmost of four charecters and once I enter the directory I needed to run
the program '/challenge/run' which I did by the below mentioned code.
```
hacker@globbing~matching-with-:~$ cd /ch*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{sr8FnAOEMGK7S7VATWshybZGUkf.dFjM4QDLzczM1czW}
```

### MATCHING WITH ?

Coming to the '?' charecter it is actually very similar to the '*' with the main point
of difference being between the two that the shell will treat '?' as single charecter
only means it will match only one charecter at a time on the other hand the shell will
treat '*' as multiple charecter. Now coming to this challenge here we just needed to 
replace the alphabets 'c' and 'l' with '?' in order to change our directory and once
our directory changed we can easily run the program '/challenge/run' to capture the
flag. Here I made a mistake while doing this the first time as I completely 
misunderstood the question as I thought I just needed to replace the first two 
alphabets of the directory '/challenge' so I just wrote 'cd /??allenge' which 
apparently displayed that I used the charecters 'c' , 'l' or '*'. Here I would say
I completely misunderstood the question in order ro complete this question completely.
```
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{sj3zs_qpYlEeHHmbP8vbbZX--9G.dJjM4QDLzczM1czW}
```

### MATCHING WITH []

Moving on to the next glob that is '[]' which is kind of a subset for '?' with the 
difference being that we can search for multiple files at once. Suppose we gave the 
command '[pwn]' then it'll match the file with the charecters 'p' , 'w' or 'n'.
In this challenge first I needed to change my directory to '/challenge/file' then
I had to give a command such that it finds multiple files all at once and for that
I used '[]'. Initially I made a mistake of not giving the apt command that is I was
writing '/challenge/run [abhs]', actually I had to write '/challenge/run file_[abhs]'
as it was just searching the files 'a' , 'b' , 'h' and 's'.
```
hacker@globbing~matching-with-:~$ cd /challenge/files
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[abhs]
You got it! Here is your flag!
pwn.college{YiJn5-lUsYm-P4OwNUwkhGVRzLa.dNjM4QDLzczM1czW}
```

### MATCHING PATHS WITH []

We can use "GLOBBING" to find out the entire paths as well. In this challenge I needed
to execute the '/challenge/run' program in the home directory only, while specifying
the path for the files we need to find along with the use of '[]'. Here I was
trying to execute the program in the '/challenge/files' directory then I was using
the incorrect path to find the files as well.
```
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[abhs]
You got it! Here is your flag!
pwn.college{MTfXqFRUGBfLHx1MwSEFGgTVSPz.dRjM4QDLzczM1czW}
```
