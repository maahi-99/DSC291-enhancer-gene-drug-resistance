### README: Integrative Single-Cell Multi-Omics Analysis of Drug Resistance in Breast Cancer

---
Maahi Shah, Eric Pham, Ben Deviney

#### Introduction 
This project integrates single-cell RNA sequencing (scRNA-seq) and single-cell ChIP sequencing (scChIP-seq) data to investigate transcriptional and chromatin state changes associated with drug resistance in breast cancer. By analyzing gene expression and enhancer activity in treated and untreated samples, the workflow identifies key genes and regulatory elements linked to drug resistance. The scRNA-seq data highlights differentially expressed genes, while scChIP-seq identifies differentially active enhancer regions and maps them to their target genes. The combined results provide insights into potential mechanisms of drug resistance and targets for future therapeutic strategies.

The dataset used in this analysis was downloaded from the Gene Expression Omnibus (GEO) under the accession number [GSE117309](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE117309).

---

#### How to Use the Code

1. Requirements:  
   The following Python packages were used in this analysis. Ensure they are installed in your environment:
   - `scanpy` (version 1.9.1): For scRNA-seq preprocessing, PCA, clustering, and UMAP visualization.
   - `pandas` (version 1.3.3): For handling tabular data and preprocessing enhancer-gene mapping.
   - `numpy` (version 1.21.2): For mathematical operations, such as calculating log2 fold-changes.
   - `matplotlib` (version 3.4.3): For creating visualizations such as volcano plots and UMAP projections.
   - `scipy` (version 1.7.1): For statistical testing (e.g., t-tests).

2. Code Workflow:
   - Preprocessing and Quality Control: Combine scRNA-seq and scChIP-seq data, normalize the values, and perform dimensionality reduction   - Visualization:
     - Generate UMAP plots for scRNA-seq clusters.
     - Create volcano plots to visualize significant enhancer activity.
   - Statistical Analysis:
     - Perform a two-sample t-test to identify significant enhancer regions and adjust p-values using the Bonferroni correction.
     - Calculate log2 fold-changes for enhancer regions.
   - Enhancer-Gene Mapping:
     - Use enhancer genomic coordinates to find overlapping genes and compile a list of enhancer-gene pairs.
   - Output:
     - Lists of differentially expressed genes, significant enhancer regions, and mapped enhancer-gene pairs.

3. Running the Code:  
   The provided scripts are modular and can be executed in sequence. Example steps:
   - For scRNA-seq analysis: Run the 'scRNA_seq_analysis.py' script.
   - For scChIP-seq analysis: Run the 'scChIP_seq_analysis.py' script.
   - Outputs, including UMAP plots, volcano plots, and enhancer-gene mappings, will be saved to the `output` folder.

 #### References

1. Dataset:  
   The scRNA-seq and scChIP-seq datasets were obtained from GEO under accession number [GSE117309](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE117309).  

2. Software and Packages:  
   - Wolf, F. A., Angerer, P., & Theis, F. J. (2018). Scanpy: Large-scale single-cell gene expression data analysis. *Genome Biology*, 19(15).  
   - Pedregosa, F., et al. (2011). Scikit-learn: Machine Learning in Python. *Journal of Machine Learning Research*, 12.  
