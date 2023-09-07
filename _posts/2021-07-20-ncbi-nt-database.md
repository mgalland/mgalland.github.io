---
layout: post
title: Download the NCBI nt database
date: 2021-04-22
---

## The NCBI partially non-redundant reference nucleotide collection (nt)

From NCBI:  
"nt.gz* files contain the nucleotide sequence database, with entries from all traditional divisions of GenBank, EMBL, and DDBJ; excluding bulk divisions (gss, sts, pat, est, htg) and wgs entries. Partially non-redundant.

## Download the database programmatically

At the time of the download (July 2021), there are 41 pre-formatted files to download. 
```bash
# Download files nt.00.tar.gz to nt.10.tar.gz
for ((i=0;i<11;i++))
do 
	curl -L -R -O "ftp://ftp.ncbi.nlm.nih.gov/blast/db/nt.0${i}.tar.gz"
done 

# Download files nt.11.tar.gz to nt.41.tar.gz
for ((i=11;i<42;i++))
do 
	curl -L -R -O "ftp://ftp.ncbi.nlm.nih.gov/blast/db/nt.0${i}.tar.gz"
done 
```
