# GUNC workflow
<table>
  <tr width="100%">
    <td width="150px">
      <a href="https://www.bork.embl.de/"><img src="https://www.bork.embl.de/assets/img/normal_version.png" alt="Bork Group Logo" width="150px" height="auto"></a>
    </td>
    <td width="425px" align="center">
      <b>Developed by the <a href="https://www.bork.embl.de/">Bork Group</a> in collaboration with <a href="https://nf-co.re/">nf-core</a></b><br>
      Raise an <a href="https://github.com/grp-bork/gunc_workflow/issues">issue</a> or <a href="mailto:N4M@embl.de">contact us</a><br><br>
      See our <a href="https://www.bork.embl.de/services.html">other Software & Services</a>
    </td>
    <td width="250px">
      Contributors:<br>
      <ul>
        <li>
          <a href="https://github.com/mahdi-robbani/">Mahdi Robbani</a> <a href="https://orcid.org/0000-0003-0161-0559"><img src="https://orcid.org/assets/vectors/orcid.logo.icon.svg" alt="ORCID icon" width="20px" height="20px"></a><br>
        </li>
        <li>
          <a href="https://github.com/cschu/">Christian Schudoma</a> <a href="https://orcid.org/0000-0003-1157-1354"><img src="https://orcid.org/assets/vectors/orcid.logo.icon.svg" alt="ORCID icon" width="20px" height="20px"></a><br>
        </li>
        <li>
          <a href="https://github.com/danielpodlesny/">Daniel Podlesny</a> <a href="https://orcid.org/0000-0002-5685-0915"><img src="https://orcid.org/assets/vectors/orcid.logo.icon.svg" alt="ORCID icon" width="20px" height="20px"></a><br>
        </li>
      </ul>
    </td>
    <td width="250px">
      Collaborators:<be>
      <ul>
        <li>
          <a href="https://github.com/JoseEspinosa/">Jose Espinosa</a>
        </li>
        <li>
          <a href="https://github.com/jfy133/">James A. Fellows Yates</a>
        </li>
      </ul>
    </td>
  </tr>
  <tr>
    <td colspan="4" align="center">The development of this workflow was supported by <a href="https://www.nfdi4microbiota.de/">NFDI4Microbiota <img src="https://github.com/user-attachments/assets/1e78f65e-9828-46c0-834c-0ed12ca9d5ed" alt="NFDI4Microbiota icon" width="20px" height="20px"></a> 
</td>
  </tr>
</table>
        
---
#### Description

The `GUNC workflow` is a nextflow workflow for the detection of chimerism & contamination in prokaryotic genomes resulting from mis-binning of contigs from unrelated lineages. The workflow is based on the `CheckM` and `GUNC` (Genome UNClutterer) tools. GUNC applies an entropy based score on taxonomic assignment and the contig location of all genes in a genome.

#### Citation
This workflow: [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.13143008.svg)](https://doi.org/10.5281/zenodo.13143008)

Also cite:
```
Orakov A, Fullam A, Coelho LP, et al. GUNC: detection of chimerism and contamination in prokaryotic genomes. Genome Biol. 2021;22(1):178. Published 2021 Jun 13. doi:10.1186/s13059-021-02393-0
Parks DH, Imelfort M, Skennerton CT, Hugenholtz P, Tyson GW. CheckM: assessing the quality of microbial genomes recovered from isolates, single cells, and metagenomes. Genome Res. 2015;25(7):1043-1055. doi:10.1101/gr.186072.114
Ewels PA, Peltzer A, Fillinger S, et al. The nf-core framework for community-curated bioinformatics pipelines. Nat Biotechnol. 2020;38(3):276-278. doi:10.1038/s41587-020-0439-x
```

An extensive list of references for the tools used by the pipeline can be found in the [`CITATIONS.md`](https://raw.githubusercontent.com/grp-bork/gunc_workflow/master/CITATIONS.md) file.

---
# Overview
1. Run CheckM ([`CheckM`](https://ecogenomics.github.io/CheckM/))
2. Run GUNC ([`GUNC`](https://grp-bork.embl-community.io/gunc/index.html))

---
# Usage
## Cloud-based Workflow Manager (CloWM)
This workflow will be available on the CloWM platform (coming soon).

## Command-Line Interface (CLI)
You can run the pipeline using:
```bash
nextflow run gunc \
   -profile <docker/singularity/.../institute> \
   --input samplesheet.csv \
   --outdir <OUTDIR>
```

## Input files
The input is a csv samplesheet with your input data that looks as follows:

`samplesheet.csv`:

```csv
id,group,assembler,fasta
test_minigut,0,MEGAHIT,https://github.com/nf-core/test-datasets/raw/mag/assemblies/MEGAHIT-test_minigut.contigs.fa.gz
```

Each row represents a metagenomic bin.
