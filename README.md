# The Missing Semester of Your CS Education
my solution to the exercises of "The Missing Semester of Your CS Education"(from MIT)

## LECTURE 1

1. Create a new directory called missing under /tmp.
```
mkdir /tmp/missing
```

2. Look up the touch program. The man program is your friend.
```
man touch
```

3. Use touch to create a new file called semester in missing.
```
touch /tmp/missing/semester
```

4. Write the following into that file, one line at a time:
```
#!/bin/sh
curl --head --silent https://missing.csail.mit.edu
```

The first line might be tricky to get working. It’s helpful to know that # starts a comment in Bash, and ! has a special meaning even within double-quoted (") strings. Bash treats single-quoted strings (') differently: they will do the trick in this case. See the Bash quoting manual page for more information.

5. Try to execute the file, i.e. type the path to the script (./semester) into your shell and press enter. Understand why it doesn’t work by consulting the output of ls (hint: look at the permission bits of the file).
```
./semester
```

6. Run the command by explicitly starting the sh interpreter, and giving it the file semester as the first argument, i.e. sh semester. Why does this work, while ./semester didn’t?
```
sh semester
```

7. Look up the chmod program (e.g. use man chmod).
```
man chmod
```

8. Use chmod to make it possible to run the command ./semester rather than having to type sh semester. How does your shell know that the file is supposed to be interpreted using sh? See this page on the shebang line for more information.
```
chmod 755 semester
```

9. Use | and > to write the “last modified” date output by semester into a file called last-modified.txt in your home directory.
```
ls -l semester | cut -d ' ' -f '6-8' > ~/last-modified.txt
```
