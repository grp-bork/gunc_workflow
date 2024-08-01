# Output

The directories listed below will be created in the results directory after the pipeline has finished. All paths are relative to the top-level results directory.

## CheckM
- `CheckM/`
  - `*_wf.tsv`: Summary tables for each sample
  - `*_qa.txt`: Quality assessment files
  - `bins/`: Contains genes and HMM analysis files for each metagenomic bin.
  - `storage/`:  Stores extended bin statistics and marker gene stats.

[CheckM](https://ecogenomics.github.io/CheckM/) provides detailed quality assessment for metagenomic bins. Its output can be found under the `CheckM` directory.

## GUNC

- `gunc/`
  - `raw/`: Contains raw GUNC analysis files for each sample
  - `checkmmerged/`: Provides merged GUNC and CheckM results for comprehensive analysis

[GUNC](https://grp-bork.embl-community.io/gunc/) identifies chimerism and contamination in genomic bins. The relevant outputs are located in the `GUNC` directory.

