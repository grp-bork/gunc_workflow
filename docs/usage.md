# gunc: Usage

## Introduction

This documentation provides guidance for using the GUNC pipeline designed for metagenomic bin quality control. The pipeline integrates two essential tools: CheckM and Genome UNClutterer (GUNC), offering comprehensive assessment and quality control of genomes recovered from various sources.

## Samplesheet input

To use this pipeline, you'll need to prepare a samplesheet with details about the samples for analysis. The samplesheet should be a comma-separated file (CSV) with 4 columns, as described below. Use the following parameter to specify the location of your samplesheet:

```bash
--input '[path to samplesheet file]'
```

### Full samplesheet

Your samplesheet should contain columns for id, group, assembler, and fasta. Here's a brief explanation of each:

- `id``: The unique identifier for each sample.
- `group``: Group or category to which the sample belongs.
- `assembler``: The genome assembly tool used (e.g., MEGAHIT, SPAdes).
- `fasta``: URL or path to the metagenomic bin (in FASTA format).

Here's an example to illustrate the format:

```console
id,group,assembler,fasta
sample_1,0,MEGAHIT,https://github.com/nf-core/test-datasets/raw/mag/assemblies/MEGAHIT-test_minigut.contigs.fa.gz
sample_2,0,SPAdes,https://github.com/nf-core/test-datasets/raw/mag/assemblies/SPAdes-test_minigut_contigs.fasta.gz
...
```

An [example samplesheet](../assets/samplesheet.csv) has been provided with the pipeline.

## Running the pipeline

The typical command for running the pipeline is as follows:

```bash
nextflow run gunc --input ./samplesheet.csv --outdir ./results -profile docker
```

This will launch the pipeline with the `docker` configuration profile. See below for more information about profiles.

Note that the pipeline will create the following files in your working directory:

```bash
work                # Directory containing the nextflow working files
<OUTDIR>            # Finished results in specified location (defined with --outdir)
.nextflow_log       # Log file from Nextflow
# Other nextflow hidden files, eg. history of pipeline runs and old logs.
```
