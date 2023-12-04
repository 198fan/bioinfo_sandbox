# Bioinformatics Projects

The list of what kind of project I will do to learn bioinformatics and the explanation of what I do as detailed as I can.

## Genome assembly of prokaryotic organism (Lactobacillus Hokkaidonensis)

First, get the fastq file using fastq-dump limiting the read to 1 million for ease of duration using this command
```bash
fastq-dump -X 1000000 --split-3 DRR024501
```
Then, check the basic information of the sequence that has been downloaded
```bash
seqkit stats *.fastq
```
After that, do quality check using FastQC, to check if trimming is needed or not.
```bash
fastqc -t 4 DRR024501_1.fastq DRR024501_2.fastq -o qc
```
In this case, you need