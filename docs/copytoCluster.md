# Transferring Files to the Cluster

In order to transfer files to work on the cluster, it is recommended to use one of the following methods

- [scp](https://www.geeksforgeeks.org/scp-command-in-linux-with-examples/)
- [cloning from github](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository)


### scp example:
```sh
scp localFileInMyDirectory.txt yourUserName@login.cradle.utrgv.edu:~/destinationForYourFile/
```

### github cloning repository example:
```sh
git clone https://github.com/emenriquez/testTFForSlurm
```