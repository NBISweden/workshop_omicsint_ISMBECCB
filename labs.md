---
layout: default
title:  'Labs'
---

### <img border="0" src="https://www.svgrepo.com/show/7421/computer.svg" width="25" height="25"> Lab instructions

#### Clone the course repository
  
Ensure that you have followed all the [installation instructions](./precourse.html). The cloned repository should contain the following folders:
- `environments/` - all conda environments necessary for running notebooks
- `session_preparation/` - data pre-processing, feature selection and dimensionality reduction
- `session_ml/` - the machine learning sessions, days 1 and 2
- `session_topology/` - the network topology analysis, day 3 morning
- `session_meta/` - network meta-analysis, day 3 afternoon

You will need to create specific [conda environments as indicated below](#environments).

#### Environments
See the [pre-course installation](./precourse.md) to install Conda and create the environments. To run each notebook, you need to activate the environment with `conda activate [name_of_the_environment]`. For instance, `conda activate ismb_si_fs` to activate the environment for the supervised integration and feature selection. If you cannot run these notebooks, each directory contains the respective HTML files to assist you.  
Please refer to the next list of notebooks and environments:  

| Topic			  			| notebook type	| path to notebook																	| environment name 			|
| --------------------------|---------------|-----------------------------------------------------------------------------------|---------------------------|
| Data pre-processing 		| jupyter  		| `/session_preparation/data_preparation/preprocessing.ipynb` 						| `ismb_prep` 				|
| Dimensionality reduction	| Rmd  			| `/session_preparation/dimreduction/OmicsIntegration_DimensionReduction.Rmd`		| `ismb_dr_ui_na`			|
| Feature selection			| Rmd  			| `/session_preparation/feature_selection/OmicsIntegration_FeatureSelection.Rmd`	| `ismb_si_fs`				|
| Supervised Integration 	| Rmd  			| `/session_ml/SupervisedOMICsIntegration/supervised_omics_integr_CLL.Rmd`			| `ismb_si_fs`				|
| Unsupervised Integration 	| Rmd  			| `/session_ml/UnsupervisedOMICsIntegration/UnsupervisedOMICsIntegration.Rmd`		| `ismb_dr_ui_na`			|
| Network analysis 			| jupyter  		| `/session_topology/lab.ipynb`														| `ismb_dr_ui_na`			|
| Network meta analysis 	| Rmd  			| `/session_meta/lab_meta-analayses-v2.Rmd`											| to create from within R 	|


#### Installation issues and bugs
As the tutorial is time limited, we will not be able to assist you in debugging your installations during the hands-on sessions. Here are some helpful tips that may assist in solving installation problems or package-related bugs:  
- deactivate the environment if applicable;  
- clean cache with `conda clean -a -y`;  
- re-install the specific environment;  
- if the problem persists, consider installing the problematic package reported in the bug from terminal with `mamba install -c conda-forge [package name] --force-reinstall`. If you find 
- if the problem still persists, consider installing it manually within R from CRAN or bioconductor. You'll find all packages used at the end of each notebook and html file.

Bugs and potential solutions:
- `unable to load shared object '.../R/library/igraph/libs/igraph.dylib'`: solve in terminal with `mamba install -c conda-forge igraph --force-reinstall`  
- `mofapy package not found.` please install it from R with `library(reticulate); use_condaenv(condaenv='ismb_dr_ui_na', required=T); py_install('mofapy', envname=' ismb_dr_ui_na', method='auto')`. For other MOFA bugs refer to [the MOFA repository](https://github.com/bioFAM/MOFA).