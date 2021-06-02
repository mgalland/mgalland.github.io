---
layout: post
title: Get file basename and create a new one in bash 
date: 2021-04-22
---

Since I often do this operation in a for loop in bash, I thought it would be handy to store it here:  

```{bash}
for f in ../star/S01*bam ;
  do fname=$(basename $f _Aligned.sortedByCoord.out.bam);
  echo "${fname}.chr08.bam";
done
```

