---
title: Submitting a Job to SLURM
order: 7
---
# Submitting a Job to SLURM

Once you have a script prepared with your job, submission is fairly straightforward.

Simply submit the job to the scheduler using the command below, where slurm_sample.sh can be replaced with your job script file name:
```sh
sbatch slurm_sample.sh
```
You may need to specify the path to the script file if you are working in another directory, for example:
```sh
sbatch ~/testTFForSlurm/slurm_sample.sh
```

## Checking Job Status
Once you submit your job, there are two simple ways to check the progress of your job. First, you can see your job's location in the scheduler queue:
```sh
squeue
```
This will output all jobs currently in the scheduler, including your job if it is currently running.

**NOTE:** Once your job completes, it will disappear from this list, so be sure to check the log files for your job to make sure that you do not resubmit in case of error or a job that has already completed.

To check the logs (output) of your job, you will go to the filename specified in `--output` in your slurm job script file. For example, if the line in your script reads:
```sh
### Sets the job's output file and path.
#SBATCH --output=myFirstJob.out.%j
```
Then your output file will appear with the job number in the same directory as your script file, with the filename `myFirstJob.out.813` (in this example case, the job # in the scheduler is 813 - each job has a unique job number assignment)

To check the contents of the logs, you can use `cat`. For example:
```sh
cat myFirstJob.out.813
```