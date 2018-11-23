Finemapping
===========

### Requirements
- GCTA >= v1.91.3 (there is a bug in v1.91.2b which causes GCTA slct to produce unexpected results)
- `conda`

### Usage

```
# Install dependencies into isolated environment
conda env create -n finemapping2 --file environment.yaml

# Activate environment
source activate finemapping2

# Alter configuration file
nano configs/config.yaml

```

# TODO
- Add logging
- Only load required fields from parquet files
- When loading, apply row filters in additions to row-group filters
- Add build 37 variant ID and position columns to sumstat files
- Add eaf_estimated column to the sumstat files and select this as eaf when loading the data (currently using MAF for molecular_qtl which is incorrect)
- Currently fails for sex chromosomes
  - Need to replace X with 23 in plink file or when specifying gcta command
  - Need to impute sex in plink file for X for cojo to work
- Only create output folders if there is anything to write
