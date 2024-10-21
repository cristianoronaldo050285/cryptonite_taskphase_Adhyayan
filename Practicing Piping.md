# PRACTICING PIPING
### REDIRECTING OUTPUT

This challenge taught me how to redirect output in Linux. ‘ECHO’ command is used to print things as it is only. To redirect an output in Linux we use the ‘>’ command. In this challenge I needed to write the word “PWN” in the file” COLLEGE” and I did that by the code mentioned below.(First check where the file “COLLEGE” is present on the system).
```
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your
flag:
pwn.college{kkYNJKXJUFJ49THNAsVNogg9ykW.dRjN1QDLzczM1czW}
```

###  REDIRECTING MORE OUTPUT
In this challenge as well I needed to redirect my flag from the ‘/challenge/run’ to ‘myflag’ using the command ‘>’.  Once it redirected the output to ‘myflag’ I used the ‘cat’ command to print out the flaf for me.
```
hacker@piping~redirecting-more-output:~$ cat /challenge/flag > myflag
cat: /challenge/flag: No such file or directory
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
[FLAG] pwn.college{YRl4MwBfi3ZS51nJ4A7m7zHsFOT.dVjN1QDLzczM1czW}
```

### APPENDING OUTPUT

This challenge taught me that redirecting outputs using ’>’ might delete the old contents leading to a problem if we need the older contents back. So, to overcome that problem we redirect input and output in append mode that is ‘>>’, thus preventing the deletion of older contents once newer contents are moved into the file.  In this challenge I needed to redirect the output in append mode(>>) from  ‘/challenge/run’ to ‘/home/hacker/the-flag’ this file. But if I didn’t use append mode then while using the ‘cat’ command after redirecting the flag it’ll only show me one half of the flag, not the other half.
```
hacker@piping~appending-output:~$ /challenge/run >> /home/hacker/the-flag
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
hacker@piping~appending-output:~$ cat /home/hacker/the-flag
 |
\|/ This is the first half:
 v
pwn.college{A2FafiHXwVhIDrlc7TQ3nPDSq1q.ddDM5QDLzczM1czW}
                              ^
     that is the second half /|\
                              |

If you only see the second half above, you redirected in *truncate* mode (>)
rather than *append* mode (>>), and so the write of the second half to stdout
overwrote the initial write of the first half directly to the file. Try append
mode!
```
### REDIRECTING ERRORS

A File Descriptor (FD) is a number that describes a communication channel in Linux.  We're already familiar with three : 
•	FD 0: Standard Input
•	FD 1: Standard Output
•	FD 2: Standard Error
A ‘>’  is the same as ‘1>’ only, and we use the ‘2>’ command for redirecting errors. In this challenge, I had to redirect the output of ‘/challenge/run’ to ‘myflag’ and all the errors to ‘instructions’ and once I pull this off I needed to use the ‘cat ‘ command in order to display the flag that I redirected.
```
hacker@piping~redirecting-errors:~$ /challenge/run > myflag 2> instructions
hacker@piping~redirecting-errors:~$ cat myflag
[FLAG] Here is your flag:
[FLAG] pwn.college{s56KIRRxT7TfYfwwVEnWmyk9Tua.ddjN1QDLzczM1czW}
```

### REDIRECTING INPUT

We can also redirect inputs from programs using  ‘<’ command. In this challenge, firstly I needed to redirect “COLLEGE” into the “PWN” file then I had to redirect the input from the “PWN” file to ‘/challenge/run’.
```
hacker@piping~redirecting-input:~$ echo COLLEGE > PWN
hacker@piping~redirecting-input:~$ /challenge/run < PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read
the value 'COLLEGE' out of it!
Here is your flag:
pwn.college{w1GYKoXbKRJ4qrWqSE4zTwY1XA6.dBzN1QDLzczM1czW}
```

###  GREPPING STORED RESULTS 

In this challenge, firstly I had to redirect my output from ‘/challenge/run’ to ‘/tmp/data.txt’ and then use the ‘grep’ command to find the string “pwn.college” as all the flags start form that phrase only. 
```
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
pwn.college{gFc-XovcC6UM4IPXLtNLH6WNEUC.dhTM4QDLzczM1czW}
```

### GREPPING LIVE OUTPUTS

This challenge taught me the use of the “PIPE OPERATOR” ‘|’ which is used to eradicate the need to the results to a file before using the ‘grep’ command to find the desired string. In this challenge I had to find the flag also while redirecting the output from’/challenge/run’ command by using the “PIPE OPERATOR”.
```
hacker@piping~grepping-live-output:~$ /challenge/run | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stdout : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/xpq4yhadyhazkcsggmqd7rsgvxb3kjy4-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stdout!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{4mAzDkEu5R5nJAf-ZuJ-8Ev1sF6.dlTM4QDLzczM1czW}
```

### GREPPING ERRORS

Here I learnt how to redirect errors and grep through them directly. The ‘>&’ operator redirects one file descriptor to another file descriptor. In this challenge, we had to redirect the error from ‘/challenge/run’ to ‘myflag’ and simultaneously grep the string “pwn.college”. Earlier, I was committing the mistake of not grepping the string “pwn.college” simultaneously along with redirecting the errors.
```
hacker@piping~grepping-errors:~$ /challenge/run 2>& 1> myflag | grep p
wn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/xpq4yhadyhazkcsggmqd7rsgvxb3kjy4-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stderr!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{MoHLx9EJBjY7wvHEV2PRt6K3jlk.dVDM5QDLzczM1czW}
```
