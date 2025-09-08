# Cheeta
GPU-Powered Fast Scanning of Interchromosomal Linkage Disequilibrium


## Welcome to Cheeta v1.0!

### Introduction

Cheeta v1.0 (C++) has the following main functions:

1.  Processes and parses genotype data from two chromosomes, and transfers it to the GPU for computing the LD metric r² using the classic haplotype frequency estimation method.
2.  Outputs either all cross-chromosome SNP-pair LD results or only those meeting specific filtering criteria (e.g., r² ≥ 0.8).

**Note:** The two functions are implemented by one command line.

### Pre-installation

Cheeta v1.0 is implemented in C++. Before using it, please install the CUDA programming environment (CUDA 12 or newer) first.

### Download

1.  Download [Cheeta v1.0 (C++, Command-line running, Windows)](https://www.cheeta.org.cn/download/cheeta1.0.zip) - a GPU-accelerated parallel computing software for Windows.

### Usage

**Command-line example:**

```bash
cheeta interChromLDr2 -file0 file0.txt -file1 file1.txt -o output.txt [-threads threads per block] [-r2_cut cutoff] [-distribution dist_file]


### Parameters

**cheeta**: Perform interchromosomal linkage disequilibrium analysis

**interChromLDr2**: computes the LD metric r² between SNP pairs from different chromosomes:

- `-file0`: input genotype data for chromosome 1;
- `-file1`: input genotype data for chromosome 2;
- `-output`: output either all cross-chromosome SNP-pair LD results, such as the LD metric r²;
- `-threads`: Specify the number of threads, defaulting to 256;
- `-r2_cut`: Specify specific filtering criteria of r², default r² is 0.8;
- `-distribution`: Specify whether to output global LD distribution statistics, default is not;

### Input/Output Format

**Input File**: please see "input0.txt" and "input1.txt" for more information.

1.  input0.txt:
    ![input0.png](../fig/input0.png)
2.  input1.txt:
    ![input1.png](../fig/input1.png)

Both input files share the same format: each row represents a sample, and each column corresponds to the genotype of an SNP (coded as 0, 1, or 2, representing genotypes AA, Aa, and aa, respectively). The input files must be pre-processed according to the reference genome prior to analysis.

**Output File**: please see output.txt for more information.

1.  output.txt:
    ![output.png](../fig/output.png)
    
    - column 1: SNP index (column number minus one) of input chromosome 1, with counting starting from 0 (e.g., the first SNP is numbered 0 (1-1=0), the fifth SNP is numbered 4 (5-1=4));
    - column 2: SNP index of input chromosome 2;
    - column 3: the LD metric r² between SNP pairs from different chromosomes.

---


