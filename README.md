
# Airbnb Market Analysis in Amsterdam Using Data Mining

This repository contains the source code and documentation for the final project of the course PMAAD (Preprocessing and Advanced Models for Data Analysis, UPC). The goal is to analyze and extract business insights from the Airbnb market in central Amsterdam by applying advanced data mining, geostatistics, and textual analysis techniques.

## Repository Structure
*   **`data/`**: Preprocessed datasets, intermediate datasets, and models (.rds, .csv).
*   **`images/`**: Key visualizations extracted for this documentation.
*   **`powerbi/`**: Original file, interactive dashboard export.
*   **`profiling/`**: Graphical results and tables generated during the advanced profiling phase (CPG, TLP, aTLP).
*   **`reports/`**: Technical-management reports, presentations, and submission appendices.
*   **`scripts/`**: Sequenced source code in R and Python to reproduce all project phases.


## Data Collection

The original datasets are **not included** in this repository because their size exceeds GitHub's recommended limits.

The data can be downloaded from the **Inside Airbnb** project:

[https://insideairbnb.com/get-the-data/](https://insideairbnb.com/get-the-data/)

This project uses the **Amsterdam** dataset. Once the `listings.csv` and `reviews.csv` files are downloaded, they must be copied into the `data/` directory before running the scripts.

***

## Project Phases

### PART I: Framework of Reference
Introduction to the problem of the tourist rental market in Amsterdam, description of the data source, and definition of the project scope based on business objectives.

### PART II & III: Quality, Data Preprocessing, and EDA
In-depth cleaning and database preparation for modeling:
*   **Profiling and Missings:** Quality assessment, error detection, and missing value imputation strategies.
*   **Outliers and Feature Engineering:** Outlier treatment and creation of new meaningful variables.
*   **EDA:** Univariate and bivariate Exploratory Data Analysis on the clean dataset.

### PART IV & V: Clustering and Advanced Profiling
Market segmentation to extract accommodation profiles:
*   **Clustering:** Application of advanced algorithms such as CURE (with Gower distance for mixed data).
*   **Profiling:** Construction of the *Class Profiling Graph* (CPG) and *Targeted Lexical Profiling* (TLP / aTLP) to define the semantics of the discovered clusters.

### PART VI: Factor Analysis (MCA and FAMD)
Dimensionality reduction and principal component extraction:
*   **MCA:** Multiple Correspondence Analysis on categorical variables with individual and variable analysis (Biplot).
*   **FAMD:** *Factor Analysis of Mixed Data* to structure a new clustering based on factorial coordinates.

### PART VII: Descriptive Statistics with MAPS (Descriptive Geostatistics)
Development of an interactive dashboard with Microsoft Power BI to deliver a visual, georeferenced narrative of the Airbnb data, stratified by areas and key variables.

### PART VIII: Geostatistics
Spatial modeling (Type I and Type II processes):
*   **Ordinary Kriging:** Design and validation of a spatial interpolation model to predict accommodation prices on regular grids.
*   **Point Processes:** Analysis of intensity and geographical distribution segregated by host type.



### PART IX: Textual Analysis
Natural Language Processing (NLP) on a sample of 1,000 user reviews:
*   **Text Preprocessing:** Cleaning, stemming, and creation of the DTM (Document-Term Matrix).
*   **LSA / Adapted MCA:** Simple Correspondence Analysis (CA) and CA-GALT to link terms to supplementary categorical variables.
*   **Topic Modeling (LDA):** *Latent Dirichlet Allocation* to discover latent topics within user experiences.



### PART X: Project Management and Conclusions
*   **Management:** Summary of development, incidents, and planning tools (Gantt) used.
*   **Conclusions:** Highlights and key insights aimed at business decision-making for an end client.

***

## Execution Environment

The project combines R (primary language for EDA, geostatistics, and NLP) and Python (for specific clustering algorithms such as CURE with Gower matrices). The following dependencies must be installed to run the scripts:

### R Environment

```R
# 1. Data Manipulation, Cleaning, and Transformation
install.packages(c("tidyverse", "dplyr", "tidyr", "reshape2", "Hmisc"))

# 2. Data Exploration (EDA) and Advanced Visualization
install.packages(c("visdat", "inspectdf", "skimr", "DataExplorer", "SmartEDA", 
                   "dataReporter", "patchwork", "ggcorrplot", "corrplot", 
                   "ggplot2", "ggrepel", "ggpubr", "grid", "gridExtra"))

# 3. Missing Value Treatment and Imputation
install.packages(c("naniar", "VIM", "mice", "missForest", "StatMatch"))

# 4. Outlier Detection
install.packages(c("EnvStats", "outliers", "chemometrics", "dbscan", "isotree", "tclust"))

# 5. Feature Selection and Random Forest
install.packages(c("vcd", "rcompanion", "caret", "mlbench", "XICOR", "randomForest"))

# 6. Clustering, Profiling, and Factor Analysis (MCA, FAMD, CA)
install.packages(c("dtwclust", "dendextend", "proxy", "cluster", "gower", 
                   "clustMixType", "factoextra", "flexclust", "FactoMineR", "psych"))

# 7. Geostatistics and Spatial Modeling
install.packages(c("spatstat", "sp", "sf", "gstat", "geoR", "raster", "OpenStreetMap", "rJava"))

# 8. Textual Analysis and NLP
install.packages(c("tm", "SnowballC", "topicmodels", "tidytext", "cld3", "lda", "wordcloud", "RColorBrewer"))
remotes::install_github("nikita-moor/ldatuning")
```

### Python Environment

To run the integration of algorithms and export data to R, the following packages are used:

```bash
pip install pandas numpy gower scipy matplotlib scikit-learn pyreadr
```
