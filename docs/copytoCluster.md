---
title: Transferring Files to Cradle
order: 5
---
# Transferring Files to the Cluster

In order to transfer files to work on the cluster, it is recommended to use one of the following methods

- [scp](https://www.geeksforgeeks.org/scp-command-in-linux-with-examples/)
- [cloning from github](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository)


### scp Examples:
Transferring a local file to your directory on the cluster
```sh
scp localFileInMyDirectory.txt yourUserName@login.cradle.utrgv.edu:~/destinationForYourFile/
```

Transferring a file in a directory on the cluster to your local folder
```sh
scp yourUserName@login.cradle.utrgv.edu:~/destinationForYourFile/ localFileInMyDirectory.txt
```

#### Note on working within a directory on the terminal

Note that in both of the cases shown above `localFileInMyDirectory.txt` is the name of the file that is in your _current_ directory in your terminal. Usually you can tell which directory you are in by either looking at your terminal prompt:
```sh
# This indicates that my current directory is ~/Desktop/test
[username@mycomputer:~/Desktop/test]$
```

Or by using a command such as `pwd` on Linux/Mac or `cd` on Windows
```sh
# This should print something like 
# /home/username/Desktop/test
$ pwd
```

### github Cloning Repository Example:
You can also simply clone a repository that you have uploaded to Github with the following
```sh
git clone https://github.com/emenriquez/testTFForSlurm
```