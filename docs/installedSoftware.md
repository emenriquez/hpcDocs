---
title: Preinstalled Software
order: 8
---
# Preinstalled Software
 - Tensorflow 2.6.2
 - PyTorch 1.10.2
 - gcc 11.2.1
 - OpenMPI 4.1.3
 - Intel OneAPI
 - CUDA 11.6
 - cuDNN 8

## Preconfigured Python Environments

The following Python virtual environments are available to be used ([or copied and then modified](/docs/configureEnvironment.md)) for easy access on the cluster

 - Tensorflow 2.6.2
   - Located in `/shared/tensorflow-2.6.2/tf_env/`
 - PyTorch
   - Located in `/shared/pytorch-1.10.2/pytorch_env`

There is also a gcc compiler available for C/C++ applications
 - gcc 11.2.1
   - Located in `/shared/openmpi/gcc-11.2.1`
 - gcc 8.5.0
   - Located in `/shared/openmpi/gcc-8.5.0`


Loading Environments/modules for your job:

To load a module for your job, you will activate the virtual environment by including the following line in your SLURM script before your code is executed. An example is shown below for the Tensorflow environment, but it can be replaced with any of the available modules in the `/shared/` directory:
```sh
### excerpt SLURM Script (options not shown)

echo "Activating TensorFlow-2.6.2 environment"
# This activates your virtual environment or module
source /shared/tensorflow-2.6.2/tf_env/bin/activate

echo "Running testTF.py"
# Then you can run your code
python3 ~/testTFForSlurm/testTF.py


echo "Deactivating TensorFlow-2.6.2 environment"
# Once your code is done, deactivate your environment
deactivate
```