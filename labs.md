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
See the [pre-course installation](./precourse.md) to install Conda and create the environments. To run each notebook, you need to activate the environment with `conda activate [name_of_the_environment]`. For instance, `conda activate ismb_si_fs` to activate the environment for the supervised integration and feature selection.  
Please refer to the next list of notebooks and environments:

- **Data pre-processing** (linux: `env-preprocessing_linux.yaml`, macOS: `env-preprocessing.yaml`)
- **Supervised Integration & Feature selection** (linux: `env-ml_linux.yaml` | macOS: `env-ml.yaml`)
- **Meta analysis** (R environments in linux | macOS `/session_meta/renv.lock`)
- **All remaining notebooks** (linux `env-ml_nets_linux.yaml` | MacOS `env-ml_nets.yaml`)

#### Installation problems and bugs
As the tutorial is time limited, we will not be able to assist you in debugging your installations during the hands-on sessions. Here are some helpful tips that may assist in solving installation problems or package-related bugs:  
- deactivate the environment if applicable;  
- clean cache with `conda clean -a -y`;  
- re-install the specific environment;  
- if the problem persists, consider installing the problematic package reported in the bug from terminal with `mamba install -c conda-forge [package name] --force-reinstall`. If you find 
- if the problem still persists, consider installing it manually within R from CRAN or bioconductor. You'll find all packages used at the end of each notebook and html file.

Bugs and potential solutions:
- `unable to load shared object '.../R/library/igraph/libs/igraph.dylib'`: solve in terminal with `mamba install -c conda-forge igraph --force-reinstall`  
- MOFA bugs: refer to [the MOFA repository](https://github.com/bioFAM/MOFA)