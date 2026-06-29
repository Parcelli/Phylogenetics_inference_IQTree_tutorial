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
### Assess  tree quality
Open the tree in **Figtree** as below to check for long branches, outliers and poorly supported branches. Generally a bootstrap value of >70% indicates reasonable support.
You will see a pop up window asking you to select the label for your input, click **OK** . Proceed to the figtree window and select the options as in the figure below to check bootsrap support value.

```
figtree aligned.treefile

```
<img width="830" height="729" alt="image" src="https://github.com/user-attachments/assets/4d2f4a2f-281a-45ba-b6f9-e2885affafac" />






