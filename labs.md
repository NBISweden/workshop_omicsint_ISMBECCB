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
See the [pre-course installation](./precourse.md), specifically [**3. Create and activate the environment**](./precourse.md#3-create-and-activate-the-environment).  
***Environments*** - we merged the environments for many notebooks down to 4 environments.  
- **Data pre-processing** (linux: `env-preprocessing_linux.yaml`, macOS: `env-preprocessing.yaml`)
- **Supervised Integration & Feature selection** (linux: `env-ml_linux.yaml` | macOS: `env-ml.yaml`)
- **Meta analysis** (R environments in linux | macOS `/session_meta/renv.lock`)
- **All remaining notebooks** (linux `env-ml_nets_linux.yaml` | MacOS `env-ml_nets.yaml`)
