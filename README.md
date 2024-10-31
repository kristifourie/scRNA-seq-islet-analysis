# scRNA-seq Analysis of Islet Cells

## Overview

This repository contains the code and data for analyzing single-cell RNA sequencing (scRNA-seq) data from human islets and stem cell-derived islets. The primary goal of this analysis is to identify and characterize beta cells within the islet cell populations.

## Table of Contents

- [Installation](#installation)
- [Data Description](#data-description)
- [Analysis Workflow](#analysis-workflow)
- [Clustering and Visualization](#clustering-and-visualization)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)

## Installation

To run the analysis, ensure you have the following dependencies installed:

- Python 3.x
- Anaconda or Miniconda
- Required Python packages:

```bash
pip install scanpy harmonypy matplotlib pandas
```

## Data Description

The dataset includes:

- **Human Islet Data**: Single-cell RNA-seq data from human islet cells.
- **SC-Derived Islet Data**: Single-cell RNA-seq data derived from stem cells.
- **Key Marker Genes**: Includes genes related to beta cell function, such as INS, PDX1, and MAFA.

Data files are organized into the following directories:

```
data/
    ├── human_islet/
    │   ├── <files>
    └── sc_islet/
        ├── <files>
```

## Analysis Workflow

The analysis involves the following key steps:

1. **Data Loading**: Load scRNA-seq data from the specified directories.
2. **Preprocessing**: Normalize, log-transform, and filter the data.
3. **Dimensionality Reduction**: Perform PCA to reduce the dimensionality of the data.
4. **Clustering**: Identify clusters using the Leiden algorithm.
5. **UMAP Visualization**: Visualize the data in reduced dimensions using UMAP.
6. **Marker Gene Analysis**: Analyze expression of known beta cell markers across clusters.

## Clustering and Visualization

The UMAP plots generated during the analysis provide insight into the clustering of islet cells and the expression levels of key beta cell markers.

```python
# Example code for generating UMAPs and clustering
sc.tl.leiden(adata_combined, resolution=0.5)
sc.tl.umap(adata_combined)
sc.pl.umap(adata_combined, color=['leiden', 'INS', 'PDX1', 'MAFA'])
```

## Results

This analysis identifies distinct clusters of islet cells and highlights the expression patterns of beta cell markers. Further investigation can lead to insights into the cellular heterogeneity within islets and the potential functional roles of identified clusters.

## Contributing

Contributions to this project are welcome! Please submit a pull request or open an issue to discuss any changes.
