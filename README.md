# RNAseq

## Methods
mRNAseq samples corresponding to the P0, P4, P7, and AD in vivo myocytes were downloaded from GEO accession (GSE64403). 
Initial quality control was performed using FastQC v0.12.0 [ref]. Reads were aligned to the gencode mouse primary assembly
genome (GRCm39, release m34) using STAR v2.7.11b [ref] with default parameters. Gene counts were generated from alignments 
using VERSE v0.1.5 with default parameters [ref] and the gencode m34 primary assembly GTF. Counts were combined and filtered
to remove genes that did not have a non-zero count in all 8 samples. Normalization and differential expression analysis was 
performed with DESeq2 v1.42.1 [ref] using default parameters comparing the AD and P0 timepoints.

## Questions to Address
Briefly remark on the quality of the sequencing reads and the alignment statistics, make sure to specifically mention the following:
  - Are there any concerning aspects of the quality control of your sequencing reads?
  - Are there any concerning aspects of the quality control related to alignment?
  - Based on all of your quality control, will you exclude any samples from further analysis?

Perform either a PCA or sample distance analysis on the counts matrix (refer to the DESeq2 vignette)
  - Remark on the plot and what it indicates to you in terms of the success of the experiment

Choose an appropriate FDR threshold to subset the differential expression results
  - How many genes are significantly differentially expressed at your chosen threshold?

Compare the results from the GSEA analysis to the gene enrichment analysis using just the DE genes (DAVID, EnrichR)
  - How similar are the results? Are there any notable differences?
  - Do you expect there to be any differences? If so, why?


## Deliverables
Produce either of the following:
1. A sample-to-sample distance plot or a PCA plot
2. A CSV of all of the results from DESeq2
3. A histogram showing the distribution of log2fold changes from your DE genes
4. A volcano plot that clearly distinguishes between significant and non-significant genes as well as whether those genes are
   up- or downregulated based on their log2foldchange. 
    - Label the top ten most significant genes on the plot
6. Perform GSEA analysis on all of the genes discovered in the experiment
    - You may choose an appropriate ranking metric
    - Report the results you believe are most interesting in a single table / figure
    - You may use the MSIGDB C2 canonical pathways collection or one of your choice
7. Use the same thresholded DE results and perform a basic enrichment analysis using a well-known annotation tool such
   as DAVID or enrichR
     - Report the results you believe are most interesting in a single table / figure

