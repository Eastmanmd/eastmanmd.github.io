---
layout: single
title: "Code Review Gallery"
permalink: /code-reviews/
author_profile: true
---

Showcasing my approach to optimizing genomic scripts for performance and readability.

### Case Study: Memory Optimization in Python
**Problem:** The original script attempted to load a 10GB FASTQ file into a list, causing a crash on nodes with limited RAM.

**Review & Fix:**
I refactored the process to use a generator, ensuring only one record is in memory at a time.

```python
# BEFORE: Memory Intensive
def get_reads(file):
    return open(file).readlines() # Loads everything at once

# AFTER: Memory Efficient
def get_reads(file):
    with open(file) as f:
        for line in f:
            yield line # Streams one line at a time
