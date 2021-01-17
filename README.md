# TCGA-BRCA ILC vs IDC

This project aims to find differentially expressed genes in ductal and lobular breast cancer tissue relative to their normal breast tissue.
TCGA-BRCA project from The Cancer Genome Atlas was utilized to collect expression and clinical data. In addition, aggregated mutation data were also downloaded for analysis. The workflow is breifly described below.

### 1 Downloading data

Data were downloaded using <code>TCGAbioloinks</code> package. The downloaded data were loaded into <code>SummarizedExperiment</code> data structure first, then filterd for ILC and IDC specific samples using barcodes and primary diagnosis of the clinical data. Finally, there were clinical data for all ILC, IDC, and normal, and specifically for ILC, IDC, and normal separately. Expression data were also divided similarly. The codes can be found in the <code>download-data.Rmd</code> file.

### 2 Differential Expression Analysis

Differentially expressed genes (DEGs) were identified using voom + limma workflow. DEGs were identified within 3 different contexts. In first analysis, we utilized all tumor and normal samples which can be found in the <code>dge-limma-all.Rmd</code> file. Then we utilized only the paired samples which can be found in the <code>dge-limma-paired.Rmd</code> file. Finally, we utilized all normal samples and only the unmatched tumor samples, which can be found in the <code>dge-limma-unpaired.Rmd</code> file.

### 3 Aalysis of DEGs

Next, we analyzed the differentially expressed genes in ILC and IDC. We extracted the genes those are commonly differentially experssed between them and also those which are specificly differentially expressed in ILC and IDC. Then we analyzed the their ontologies and KEGG pathways. The codes can be found in <code>deg-analysis-all.Rmd</code> for *all* dataset. Similarly, codes for *paired* dataset can be found in <code>deg-analysis-paired.Rmd</code> file.
