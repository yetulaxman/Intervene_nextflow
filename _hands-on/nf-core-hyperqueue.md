---
topic: nextflow_container
title: Tutorial2 - Run nf-core pipeline with hyperqueue executor
---

nf-core is a community effort to collect a curated set of analysis pipelines built using Nextflow. Here we use [Sarek workflow](https://github.com/nf-core/sarek) as an example pipeline to detect variants on whole genome or targeted sequencing data.  In this tutorial we use HyperQueue executor instead of 'local' or 'slurm' executor. HyperQueue executor is useful for running nextflow in high-throughput manner and will not cause lot of overhead on batch scheduler accounting DB.


Here is an example batch script to run the pipeline on Puhti:
```bash
#!/bin/bash
#SBATCH --job-name=sarek_demo
#SBATCH --account=project_xxxx
#SBATCH --time=02:00:00
#SBATCH --nodes=2
#SBATCH --cpus-per-task=40
#SBATCH --ntasks-per-node=1
#SBATCH --partition=large

module load nextflow/22.10.1
module load hyperqueue

# To avoid disck space errors on home directory, use current working or other writable directory  
export APPTAINER_TMPDIR=$PWD      
export APPTAINER_CACHEDIR=$PWD

# Create a per job directory

export HQ_SERVER_DIR=$PWD/.hq-server-$SLURM_JOB_ID
mkdir -p $HQ_SERVER_DIR

# create a config file for nextflow to tell that this workflow uses hyperqueue executor
echo "executor {
   queueSize = $(( 40*SLURM_NNODES ))   
   name = 'hq'
  cpus = $(( 40*SLURM_NNODES )) 
 }" >>  hq.config
 
hq server start &
srun --cpu-bind=none --hint=nomultithread --mpi=none -N $SLURM_NNODES -n $SLURM_NNODES -c 40 hq worker start --cpus=40 &

num_up=$(hq worker list | grep RUNNING | wc -l)
while true; do

    echo "Checking if workers have started"
    if [[ $num_up -eq $SLURM_NNODES ]];then
        echo "Workers started"
        break
    fi
    echo "$num_up/$SLURM_NNODES workers have started"
    sleep 1
    num_up=$(hq worker list | grep RUNNING | wc -l)

done

nextflow run -c hq.config nf-core/sarek -r 3.1.1 -profile test,singularity -resume

# Make sure we exit cleanly once nextflow is done
hq worker stop all
hq server stop                     
                      
```

copy and paste the above script to a file named sarek_nfcore-hq.sh and replace your project number with project_xxxx in slurm directives.

Please note that all the nextflow scripts from underlying GitHub repository are cloned to "~/.nextflow/assets/" when launching pipelines with specific version (``` nextflow run nf-core/sarek -r 3.1.1 ... ```).  

Finally, submit your job

```bash
sbatch sarek_nfcore-hq.sh

```
