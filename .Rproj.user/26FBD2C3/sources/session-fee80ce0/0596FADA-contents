#!/bin/bash
#
#SBATCH --account=132768133143
#SBATCH --job-name=parallelization-experiment
#SBATCH --time=00:05:00
#SBATCH --nodes=1
#SBATCH --tasks-per-node=1
#SBATCH --cpus-per-task=8
#SBATCH --mem=10G
#SBATCH --output=/scratch/user/brubaker/parallelization/par.o

## load required modules
module load GCC/12.2.0
module load OpenMPI/4.1.4
module load R_tamu/4.3.1

## run experiment
cd /scratch/user/brubaker/parallelization/
Rscript parallelization.R
