---
layout: post
title: Downloading fastq files from NCBI SRA programmatically
date: 2021-06-05
---

Often, one wants to download multiple FASTQ files from the NCBI Sequence Read Archive. 

## Step 1: list of SRR identifiers

Make a file called "files2download.txt". Add the SRR identifiers from NCBI. 

```bash
SRR1266879
SRR1266880
SRR1266881
SRR1266882
etc.
```

There is one run identifier per line. 

## Step 2: make the bash script

Create a `bash` with these lines:

```
#!/bin/bash

FILENAME="files2download.txt"

LINES=$(cat $FILENAME)

for LINE in $LINES; do
    echo $LINE
    parallel-fastq-dump -s $LINE -t 8 -O ./ --gzip 
done
```

## parallel-fastq-dump

usage: `parallel-fastq-dump [-h] [-s SRA_ID] [-t THREADS] [-O OUTDIR] [-T TMPDIR] [-N MINSPOTID] [-X MAXSPOTID] [-V]`

parallel fastq-dump wrapper, extra args will be passed through

optional arguments:
  -h, --help            show this help message and exit
  -s SRA_ID, --sra-id SRA_ID
                        SRA id (default: None)
  -t THREADS, --threads THREADS
                        number of threads (default: 1)
  -O OUTDIR, --outdir OUTDIR
                        output directory (default: .)
  -T TMPDIR, --tmpdir TMPDIR
                        temporary directory (default: None)
  -N MINSPOTID, --minSpotId MINSPOTID
                        Minimum spot id (default: 1)
  -X MAXSPOTID, --maxSpotId MAXSPOTID
                        Maximum spot id (default: None)
  -V, --version         shows version (default: False)

DESCRIPTION:
Example: parallel-fastq-dump --sra-id SRR2244401 --threads 4 --outdir out/ --split-files --gzip

**Source:** https://github.com/rvalieris/parallel-fastq-dump