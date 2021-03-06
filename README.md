
<!-- README.md is generated from README.Rmd. Please edit that file -->

# FILEST <img src="man/figures/filest_logo.png" align="right" />

<!-- badges: start -->

[![Lifecycle:
archived](https://img.shields.io/badge/lifecycle-archived-red.svg)](https://www.tidyverse.org/lifecycle/#archived)
<!-- badges: end -->

`FILEST` (Fine-Level Structure Simulator) is a population genetic
simulator. The simulator is able to generate synthetic datasets for
single-nucleotide polymorphisms (SNP) for multiple populations. The
genetic distances among populations can be set according to the Fixation
Index (Fst). This tool is able to simulate outlying individuals and
missing SNPs can be specified. For Genome-wide association study (GWAS),
disease status can be set in desired level according risk ratio.

## Installation

You can install the released version of FILEST from
[CRAN](https://CRAN.R-project.org) with:

``` r
install.packages("FILEST")
```

Alternatively, you can install the dev version of FILEST from
[Gitlab](https://gitlab.com/chaichoompu/filest) with

``` r
install.packages("remotes")
remotes::install_gitlab("chaichoompu/filest", dependencies = TRUE)
```

## Document

You can see the reference manual from:
<https://chaichoompu.gitlab.io/filest_doc/index.html>

## Example

This best way to understand the package is the run the demo function and
edit the parameters in the setting file:

``` r
library(FILEST)

output_dir <- demo.filest()
#> Creating a setting file ... /var/folders/sp/hhmj9xvx53z4g4dktf5f503r0000gp/T//RtmpJBcXG8/example1.txt
#> Generating the simulated data  to  ... /var/folders/sp/hhmj9xvx53z4g4dktf5f503r0000gp/T//RtmpJBcXG8
#> Start [S0] at 2021-01-27 04:44:07
#> Setting file is : /var/folders/sp/hhmj9xvx53z4g4dktf5f503r0000gp/T//RtmpJBcXG8/example1.txt
#> The simulated files will be saved in this directory: /var/folders/sp/hhmj9xvx53z4g4dktf5f503r0000gp/T//RtmpJBcXG8/example1
#> Creating data file setting #1 - rep #1
#> Done - 0.0813930034637451172 secs
#> Writing data files setting #1 - rep #1
#> Done - 0.282542943954467773 secs
#> Creating status file setting #1 - rep #1
#> Done - 0.283823966979980469 secs
#> Estimating Fst setting #1 - rep #1
#> Done - 0.305084943771362305 secs
#> Creating maker information setting #1 - rep #1
#> Done - 0.540650844573974609 secs
#> Generating PC scores #1 - rep #1
#> Generating EigenVector  #1 - rep #1
#> Done - 1.12706184387207031 secs
```

The demo function creates the setting file at a temp directory as
`example1.txt`, and you can use as a template to edit:

``` r
print(file.path(output_dir,"example1.txt"))
#> [1] "/var/folders/sp/hhmj9xvx53z4g4dktf5f503r0000gp/T//RtmpJBcXG8/example1.txt"
```

The demo function create the simulated files at a temp directory as
\`well.`example1`.

``` r
dir(file.path(output_dir,"example1"))
#>  [1] "simSNP_rep1_data_numMark_rowInd_colVar.txt"
#>  [2] "simSNP_rep1_data_numMark_rowVar_colInd.txt"
#>  [3] "simSNP_rep1_eigenvector10.txt"             
#>  [4] "simSNP_rep1_estimated_Fst.txt"             
#>  [5] "simSNP_rep1_individuals_with_header.txt"   
#>  [6] "simSNP_rep1_individuals.txt"               
#>  [7] "simSNP_rep1_PC.pdf"                        
#>  [8] "simSNP_rep1_PC10.txt"                      
#>  [9] "simSNP_rep1.bed"                           
#> [10] "simSNP_rep1.bim"                           
#> [11] "simSNP_rep1.fam"                           
#> [12] "simSNP_rep1.RData"
```

## About

  - Prof. Kristel Van Steen, visit
    <a href="http://bio3.giga.ulg.ac.be/" border=0 style="border:0; text-decoration:none; outline:none"><img width="40px" src="man/figures/bio3_logo.png" align="center" /></a><br />
  - Kridsadakorn Chaichoompu, visit
    <a href="http://www.biostatgen.org/" border=0 style="border:0; text-decoration:none; outline:none"><img width="110px" src="man/figures/biostatgen_logo.png" align="center" /></a><br />
