
<!-- README.md is generated from README.Rmd. Please edit that file -->

# SimBu

<!-- badges: start -->

[![R-CMD-check](https://github.com/omnideconv/simulator/workflows/R-CMD-check/badge.svg)](https://github.com/omnideconv/simulator/actions)
<!-- badges: end -->

The goal of SimBu is to simulate pseudo-bulk RNAseq datasets from public
or private single-cell RNAseq datasets.

## Installation

To install this package, use the following command:

``` r
install.packages("devtools")
devtools::install_github("omnideconv/SimBu") # auth_token=XXX for private repository
```

If you want to use the public data integration the package offers
([sfaira](https://theislab.github.io/Datasets) database), you
additionally have to install sfaira into a new conda environment; follow
these steps in your terminal: (You need python 3.7+ to install
sfaira!)  
We recommend to use the latest version of sfaira, currently this is
0.3.9.

    conda create --name sfaira python=3.9 pip
    conda activate sfaira
    /path/to/conda/envs/sfaira/bin/pip install git+https://github.com/theislab/sfaira.git@main #this ensures that the correct pip is used

## Usage

Create a dataset-object with local data and simulate a pseudo-bulk
dataset

``` r
library(SimBu)
# use local data to build dataset
dataset <- dataset(annotation = annotation_dataframe, count_matrix = expression_matrix, name = "test_dataset")
simulation <- simulate_bulk(data = dataset, scenario = "uniform", scaling_factor = "none")
```
