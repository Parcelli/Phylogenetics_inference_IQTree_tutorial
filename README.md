# Phlogenetics Inference Using IQTree
This tutorial walks you through a typical workflow from aligned sequences to a dated phylogeny suitable for genomic epidemiology studies.

## Pre-requisite
This tutorial assumes that you have an aligned fasta file ready for phylogenetics inference using IQ-Tree. If not please align your sequences using **mafft** and curate the alignment using **Aliview** before proceeding.

## Tool Installation using Conda 

```
conda install bioconda::iqtree
#Check success of installation
iqtree --version
```
## Tree Inference 

```
iqtree2 \
-s aligned.fasta \
-m MFP \
-bb 1000 \
-nt AUTO
```

### Parameters
| Parameter  | Meaning                 |
| ---------- | ----------------------- |
| -s         | Input alignment         |
| -m MFP     | Model Finder Plus       |
| -bb 1000   | Ultrafast bootstrap     |
| -nt AUTO   | Automatic CPU detection |


### Output files
| File      | Description             |
| --------- | ----------------------- |
| .treefile | Maximum likelihood tree |
| .iqtree   | Model and statistics    |
| .log      | Run log                 |
| .contree  | Consensus tree          |
| .ckp.gz   | Checkpoint              |

* Key Output : **aligned.treefile**


