---
layout: post
title: Optimizing VCF Parsing
---
### The Problem
The original script used a standard file read for a 50GB VCF, causing memory overflow.

### The Fix
I implemented a generator pattern using `pysam` to stream the records.



```python
# Reviewed Code Chunk
import pysam
vcf = pysam.VariantFile("large_study.vcf.gz")
for record in vcf.fetch():
    process(record) # Constant memory footprint
