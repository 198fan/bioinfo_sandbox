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
![Screenshot from 2023-12-04 16-05-57](https://github.com/198fan/bioinfo_sandbox/assets/92066882/90963fc8-5291-44db-81a8-cf5a2d2a44cf)
![Screenshot from 2023-12-04 16-06-50](https://github.com/198fan/bioinfo_sandbox/assets/92066882/5c204c39-ddfe-4ab1-b7f9-dac41c263403)
In this case, we need to do some trimming using because there are some adapter content and low quality at the end of reads.
```bash
fastp -i DRR024501_1.fastq -o DRR024501_1.fastp.fastq -I DRR024501_2.fastq -O DRR024501_2.fastp.fastq
```
Then we can proceed to assembly the trimmed reads.
