# Data-driven transcriptomics analysis identifies PCSK9 as a novel target in aging liver (Arif and Matyas et al, 2023)
## Preparation

This analysis was performed succesfully in "CentOS Linux release 7.5.1804 (Core)". If you use different version of Linux or OS, you may need to adjust it accordingly and we are not responsible for any liability or error.

1. Clone the repository

2. Install miniconda [LINK](https://docs.conda.io/en/latest/miniconda.html)/anaconda [LINK](https://www.anaconda.com/products/distribution)(SKIP if you have existing installation)

3. Install R (and RStudio, if necessary), and the following R packages by executing the following commands in R/RStudio (SKIP if you have existing installation)
```

if (!require("BiocManager", quietly = TRUE))
    install.packages("BiocManager")

BiocManager::install("DESeq2")
BiocManager::install("piano")
install.packages("snowfall")

# I don't think the following is not necessary, but in case they are not automatically installed
BiocManager::install("Biobase")
install.packages("RColorBrewer")
install.packages("gplots")
install.packages("snow")
```

3. Enter the folder and create the conda environment using the environment file in the folder
```
conda env create -f env.yml
```

4. Include the new environment in Jupyter
```
ipython kernel install --user --name=LiverAging_Analysis
```

5. Download Enrichr Library for [GO Biological Processes](https://maayanlab.cloud/Enrichr/geneSetLibrary?mode=text&libraryName=GO_Biological_Process_2021) and [KEGG Human](https://maayanlab.cloud/Enrichr/geneSetLibrary?mode=text&libraryName=KEGG_2021_Human). Place them under the "lib/" folder and change their extension from ".txt" to ".gmt". WARNING!! open each file and remove the apostrophe (') sign (Find --> Replace ALL). Failure to do this will cause invalid results. Example: 'de novo' posttranslational protein folding (GO:0051084) --> de novo posttranslational protein folding (GO:0051084)

## Execution
If you have your own Jupyter, you can use it, just make sure to select the correct kernel (Step 3)

1. Open Jupyter by executing the command below
```
jupyter
```

2. Direct your browser to http://localhost:8080

3. Open the Codes.ipynb file and make sure that the selected kernel is "LiverAging_Analysis" (top right corner)

4. Run the cell one by one. 
