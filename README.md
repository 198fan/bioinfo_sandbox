# Bioinformatics Project

The list of what kind of project I will do to learn bioinformatics and the explanation of what I do as detailed as I can.

1. Genome assembly of prokaryotic organism (Lactobacillus Hokkaidonensis)

First, get the fastq file using fastq-dump limiting the read to 1 million of ease of duration using this command
```bash
fastq-dump -X 1000000 --split-3 DRR024501
```