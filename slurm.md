---
title: slurm
created: '2022-03-03T03:59:02.017Z'
modified: '2022-03-03T03:59:06.491Z'
---

# slurm

SLURM
Display default settings for SLURM:
$ scontrol show partitions

Display resources on the available nodes:
$ sinfo -o "%20N  %10c  %10m  %25f  %10G "

Show resources allocated to a specific job
$ scontrol show job -d <job-ID>

