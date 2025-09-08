# Cheeta
GPU-Powered Fast Scanning of Interchromosomal Linkage Disequilibrium

## Navigation

- [Home](../docs/index.html)
- [Software](../software.html) (Current)

## Welcome to Cheeta v1.0!

### Introduction

Cheeta v1.0 (C++) has the following main functions:

1.  Processes and parses genotype data from two chromosomes, and transfers it to the GPU for computing the LD metric r² using the classic haplotype frequency estimation method.
2.  Outputs either all cross-chromosome SNP-pair LD results or only those meeting specific filtering criteria (e.g., r² ≥ 0.8).

**Note:** The two functions are implemented by one command line.

### Pre-installation

Cheeta v1.0 is implemented in C++. Before using it, please install the CUDA programming environment (CUDA 12 or newer) first.

### Download

1.  Download [Cheeta v1.0 (C++, Command-line running, Windows)](../download/cheeta1.0.zip) - a GPU-accelerated parallel computing software for Windows.

### Usage

**Command-line example:**

```bash
cheeta interChromLDr2 -file0 file0.txt -file1 file1.txt -o output.txt [-threads threads per block] [-r2_cut cutoff] [-distribution dist_file]
