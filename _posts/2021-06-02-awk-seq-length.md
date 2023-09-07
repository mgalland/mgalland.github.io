---
layout: post
title: Computing sequence length from a fasta file 
date: 2021-06-02
---

Often, one wants to calculate the sequence length from a FASTA file. 

## Example

Say you have a FASTA file called `my_sequence.fasta`:  

```
>my_sequence
ATCGATCGATCG
```

Here, you'd like to compute "12" as the length of the `ATCGATCGATCG` sequence. 

## One-liner

To achieve this on a bigger FASTA file, run this code in your Shell: 

```bash
awk '/^>/ {print; next; } { seqlen = length($0); print seqlen}' my_sequences.fasta
```

This will return results to the stdout (your screen): 

```bash
12
```

You can execute this code on a multi-line FASTA file.


## FASTQ to FASTA

If needed, first convert your FASTQ to FASTA with [seqtk](https://github.com/lh3/seqtk).

```bash
seqtk seq -a in.fq.gz > out.fa
```
