---
title: Intro to Working on Cradle
order: 4
---
# Intro to Working on Cradle

The Cradle cluster currently uses a command line interface for all user operations, the OS is linux-based. 

If you are not too familiar with working in the terminal, you can [check here for some useful command line operations on linux.](https://cheatography.com/davechild/cheat-sheets/linux-command-line/)

## Scheduler

The cluster accepts jobs through a scheduler called SLURM. Instead of running python scripts directly, the details of the job are submitted to the scheduler and placed into a queue to receive resources from the cluster. As soon as the resources are available, your job will begin and be carried out.

This is not really like running scripts interactively, so once the job is submitted the output is collected in output files instead of being displayed in the terminal. Additionally, users are not required to remain logged in for jobs to begin, be carried out and complete. You can simply log back in and check the status at anytime

[See here for a Sample script to submit a simple Machine Learning Job with Tensorflow](/docs/sampleSlurm.md)