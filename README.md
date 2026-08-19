# Collated Bioinformatics Findings on Abundant Influenza Defective Viral Genomes

## Overview

This repository documents the bioinformatics analyses completed during my summer research project investigating **defective viral genomes (DVGs)** in influenza patient samples.

DVGs are truncated forms of viral genomes that have lost a substantial portion of their genetic material. Although they are generally unable to replicate independently, they can persist through coinfection by using the replication machinery of wildtype virus. This project investigated the characteristics, abundance, diversity, and positional distribution of influenza DVGs, with a particular focus on the most abundant DVGs within patient samples.

## Data availability and reproducibility

Some analyses in this repository form part of ongoing research. To protect unpublished results and maintain academic integrity:

- Data import code has been removed.
- Patient hospitalisation results that are not yet publicly available have been omitted.
- Analyses based on publicly available data can otherwise be reproduced by supplying the appropriate input data.

The analysis code presented in this repository is retained as documentation of the methods and computational work completed during the project.

## Main analyses

### 1. Determining an optimal bin length for DVG grouping

The primary analysis investigated how variation in DVG start and end positions could be used to establish a principled bin length for grouping similar DVGs within each influenza genome segment.

The workflow:

1. Identified the most abundant DVG in each sample.
2. Calculated pairwise differences between DVGs based on their genomic positions.
3. Applied a range of distance cutoffs to classify DVG pairs as being within or outside each cutoff.
4. Calculated the cumulative proportion of DVG pairs grouped at each cutoff.
5. Repeated the analysis independently across influenza genome segments.

This analysis was designed to identify a biologically and analytically meaningful basis for grouping DVGs before subsequent diversity and abundance analyses.

### 2. Investigating positional and length variation

Follow-up analyses examined whether observed patterns were driven primarily by DVG length or by genomic position. A length-only analysis did not reproduce the prominent pattern observed when positional information was included, supporting the interpretation that genomic position plays an important role in the structure of DVG populations.

Additional visualisations were used to examine the start and end positions of DVGs and explore potential relationships between deletion size and DVG abundance.

### 3. Analysis of samples with short dominant DVGs

Samples whose most abundant DVG was shorter than 1000 bp were examined in greater detail. The five most abundant DVGs in these samples were visualised to investigate whether small, highly abundant DVGs co-occurred with larger deletion events. 

### 4. Linkage analysis of small deletion events

A shared-read linkage analysis was performed to determine whether small deletion events were associated with other deletion events within the same samples.

Of the **34 samples analysed**:

- **14 samples had no detectable linkage events**.
- Samples with detectable linkage had between **1 and 20 linked events**.

The results suggest that small deletions may be associated with larger deletion events, potentially reflecting the accumulation or co-occurrence of multiple deletion events within samples. An alternative explanation is that multiple independent small deletions can occur within the same sample.

DVG abundance was also compared between samples with and without detectable linkage. Samples with linkage events showed considerably higher DVG abundance (cheat load), suggesting a potential association between deletion linkage and DVG abundance.

### 5. DVG richness, evenness, and community composition

Additional exploratory analyses investigated DVG diversity using:

- Bray–Curtis dissimilarity
- Pairwise community comparisons
- Richness and evenness measurements
- Simpson diversity
- Relationships between DVG abundance and diversity

Some analyses also examined differences between patient groups. As these results are part of ongoing research, the results themselves are not reported here, although the analysis pipeline is included.

### 6. Principal component analysis of DVG abundance

Principal component analysis (PCA) was used to explore variation in DVG abundance profiles across influenza genome segments and to investigate whether samples showed evidence of clustering based on their abundance profiles.

This analysis included PCA of sequencing depth and relative DVG segment abundance. Results relating to ongoing research questions are not reported, but the code used for these analyses is included.

## Repository contents

The repository contains:

- **Analysis report** — a detailed account of the methods, analyses, and findings from the project.
- **R code** — scripts and code chunks used for data processing, statistical analysis, and visualisation. **Found within the report**
- **Plots** - handful of plots produced from the original code as examples.

## Methods and skills demonstrated

This project involved:

- R programming
- Data manipulation and cleaning
- Functional programming using `lapply()` and `purrr`
- Pairwise comparisons and distance calculations
- Data reshaping with `tidyr`
- Statistical analysis
- Bray–Curtis dissimilarity analysis
- Rarefaction and diversity analysis
- Principal component analysis
- Shared-read linkage analysis
- Data visualisation using `ggplot2`

## Software and packages

The analyses were performed in R using packages including:

- `tidyverse`
- `dplyr`
- `tidyr`
- `purrr`
- `ggplot2`
- `vegan`
- `FactoMineR`
- `factoextra`
- `performance`
- `car`
- `broom`
- `emmeans`

Additional packages used for specific analyses are listed in the associated analysis code.

## Notes

This repository is intended to document the computational and analytical work completed during the project. Where analyses relate to unpublished or ongoing research, sensitive data and unreleased findings have been excluded while retaining the methodological code where appropriate.
