---
layout: default
title:  'Labs'
---
{::options parse_block_html="true" /}

### <img border="0" src="https://www.svgrepo.com/show/7421/computer.svg" width="25" height="25"> Lab instructions

#### Clone the course repository
  
Ensure that you have followed all the [installation instructions](./precourse.html). In each container you will find a folder `workshop/` that contains the latest version of the repository. Inside you find:
- `docker/` - all container information necessary for running notebooks
- `session_preparation/` - data pre-processing, feature selection and dimensionality reduction
- `session_ml/` - the machine learning sessions, days 1 and 2
- `session_topology/` - the network topology analysis, day 3 morning
- `session_meta/` - network meta-analysis, day 3 afternoon
- `environments/` - legacy conda environments

You will need to create the [two docker containers](#containers) to run with each of the notebooks.

#### Environments
See the [pre-course installation](./precourse.md) to setup and start the docker containers. For notebooks that are in `Rmd` you should use the `rstudio` container, whereas for the `ipynb` notebooks you should use the `jupyter` container.  If you cannot setup and run these notebooks, each directory also contains the respective HTML files to assist you.  
Please refer to the next list of notebooks and environments:  

| Topic			  			| notebook type	| path to notebook																	| HTML file 					| container name 			|
| --------------------------|---------------|-----------------------------------------------------------------------------------| ------------------------------|---------------------------|
| Data pre-processing 		| jupyter  		| `/session_preparation/data_preparation/preprocessing.ipynb` 						| [html](/session_preparation/data_preparation/preprocessing.html) 						| `ismb_prep` 				|
| Dimensionality reduction	| Rmd  			| `/session_preparation/dimreduction/OmicsIntegration_DimensionReduction.Rmd`		| [html](/session_preparation/dimreduction/OmicsIntegration_DimensionReduction.html)	| `ismb_dr_ui_na`			|
| Feature selection			| Rmd  			| `/session_preparation/feature_selection/OmicsIntegration_FeatureSelection.Rmd`	| [html](/session_preparation/feature_selection/OmicsIntegration_FeatureSelection.html)	| `ismb_si_fs`				|
| Supervised Integration 	| Rmd  			| `/session_ml/SupervisedOMICsIntegration/supervised_omics_integr_CLL.Rmd`			| [html](/session_ml/SupervisedOMICsIntegration/supervised_omics_integr_CLL.html)		| `ismb_si_fs`				|
| Unsupervised Integration 	| Rmd  			| `/session_ml/UnsupervisedOMICsIntegration/UnsupervisedOMICsIntegration.Rmd`		| [html](/session_ml/UnsupervisedOMICsIntegration/UnsupervisedOMICsIntegration.html)	|`ismb_dr_ui_na`			|
| Network analysis 			| jupyter  		| `/session_topology/lab.ipynb`														| [html](/session_topology/lab.html)  													| `ismb_dr_ui_na`			|
| Network meta analysis 	| Rmd  			| `/session_meta/lab_meta-analayses-v2.Rmd`											| [html](/session_meta/lab_meta-analayses-v2.html)										| to create from within R 	|


