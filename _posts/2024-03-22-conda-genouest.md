---
layout: post
title: Source a conda environment on the GenOuest cluster and start Shortstack
date: 2024-03-15
---

## Creation du script Shortstack

The script is called `shortstack_sbatch_script.sh ` and contains the following lines: 

```bash
#! /bin/bash
source /local/env/envconda.sh
source activate /groups/bipaa/env/shortstack_4.0.3 # ou source activate /groups/bipaa/env/shortstack

ShortStack --readfile [my sample] --outdir [my output directory] --threads N --dn_mirna --genome [my genome] 
```

## Submit the script to SLURM 

```bash
# Request resources from genouest
srun -c4 --mem=40G --pty bash  
bash shortstack_sbatch_script.sh
```
