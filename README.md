# Single-Cell RNA-seq Analysis of Pancreatic Cancer Tumor Microenvironment

## Overview
Analyzing the tumor microenvironment of pancreatic ductal adenocarcinoma (PDAC) at single-cell resolution using the Peng et al. (2019) dataset — 57,530 cells from 24 PDAC tumors and 11 normal pancreas samples.

## Motivation
PDAC has a ~12% five-year survival rate. The tumor builds a dense stroma that blocks drug delivery and recruits immunosuppressive cells. Bulk RNA-seq averages gene expression across cell types, masking the cell-type-specific interactions driving immune evasion. Single-cell RNA-seq reveals which cell types are present, how they differ between tumor and normal tissue, and how they communicate.

## Hypothesis
The PDAC tumor microenvironment has a distinct cellular composition and active signaling pathways — compared to normal pancreas — that collectively suppress immune response and protect the tumor.

## Project Structure
- `01_QC_preprocessing.ipynb` — QC, doublet detection, normalization, batch correction, clustering, UMAP
- `02_clustering_annotation.ipynb` — Cell type annotation using marker genes, tumor vs. normal comparison (in progress)
- `03_cellchat_analysis.Rmd` — Ligand-receptor signaling analysis with CellChat (planned)

## Dataset
Peng et al. (2019) "Single-cell RNA-seq highlights intra-tumoral heterogeneity and malignant progression in pancreatic ductal adenocarcinoma." Cell Research.
- Accession: CRA001160 (Genome Sequence Archive)
- 57,530 cells, 18,008 genes
- 24 PDAC tumors + 11 normal pancreas samples

## Tools
- Python: Scanpy, AnnData, Scrublet, Harmony
- R: CellChat (notebook 3)
- Environment: conda, WSL, Jupyter Lab

## Key Results (Notebook 1)
- 655 doublets detected and removed (1.1%)
- 56,875 cells retained after QC
- 2,000 highly variable genes selected
- Batch correction across 35 patients with Harmony
- 12 clusters identified with Leiden algorithm
- Tumor samples dominated by malignant ductal cells, CAFs, and macrophages
- Normal samples dominated by non-malignant ductal and acinar cells

## Notebook 1 - Results
**[View full notebook with code and plots](https://nbviewer.org/github/akalle1/scrna_pdac/blob/master/data/01_QC_preprocessing.ipynb)
