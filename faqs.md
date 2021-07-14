---
layout: default
title:  'FAQs'
---
{::options parse_block_html="true" /}

<style>
h1, .h1, h2, .h2, h3, .h3, h4, .h4 { margin-top: 50px }
p.caption {font-size: 0.9em;font-style: italic;color: grey;margin-right: 10%;margin-left: 10%;text-align: justify}
</style>

### <img border="0" src="https://www.svgrepo.com/show/7421/computer.svg" width="25" height="25"> Frequently asked questions

#### Installation issues and bugs
As the tutorial is time limited, we will not be able to assist you in debugging your installations during the hands-on sessions. Here are some helpful tips that may assist in solving installation problems or package-related bugs:  
- deactivate the environment if applicable;  
- clean cache with `conda clean -a -y`;  
- re-install the specific environment;  
- if the problem persists, consider installing the problematic package reported in the bug from terminal with `mamba install -c conda-forge [package name] --force-reinstall`. If you get an error `Problem: nothing provides requested [package name` please search for it [in anaconda cloud](https://anaconda.org/) and change the channel accordingly (e.g. one of `-c [bioconda | r | rdonnelly ]`);
- if the problem still persists, consider installing it manually within R from CRAN or bioconductor. You'll find all packages used at the end of each notebook and html file.

##### Bugs and potential solutions:

<details>
  <summary markdown="span">`Command line developer tools not found` (OSX)</summary></details>

  If you don't yet have Mac OSX command line developer tools, please install it using:

  ```
  xcode-select --install
  ```



<details>  
  <summary markdown="span">rstudio crashes upon opening</summary>  

  In terminal try to open R by typing: `r`. Examine the returned error.  


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