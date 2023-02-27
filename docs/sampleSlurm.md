---
title: Sample Script for SLURM Job
order: 5
---
# Sample Script for a SLURM job

The script below will request resources from the cluster and carry out a test job with Tensorflow:

```sh
#!/bin/bash

### Sets the job's name.
#SBATCH --job-name=myFirstJob

### Sets the job's output file and path.
#SBATCH --output=myFirstJob.out.%j

### Sets the job's error output file and path.
#SBTACH --error=myFirstJob.err.%j

### Requested number of nodes for this job. Can be a single number or a range.
#SBATCH -N 1

### Requested partition (group of nodes, i.e. compute, bigmem, gpu, etc.) for the resource allocation. 
#SBATCH -p kimq

### Requested number of gpus
#SBATCH --gres=gpu:1

### Limit on the total run time of the job allocation.
#SBATCH --time=1:00:00

echo "CUDA_VISIBLE_DEVICES: $CUDA_VISIBLE_DEVICES"

echo "Activating TensorFlow-2.6.2 environment"
source /shared/tensorflow-2.6.2/tf_env/bin/activate

echo "Running testTF.py"
python3 ~/testTFForSlurm/testTF.py

echo "Deactivating TensorFlow-2.6.2 environment"
deactivate

echo "Done."
```

*You will need the file `testTF.py` [downloaded](/docs/copyToCluster.md) for this script to work. If you have a file located in another directory, you can just provide the full path

For example:

Instead of
```sh
echo "Running Test Script File"
python3 ~/testTFForSlurm/testTF.py
```

Your file call will be
```sh
echo "Running Test Script File"
python3 /path/to/your/file.py
```