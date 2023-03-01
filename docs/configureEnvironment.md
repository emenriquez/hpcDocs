---
title: Configure Virtual Environment
order: 9
---
# Add to Existing Shared Environment

```
pip3 install --user virtualenv-clone
```
Now clone the environment with tensorflow (configured for the cluster and runs much faster)
```sh
virtualenv-clone /shared/tensorflow-2.6.2/tf_env/ ~/myEnvs/tf_env
```
(it takes a couple of minutes...)

Now you have the original environment copied to your user account

### Add new modules to your environment

Now you can add new packages by activating your environment and then installing anything needed inside

Ex: to install pandas in the copied `tf_env`
```sh
source ~/myEnvs/tf_env/bin/activate
```
Next, install the package
```sh
pip3 install pandas
```

### Make Sure to activate your new environment in the job script

Change the following line in your job submission script
```sh
echo "Activating TensorFlow-2.6.2 environment"
source /shared/tensorflow-2.6.2/tf_env/bin/activate
```
To your new environment
```sh
echo "Activating My custom environment"
source ~/myEnvs/tf_env/bin/activate
```