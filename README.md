# TEnGExA_1.0
TEnGExA-package {TEnGExA}	R Documentation
Tissue-Enrichment Analysis of any Number of Genes and Tissues
Description

Tissue-enrichment analysis of any large number of genes with any number of tissues, irrespective of any organism provided only the read count matrix.

Details

The DESCRIPTION file: This package was not yet installed at build time.
While working on transcripts such as CDS, alternative splicing, circular RNAs or lncRNAs, one can annotate them to assign some biological process or functions to relate with some specific pathway or network analysis. But while dealing with data from multiple tissues it is always preferable to proceed with some tissue-specific or tissue-enriched transcripts only. Recently tools have been developed for tissue-enrichment analysis but not only needs technical advancement to work with but more importantly limited to specific organism or predetermined list of genes or transcripts. R package has been developed to perform tissue-enrichment analysis of any large number of genes with any number of tissues, irrespective of any organism provided only the read count matrix. Index: This package was not yet installed at build time.

Required software and packages

 R (http://www.r-project.org/)


Command

result=TEnGExA(x, fpkm_flag=0, threshold=5, tissue_num=5, min_fpkm= 1)

Parameters

########## Count matrix or FPKM matrix ########## 

x could be a count matrix with following columns:

1st column: Gene/Transcript Id, 2nd column: Gene/Transcript Length, 3rd ... nth columns are read counts of genes/transcripts in different tissues/samples

x  could be a fpkm values matrix with following columns:

1st column: Gene/Transcript Id, 2nd ... nth columns are fpkm values of genes/transcripts in different tissues/samples

########## fpkm_flag ########## 

fpkm_flag 0 for count matrix or 1 for FPKM value matrix 

Default-value 0

########## thershold ##########

fpkm value threshold to be considered for calling any gene/transcript as expressed 

Default-value 5

########## tissue_num ########## 

Minimum number of tissues to be considered for assigning group enrichment class #

Default-value 5

##########  min_fpkm ########## 

Minimum FPKM value threshold to be considered for expression analysis #########

Default-value 1

######### Output ########

The output results are in matrix form with deatils in last column

Default-outful-file output1.csv

########   ########

Author(s)


Hukam C Rawal, Angadi U B, T. K. Mondal.

Original code written by : Angadi U B Angadi UB <angadiub@gmail.com>

Maintainer: Angadi UB <angadiub@gmail.com>

Citation:

Rawal, H.C., Angadi, U., Mondal, T.K. (2021). TEnGExA: an R package based tool for tissue enrichment and gene expression analysis. Briefings in Bioinformatics, 22(3):bbaa221. https://doi.org/10.1093/bib/bbaa221

KEYWORDS

Tissue Enriched, Tissue Enhanced, Gene, Tissue, read count, FPKM


How to Run:

Download the package and untar it (eg.: tar -xzvf TEnGExA_1.0.tar.gz)

Open R enviornment

###Install package (one time only)

install.packages('./TEnGExA', repos = NULL, type="source")

### call library

library('TEnGExA')

### Run with sample file

datafile= paste(path.package("TEnGExA"),"/exdata/sample-fpkm-matrix-1.csv",sep="")

data1 = read.csv(datafile, header = TRUE)

result=TEnGExA(data1, fpkm_flag=1, threshold=5, tissue_num= 4, min_fpkm= 1)

write.csv(result, "output1.csv")
