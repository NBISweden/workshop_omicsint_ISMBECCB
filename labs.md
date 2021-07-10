---
layout: default
title:  'Labs'
---
{::options parse_block_html="true" /}

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

| Topic			  			| notebook type	| path to notebook																	| HTML file 					| environment name 			|
| --------------------------|---------------|-----------------------------------------------------------------------------------| ------------------------------|---------------------------|
| Data pre-processing 		| jupyter  		| `/session_preparation/data_preparation/preprocessing.ipynb` 						| [html](/session_preparation/data_preparation/preprocessing.html) 						| `ismb_prep` 				|
| Dimensionality reduction	| Rmd  			| `/session_preparation/dimreduction/OmicsIntegration_DimensionReduction.Rmd`		| [html](/session_preparation/dimreduction/OmicsIntegration_DimensionReduction.html)	| `ismb_dr_ui_na`			|
| Feature selection			| Rmd  			| `/session_preparation/feature_selection/OmicsIntegration_FeatureSelection.Rmd`	| [html](/session_preparation/feature_selection/OmicsIntegration_FeatureSelection.html)	| `ismb_si_fs`				|
| Supervised Integration 	| Rmd  			| `/session_ml/SupervisedOMICsIntegration/supervised_omics_integr_CLL.Rmd`			| [html](/session_ml/SupervisedOMICsIntegration/supervised_omics_integr_CLL.html)		| `ismb_si_fs`				|
| Unsupervised Integration 	| Rmd  			| `/session_ml/UnsupervisedOMICsIntegration/UnsupervisedOMICsIntegration.Rmd`		| [html](/session_ml/UnsupervisedOMICsIntegration/UnsupervisedOMICsIntegration.html)	|`ismb_dr_ui_na`			|
| Network analysis 			| jupyter  		| `/session_topology/lab.ipynb`														| [html](/session_topology/lab.html)  													| `ismb_dr_ui_na`			|
| Network meta analysis 	| Rmd  			| `/session_meta/lab_meta-analayses-v2.Rmd`											| [html](/session_meta/lab_meta-analayses-v2.html)										| to create from within R 	|


#### Installation issues and bugs
As the tutorial is time limited, we will not be able to assist you in debugging your installations during the hands-on sessions. Here are some helpful tips that may assist in solving installation problems or package-related bugs:  
- deactivate the environment if applicable;  
- clean cache with `conda clean -a -y`;  
- re-install the specific environment;  
- if the problem persists, consider installing the problematic package reported in the bug from terminal with `mamba install -c conda-forge [package name] --force-reinstall`. If you get an error `Problem: nothing provides requested [package name` please search for it [in anaconda cloud](https://anaconda.org/) and change the channel accordingly (e.g. `-c [bioconda | r | rdonnelly ]`);
- if the problem still persists, consider installing it manually within R from CRAN or bioconductor. You'll find all packages used at the end of each notebook and html file.

##### Bugs and potential solutions:

<details>
	<summary markdown="span">rstudio crashes upon opening</summary>  

	In terminal try to open R by typing: `r`. Examine the returned error.  

</details>
<details>
  <summary markdown="span">`unable to load shared object '.../R/library/igraph/libs/igraph.dylib'`</summary>  

  In terminal, run  

  ```
  mamba install -c conda-forge igraph --force-reinstall
  ```

</details>

<details>
	<summary markdown="span">`dyld: Library not loaded: @rpath/libncurses.6.dylib`</summary>  

	In terminal run  

	```
	mamba install conda-forge::ncurses
	```
</details>

<details>
	<summary markdown="span">`mofapy package not found.`</summary>  

	Please install it from R with  

	```
	library(reticulate)
	use_condaenv(condaenv='ismb_dr_ui_na')
	```
</details>  

<details>
	<summary markdown="span">MOFA bugs</summary>  

	Refer to [the MOFA repository](https://github.com/bioFAM/MOFA).  
</details>