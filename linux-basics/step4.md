Now that we know how to move around the system, how do we figure out what is available to us? Right now it’s like we are moving around in the dark. Well, we can use the wonderful ls command to list directory contents. The ls command will list directories and files in the current directory by default, however you can specify which path you want to list the directories of.

<pre>$ ls
$ ls /home/clarusway</pre>

ls is a quite useful tool, it also shows you detailed information about the files and directories you are looking at.

Also note that not all files in a directory will be visible. Filenames that start with . are hidden, you can view them however with the ls command and pass the -a flag to it (a for all). 

<pre>$ ls -a</pre>

There is also one more useful ls flag, -l for long, this shows a detailed list of files in a long format. This will show you detailed information, starting from the left: file permissions, number of links, owner name, owner group, file size, timestamp of last modification, and file/directory name. 

<pre>$ ls -l</pre>

<pre>clarusway@mac:$ ls -l
total 16
-rw-r--r-- 1 root root   13 Jun 28 12:39 clarusway
drwxr-xr-x 2 root root 4096 Jun 28 12:39 one
drwxr-xr-x 4 root root 4096 Jun 28 12:39 three
drwxr-xr-x 5 root root 4096 Jun 28 12:39 two</pre>

Commands have things called flags (or arguments or options, whatever you want to call it) to add more functionality. See how we added -a and -l, well you can add them both together with -la. The order of the flags determines which order it goes in, most of the time this doesn’t really matter so you can also do ls -al and it would still work.

<pre>$ ls -la</pre>

## Exercise

Run ls with different flags and see the output you receive.

>>Q4: What command would you use to see hidden files?<<

=== ls -a
