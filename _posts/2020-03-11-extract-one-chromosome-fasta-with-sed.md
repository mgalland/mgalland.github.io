---
layout: post
title: Extracting one chromosome from a FASTA file with sed.
date: 2019-08-07
title: "Extracting one chromosome from a FASTA file with sed"
---


You've downloaded your favorite (plant) genome, but you'd only want to have chromosome 1 for instance. Let's suppose you're working on tomato so you'd need to extract everything between `SL4.0chr01` and `SL4.0chr02`. 


1. If you're on Mac OS X, install `gnu-sed` with `brew install gnu-sed`.
2. Then all you have to do is: `gsed -n '/SL4.0ch01/,/SL4.0ch02/p' ~/Downloads/S_lycopersicum_chromosomes.4.00.fa > S_lycopersicum_chromosomes.4.00.chrom1.fa`

You then have to remove the `>SL4.0ch02` at the end of your fasta file.   

You can do it programmatically with `head -n $(( $(wc -l S_lycopersicum_chromosomes.4.00.chrom1.fa | awk '{print $1}') - 1 )) S_lycopersicum_chromosomes.4.00.chrom1.fa > S_lycopersicum_chromosomes.4.00.chrom1.fa`
