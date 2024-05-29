
## Introduction

**gunc** (Genome UNClutterer) is a bioinformatics pipeline that is used for detection of chimerism and contamination in prokaryotic genomes resulting from mis-binning of genomic contigs from unrelated lineages. It does so by applying an entropy based score on taxonomic assignment and contig location of all genes in a genome.

1. Run CheckM ([`CheckM`](https://ecogenomics.github.io/CheckM/))
2. Run GUNC ([`GUNC`](https://grp-bork.embl-community.io/gunc/index.html))

## Usage

First, prepare a samplesheet with your input data that looks as follows:

`samplesheet.csv`:

```csv
id,group,assembler,fasta
test_minigut,0,MEGAHIT,https://github.com/nf-core/test-datasets/raw/mag/assemblies/MEGAHIT-test_minigut.contigs.fa.gz
```

Each row represents a metagenomic bin.

-->

Now, you can run the pipeline using:

```bash
nextflow run gunc \
   -profile <docker/singularity/.../institute> \
   --input samplesheet.csv \
   --outdir <OUTDIR>
```

## Credits

nf-core/gunc was originally written by Mahdi Robbani.

We thank the following people for their extensive assistance in the development of this pipeline:

- James A. Fellows Yates
- Jose Espinosa

## Citations

<!-- TODO nf-core: Add citation for pipeline after first release. Uncomment lines below and update Zenodo doi and badge at the top of this file. -->
<!-- If you use  nf-core/gunc for your analysis, please cite it using the following doi: [10.5281/zenodo.XXXXXX](https://doi.org/10.5281/zenodo.XXXXXX) -->

Tools used:
- Orakov, A., Fullam, A., Coelho, L.P. et al. GUNC: detection of chimerism and contamination in prokaryotic genomes. Genome Biol 22, 178 (2021). https://doi.org/10.1186/s13059-021-02393-0
- Parks DH, Imelfort M, Skennerton CT, Hugenholtz P, Tyson GW. 2014. Assessing the quality of microbial genomes recovered from isolates, single cells, and metagenomes. Genome Research, 25: 1043-1055.

An extensive list of references for the tools used by the pipeline can be found in the [`CITATIONS.md`](CITATIONS.md) file.

You can cite the `nf-core` publication as follows:

> **The nf-core framework for community-curated bioinformatics pipelines.**
>
> Philip Ewels, Alexander Peltzer, Sven Fillinger, Harshil Patel, Johannes Alneberg, Andreas Wilm, Maxime Ulysse Garcia, Paolo Di Tommaso & Sven Nahnsen.
>
> _Nat Biotechnol._ 2020 Feb 13. doi: [10.1038/s41587-020-0439-x](https://dx.doi.org/10.1038/s41587-020-0439-x).
