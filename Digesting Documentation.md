# Digesting Documentation
### LEARNING FROM DOCUMENTATION

In order to run a program correctly it depends largely on the correct usage of arguements
along with the execution of programs like the case of 'ls -a' where '-a' arguement
was passed to list the secret hidden files present in the directory. In this challenge
I needed to execute the program '/challenge/challenge' along with passing the 
arguement --giveflag'.
```
hacker@man~learning-from-documentation:~$ /challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{UG0kWR3gpXFzAgHmRIH10rFr-hf.dRjM5QDLzczM1czW}
```

### LEARNING COMPLEX USAGE

The '--printfile' arguement is used to arbitrary files to the terminal and the arguement 
to '--printfile' is the path that it'll read out. In this challenge first we needed
to give the program '/challenge/challenge' then use the arguement '--printfile'
along with giving the address of the flag in the same line only.
```
```

### READING MANUALS

The 'man' command is used to print the manual of a command that we pass as an 
arguement. 'man' is the short form of manual. You can scroll around the manpage with
your arrow keys and 'PgUp/PgDn'. When you're done reading the manpage, you can hit 'q'
to quit. The arguements that we give to the 'man' command are not file paths but 
just the command. In this challenge we needed to read the manual of 'challenge'
command to understand what is needed to get that flag.
```
hacker@man~reading-manuals:~$ man challenge
hacker@man~reading-manuals:~$ /challenge/challenge --ggxevd 778
Correct usage! Your flag: pwn.college{g7g7xevdDCymrHN8k36J6v6LxfP.dRTM4QDLzczM1czW}
```

### SEARCHING MANUALS

You can scroll man pages with the arrow keys and 'PgUp/PgDn' and search with '/'.
After searching, you can hit 'n' to go to the next result and 'N' to go to the 
previous result. Instead of '/', you can use '?' to search backwards. In this 
challenge we needed to read the manual of 'challenge' command and then find using
'/' the arguement that we need to pass in order to get the flag.
```
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ /challenge/challenge --of
Initializing...
Correct usage! Your flag: pwn.college{EoRDZAPIl4OUbJo2w48EVbKBPro.dVTM4QDLzczM1czW}
```

### HELPFUL PROGRAMS

Through this challenge I learn that some programs don't even have a manual page and
in order to invoke it we need to give a special arguement like '--help' , '-h' ,
'-?' or '-help' etc. In this challenge I had to use the '--help' arguement to get
the manual page of '/challenge/challenge' and then use the given information in the
manual to get the flag.
```
hacker@man~helpful-programs:~$ /challenge/challenge --help
hacker@man~helpful-programs:~$ /challenge/challenge -p
The secret value is: 989
hacker@man~helpful-programs:~$ /challenge/challenge -g 989
Correct usage! Your flag: pwn.college{E98pJQ9kZlp0hYon32pkSTmGvO5.ddjM4QDLzczM1czW}
```

### HELP FOR BUILTINS

Some commands, rather than being programs with 'man' pages and 'help' options, are 
built into the shell itself. These are called "builtins". Builtins are invoked just
like commands, but the shell handles them internally instead of launching other 
programs. In this challenge the command 'challenge' is a 'builtin' and I needed to use
the 'help' command to access the manual page of 'challenge' and then follow the 
instructions to get the flag as depicted in the code below.
```
hacker@man~help-for-builtins:~$ help challenge
hacker@man~help-for-builtins:~$ challenge --secret gdN1iVez
Correct! Here is your flag!
pwn.college{gdN1iVeznUCjjGLVKrCfQx24EOz.dRTM5QDLzczM1czW}
```




