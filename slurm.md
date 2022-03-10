# slurm

SLURM
Display default settings for SLURM:
$ scontrol show partitions

Display resources on the available nodes:
$ sinfo -o "%20N  %10c  %10m  %25f  %10G "

Show resources allocated to a specific job
$ scontrol show job -d <job-ID>

