
# TaxaSignpy

## Introduction

The TaxaSignpy is a convenient and rapid pipeline for taxonomy assignments based on rRNA sequence. The TaxaSignpy automatically defines Operational Taxonomic Units (OTUs) with raw sequence data and classify the OTUs based on the naive Bayesian classifier method. For both processes, TaxaSignpy utilizes two other published tools, [VSEARCH](https://github.com/torognes/vsearch/) and [RDP Classifier](http://rdp.cme.msu.edu/classifier/classifier.jsp).
Another goal of this project is to create a pipeline for the person who is not familiar with computation by using cloud services. For that reason, two cloud services of Google, [Colaboratory](https://colab.research.google.com/notebooks/intro.ipynb) and [Drive](https://www.google.com/drive/), was chosen. Google Colaboratory service with python3 was chosen to run the pipeline and Google drive was chosen to importing input data and store output results.

## Install

For the users who have own Linux system, they just need to install two other preprocess tools, VSEARCH and RDP Classifier. The TaxaSignpy is a python module so pipeline itself does not need extra installation steps. 
However, for the users who are going to utilize cloud service, they can run the pipeline just with run the 'ipynb' on the Google Colaboratory.

VSEARCH can be installed easily by using 'apt' command as below, or install manually with [VSEARCH github](https://github.com/torognes/vsearch/).

`apt install vsearch -y`

RDP Classifier can be installed by using 'anaconda' as below, or install manually with [RDP Classifier github](https://github.com/rdpstaff/classifier).

`conda install -c bioconda rdp_classifier -y`

## Usage
In the TaxaSignpy pipeline, there are seven different modules in detail. If you want to see the results of each step, you can use an individual module as below.

```
import TaxaSign

path = "directory of the folder which contains sequence data"
TaxaSign.taxasign( path )
TaxaSign.taxasign.fastq_merge()
TaxaSign.taxasign.fastq_filtering()
TaxaSign.taxasign.OTU_defining()
TaxaSign.taxasign.taxonomy_assigning()
TaxaSign.taxasign.analysis_statistic()
TaxaSign.taxasign.result_summary()
```

or if you want to run all the processes at once, the module as below can be used.

```
impot TaxaSign

path = "directory of the folder which contains sequence data"
TaxaSign.autorun_all( path )
```

## References
OTU, VSEARCH, RDP Classifier, google colab, google drive

* Edgar RC (2010)
**Search and clustering orders of magnitude faster than BLAST.**
*Bioinformatics*, 26 (19): 2460-2461.
doi:[10.1093/bioinformatics/btq461](http://dx.doi.org/10.1093/bioinformatics/btq461)
