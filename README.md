# Human Lung Cell Atlas: BPD Single-Cell Visualization

This project explores open single-cell RNA-seq data from the CELLxGENE Census, focusing on human lung cells and bronchopulmonary dysplasia (BPD). The analysis uses public human lung metadata, marker-gene expression, and hosted scVI embeddings to create dot plots and UMAP visualizations for a focused BPD lung-cell population.

## Project Goal

The goal is to demonstrate a concise, reproducible bioinformatics workflow using open-source single-cell data. The notebook starts with broad human lung metadata exploration, then narrows to BPD-associated lung cells across early developmental stages where the disease is most biologically relevant.

BPD is most commonly associated with premature infants and early-life lung development. For that reason, the disease-focused section looks at infant and toddler developmental stages that appear in the CELLxGENE metadata with enough BPD-labeled cells for visualization. This smaller subset makes the analysis more interpretable, limits broad age-related heterogeneity, and keeps the notebook practical to run in Colab or a local Jupyter environment.

## Notebooks

- `HCA_VisualizationNotebook_colab.ipynb`: Google Colab version with an install cell

## Data Source

Data are queried directly from CELLxGENE Census with the `cellxgene-census` Python package. No raw data files are stored in this repository. The notebook retrieves selected human lung metadata, marker gene expression, and hosted scVI embeddings at runtime.

## Workflow

1. Query primary human lung cell metadata from CELLxGENE Census.
2. Explore cell type, disease, and developmental stage distributions.
3. Generate an initial lung marker-gene dot plot across major cell populations.
4. Filter to BPD-labeled cells in infant/toddler developmental stages.
5. Sample cells by developmental stage to keep the analysis balanced and memory-conscious.
6. Generate UMAPs from hosted scVI embeddings.
7. Compare BPD marker-gene expression by cell type and developmental stage.

## Results

### BPD Cell Counts by Developmental Stage

This plot shows where BPD-labeled lung cells are represented across early developmental stages. Stages with sufficient cells are carried forward into the focused UMAP workflow.

![BPD cell counts by developmental stage](figures/bpd_cell_counts_by_development_stage.png)

### Initial Human Lung Marker Dot Plot

Canonical marker genes separate broad lung cell populations, including epithelial, endothelial, immune, myeloid, and fibroblast-associated groups.

![Human lung marker dot plot](figures/human_lung_marker_dotplot.png)

### BPD UMAP by Developmental Stage

The BPD-focused UMAP uses hosted scVI embeddings and shows how sampled infant/toddler disease-associated cells distribute by developmental stage.

![BPD UMAP by developmental stage](figures/bpd_umap_by_development_stage.png)

### BPD UMAP by Top Cell Types

The same embedding colored by the top 10 cell types highlights major cell populations in the focused BPD subset.

![BPD UMAP by top 10 cell types](figures/bpd_umap_by_top10_cell_types.png)

### BPD UMAP by Sex

This view checks whether sex metadata creates obvious structure in the BPD-focused embedding.

![BPD UMAP by sex](figures/bpd_umap_by_sex.png)

### BPD Marker Dot Plot by Developmental Stage

The final dot plot compares marker-gene expression patterns across the selected BPD developmental stages.

![BPD marker dot plot by developmental stage](figures/bpd_marker_dotplot_by_development_stage.png)
